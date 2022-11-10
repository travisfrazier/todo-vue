<template>
  <div class="todo-wrapper">
    <input @click="markComplete" :checked="isDone" :id="id" type="checkbox" />
    <label>{{ label }}</label>
    <button class="delete" @click="deleteToDo">
      <span>&times;</span>
    </button>
  </div>
</template>


<script>
export default {
  data() {
    return {
      isDone: this.done,
    };
  },
  props: {
    label: {
      type: String,
      required: true,
    },
    done: {
      type: Boolean,
      default: false,
    },
    id: {
      type: String,
      required: true,
    },
  },
  methods: {
    deleteToDo() {
      this.$emit('deleteItem');
    },
    markComplete() {
      this.$emit('markItemComplete')
    }
  }
};
</script>

<style lang="scss" scoped>
</style>