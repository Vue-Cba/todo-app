<template>
  <div>
    <TodoInput @addItem="add" />
    <TodoList :items="items" @changeStatus="changeStatus" @remove="remove" />
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
  data() {
    return {
      items: [
        { status: false, content: "Task 1" },
        { status: false, content: "Task 2" },
        { status: false, content: "Task 3" }
      ]
    };
  },
  methods: {
    add(content) {
      const newIndex = this.items.length;
      const newItem = { status: false, content: content };
      this.items.splice(newIndex, 0, newItem);
    },
    remove(index) {
      this.items.splice(index, 1);
    },
    changeStatus(index) {
      this.items[index].status = !this.items[index].status;
    }
  }
};
</script>

<style></style>
