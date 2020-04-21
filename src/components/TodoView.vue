<template>
  <div>
    <TodoInput />
    <TodoList />
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
  }
};
</script>

<style></style>
