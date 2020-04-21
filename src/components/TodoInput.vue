<template>
  <div>
    Todo Input
    <input v-model="nuevoItem">
    <button @click="crearItem">+</button>
  </div>
</template>

<script>
export default {
  name: "TodoInput",
  data(){return{
    nuevoItem: ''
  }},
  methods:{
    crearItem(){
      if(this.nuevoItem.length > 0){
        this.$emit('crear', this.nuevoItem);
        this.nuevoItem = '';
      }else{
        alert('Para agregar un nuevo item, debes escribir algo!')
      }
    }
  }
};
</script>

<style></style>
