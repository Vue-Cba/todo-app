<template>
  <div>
    <TodoInput @crear="agregarItem"/>
    <TodoList :items="items" @borrar="borrarItem"/>
  </div>
</template>

<script>
import TodoInput from "./TodoInput";
import TodoList from "./TodoList";

export default {
  name: "TodoView",
  components: {
    TodoInput,
    TodoList
  },
  data(){return{
    items: [
      "Task 1",
      "Task 2",
      "Task 3"
    ]
  }},
  methods:{
    agregarItem(item){
      const newIndex = this.items.length;
      this.items.splice(newIndex, 0, item);
    },
    borrarItem(index){
      this.items.splice(index, 1);
    }
  }
};
</script>

<style></style>
