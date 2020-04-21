<template>
  <div>
    Todo List
    <div v-for="(item, index) in items" :key="index">
      {{item}}
      <button @click="()=>borrarItem(index)">-</button> 
    </div>
  </div>
</template>

<script>
export default {
  name: "TodoList",
  props:{
    items: Array
  },
  methods:{
    borrarItem(index){
      this.$emit('borrar', index)
    }
  }
};
</script>

<style></style>
