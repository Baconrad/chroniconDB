<template>
  <div class="container">
    <nuxt-link to="/">index</nuxt-link>
  </div>
</template>

<script>
import Logo from '~/components/Logo.vue'
import axios from 'axios'

export default {
  data() {
    console.log(this.$route.params)
    console.log(this.$route.params.id)
    return {
      id: this.$route.params.id,
      title: 'Hello World!',
    }
  },
  head() {
    return {
      title: `${this.title} - Nuxt.js - ${this.id}`,
      meta: [
        { charset: 'utf-8' },
        { name: 'viewport', content: 'width=device-width, initial-scale=1' },
        {
          hid: 'description',
          name: 'description',
          content: 'Meta description',
        },
      ],
    }
  },
  validate({ params }) {
    return !isNaN(+params.id)
  },
  async asyncData({ params, error }) {
    // try {
    //   const { data } = await axios.get(`https://jsonplaceholder.typicode.com/users/${+params.id}`)
    //   return data
    // } catch (e) {
    //   error({ message: 'User not found', statusCode: 404 })
    // }
  },
}
</script>

<style></style>
