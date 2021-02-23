<template>
  <Logo></Logo>
  <ToDoInput @add="handleAddTodo"></ToDoInput>
  <ToDo :text="'un todo realizado'" :done="true"></ToDo>
  <ToDo :text="'un todo por realizar'" :done="false"></ToDo>  
</template>

<script>
import Logo from "./components/Logo.vue";
import ToDoInput from "./components/ToDoInput.vue";
import ToDo from "./components/ToDo.vue"

export default {
  name: "App",
  components: {
    Logo,
    ToDoInput,
    ToDo
  },
  methods: {
    handleAddTodo(event) {
      console.log(event);
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
