<template>
  <div>
    <!-- Se muestra como usar una funcion y de acuerdo al parametro establece el comportamiento -->
    <!-- O definir una funcion por comportamiento deseado -->
    <button @click="selectAll">Todos {{ isFilterActive("all") }}</button>
    <button @click="selectPending">
      Pendientes {{ isFilterActive("pending") }}
    </button>
    <button @click="selectCompleted">
      Completados {{ isFilterActive("completed") }}
    </button>
    <button @click="selectDeleted">
      Borrados {{ isFilterActive("deleted") }}
    </button>
  </div>
</template>

<script>
export default {
  name: "TodoFilters",
  props: {
    value: String
  },
  methods: {
    // Si llegaramos a querer usar el v-model.lazy se debe cambiar
    // el evento a change en un lugar y no en 4
    emitSelectedFilter(filter) {
      this.$emit("input", filter);
    },
    selectAll() {
      this.emitSelectedFilter("all");
    },
    selectPending() {
      this.emitSelectedFilter("pending");
    },
    selectCompleted() {
      this.emitSelectedFilter("completed");
    },
    selectDeleted() {
      this.emitSelectedFilter("deleted");
    },
    isFilterActive(filter) {
      // String.indexOf es mas preciso que la comparacion ===
      // Pero ambas funcionan en este caso en el que
      // el programador define los string a comparar
      return filter.indexOf(this.selectedFilter) !== -1;
    }
  },
  computed: {
    // Se genera una computed para que el codigo sea mas limpio
    selectedFilter() {
      return this.value;
    }
  }
};
</script>

<style></style>
