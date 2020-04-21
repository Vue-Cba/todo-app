<template>
  <div>
    <TodoInput @addItem="add" />
    <TodoList :filter="filter" :items="items" @changeStatus="changeStatus" @remove="remove" />
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
        { completed: false, content: "Task 1", deleted: false },
        { completed: false, content: "Task 2", deleted: false },
        { completed: false, content: "Task 3", deleted: false },
        { completed: true, content: "Task 4 deleted", deleted: true },
        { completed: true, content: "Task 5 completed", deleted: false }
      ],
      filter: "all"
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
      this.items[index].completed = !this.items[index].completed;
    }
  }
};
</script>

<style></style>
