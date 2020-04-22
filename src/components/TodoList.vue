<template>
  <div>
    Todo List
    <div
      v-for="(item, index) in filteredItems"
      :key="index"
      :style="item.completed && 'color:green'"
    >
      <input
        type="checkbox"
        @change="() => changeStatus(index)"
        :checked="item.completed"
      />
      {{ item.content }}
      <button @click="() => removeItem(index)">-</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "TodoList",
  props: {
    items: Array,
    filter: String
  },
  methods: {
    removeItem(index) {
      this.$emit("remove", index);
    },
    changeStatus(index) {
      this.$emit("changeStatus", index);
    }
  },
  computed: {
    filteredItems() {
      if (!this.items.length) {
        return [];
      }
      switch (this.filter) {
        case "pending":
          return this.items.filter(item => !item.completed && !item.deleted);
        case "deleted":
          return this.items.filter(item => item.deleted);
        case "completed":
          return this.items.filter(item => item.completed && !item.deleted);
        case "all":
        default:
          return this.items;
      }
    }
  }
};
</script>

<style></style>
