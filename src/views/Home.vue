<template>
  <div>
    <Navbar></Navbar>
    <div class="container-fluid">
      <div class="row">
        <Card v-for="(product, i) in products" :key="i" :product="product"></Card>
      </div>
    </div>
  </div>
</template>

<script>
import Navbar from '../components/Navbar'
import Card from '../components/Card'

export default {
  name: 'Home',
  components: {
    Navbar,
    Card
  },
  methods: {
    fetchProducts () {
      this.$store.dispatch('fetchProducts')
      this.$router.push('/')
    }
  },
  created () {
    this.fetchProducts()
  },
  computed: {
    products () {
      return this.$store.state.products
    }
  }
}
</script>

<style>

</style>
