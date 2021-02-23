<template>
  <div class="todo">
    <div>
      <input
        data-test="checkbox"
        type="checkbox"
        :checked="done"
        @change="change"
      />
    </div>
    <div>
      <span data-test="span" :style="styleObject">{{ text }}</span>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    text: String,
    done: Boolean,
  },
  computed: {
    styleObject() {
      const styleObject = {
        textDecoration: "none",
      };
      if (this.done) {
        styleObject.textDecoration = "line-through";
      }
      return styleObject;
    },
  },
  methods: {
    change(event) {
      this.$emit("todoDone", event.target.checked);
    },
  },
};
</script>
