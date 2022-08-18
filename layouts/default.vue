<template>
  <div>
    <div>
      <p>Default Layout</p>
      <nuxt-link to="/" >Home</nuxt-link> |
      <nuxt-link to="/create">Create</nuxt-link>
    </div>
    <Nuxt />
  </div>
</template>

<script>
export default {
  head() {
    return {
      titleTemplate: '%s - Tagline Used Along Every Page',
      meta: [
        {
          //hid and name values will remain same here and in every page
          hid: 'description',
          name: 'description',
          content: 'Index Page content details'
        }
      ]
    }
  }
}
</script>
