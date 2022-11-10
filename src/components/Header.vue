<template>
  <header class="header">
    <div class="container">
      <h1>TODO</h1>
      <g-image @click="changeMode" v-if="!darkMode" class="image-toggle" src="../images/icon-moon.svg" />
      <g-image @click="changeMode" v-if="darkMode" class="image-toggle" src="../images/icon-sun.svg" />
    </div>
  </header>
</template>

<script>
export default {
  data() {
    return {
      darkMode: false
    }
  },
  methods: {
    changeMode() {
      this.darkMode = !this.darkMode;
      this.$emit('updateMode');
    }
  }
};
</script>

<style lang="scss" scoped>
</style>