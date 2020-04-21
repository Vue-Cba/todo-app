<template>
  <div>
    Todo List
    <div
      v-for="(item, index) in items"
      :key="index"
      :style="item.status && 'color:green'"
    >
      <input
        type="checkbox"
        @change="() => changeStatus(index)"
        :checked="item.status"
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
    items: Array
  },
  methods: {
    removeItem(index) {
      this.$emit("remove", index);
    },
    changeStatus(index) {
      this.$emit("changeStatus", index);
    }
  }
};
</script>

<style></style>
