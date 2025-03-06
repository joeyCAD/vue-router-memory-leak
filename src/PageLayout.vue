<template>
  <div :class="`page-${ props.length }`">
    <h1>Total: {{ props.length }}</h1>
    <div v-for="index in props.length" class="render-item">
      <h4>
        {{ index }}: node content
      </h4>
      <span>node</span>
      <span>node</span>
      <span>node</span>
      <span>node</span>
      <span>node</span>
      <span>node</span>
      <span>node</span>
      <span>node</span>
      <span>node</span>
      <span>node</span>
    </div>
  </div>
</template>

<script setup lang="ts">
const props = defineProps({
  length: {
    type: Number,
    default: 10000,
  }
})
</script>

<style>
.render-item {
  margin-bottom: 6px;
  border-bottom: 1px;
}
.render-item span {
  padding: 0 4px;
}
</style>