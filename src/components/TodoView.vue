<template>
  <div>
    <TodoInput />
    <TodoList :items="items" />
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
  }}
};
</script>

<style></style>
