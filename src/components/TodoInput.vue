<template>
  <div>
    Todo Input
    <input v-model="newItem" />
    <button @click="addItem">+</button>
  </div>
</template>

<script>
export default {
  name: "TodoInput",
  data() {
    return {
      newItem: ""
    };
  },
  methods: {
    addItem() {
      if (this.newItem.length > 0) {
        this.$emit("addItem", this.newItem);
        this.newItem = "";
      } else {
        alert("Para agregar un nuevo item, debes escribir algo!");
      }
    }
  }
};
</script>

<style></style>
