<template>
  <div class="container">
    <draggable
      v-model="items"
      item-key="id"
      @change="$emit('change', { event: $event, someAdditionalData: { test: 1 } })"
    >
      <template #item="{ element }">
        <div class="item">{{ element.name }}</div>
      </template>
    </draggable>
  </div>
</template>
<script lang="ts">
import { defineComponent } from 'vue'
import draggable from 'vuedraggable'

export default defineComponent({
  components: {
    draggable
  },
  data() {
    return {
      items: [
        {id: 1, name: 'first'}, 
        {id: 2, name: 'second'},
        {id: 3, name: 'third'}
      ]
    }
  }
})
</script>

<style>
.container {
  width: 300px;
  border: 1px solid #000;
}
.item {
  padding: 10px;
  margin: 10px;
  border: 1px solid #000;
}
</style>
