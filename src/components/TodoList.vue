<template>
  <div>
    Todo List
    <div v-for="(item, index) in items" :key="index">
      {{item}}
    </div>
  </div>
</template>

<script>
export default {
  name: "TodoList",
  props:{
    items: Array
  }
};
</script>

<style></style>
