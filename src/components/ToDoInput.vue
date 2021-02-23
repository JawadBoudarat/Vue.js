<template>
  <div class="todo-input">
    <label for="todo-input">Introduzca un texto</label>
    <input
      type="text"
      id="todo-input"
      v-on:keyup.enter="onKeyup"
      v-model="text"
    />
  </div>
</template>

<script>
export default {
  emits: ["add"],
  data() {
    return {
      text: "",
    };
  },
  methods: {
    onKeyup() {
      if (this.text) {
        this.$emit("add", this.text);
        this.text = "";
      }
    },
  },
};
</script>

