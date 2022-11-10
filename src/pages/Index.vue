<template>
  <Layout>
    <Header />
    <main>
      <List />
    </main>
    <Complete />
  </Layout>
</template>

<script>
import Header from '../components/Header.vue'
import List from  '../components/List.vue'
import Complete from '../components/Complete.vue'

export default {
  metaInfo: {
    title: 'Hello, world!'
  },
  components: {
    Header,
    List,
    Complete
  }
}
</script>

<style>
.home-links a {
  margin-right: 1rem;
}
</style>
