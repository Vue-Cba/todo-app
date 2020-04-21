<template>
  <div>
    Todo App
    <TodoView />
  </div>
</template>

<script>
import TodoView from "./components/TodoView";

export default {
  name: "App",
  components: {
    TodoView
  }
};
</script>
