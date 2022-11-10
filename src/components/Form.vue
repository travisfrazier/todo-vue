<template>
  <form @submit.prevent="onSubmit">
    <input
      v-model.lazy.trim="label"
      type="text"
      class="todo-input"
      name="new-todo"
      autocomplete="off"
      placeholder="Create a new todo..."
    />
    <button type="submit">Add</button>
  </form>
</template>


<script>
export default {
  data() {
    return {
      label: "",
    };
  },
  methods: {
    onSubmit() {
      if (this.label === "") {
        return;
      }
      this.$emit("added", this.label);
      this.label = "";
    },
  },
};
</script>

<style lang="scss" scoped>
</style>