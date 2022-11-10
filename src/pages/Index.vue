<template>
  <Layout :class="darkMode ? 'dark-theme' : 'light-theme'">
    <Header @updateMode="toggleMode" />
    <main>
      <List />
    </main>
  </Layout>
</template>

<script>
import Header from '../components/Header.vue'
import List from  '../components/List.vue'

export default {
  metaInfo: {
    title: 'Hello, world!'
  },
  components: {
    Header,
    List
  },
  data() {
    return {
      darkMode: false
    }
  },
  methods: {
    toggleMode() {
      this.darkMode = !this.darkMode;
    }
  }
}
</script>

<style>
.home-links a {
  margin-right: 1rem;
}
</style>
