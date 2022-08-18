<template>
  <div>
    <h3>Index Page</h3>
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
  head() {
    return {
      title: 'Index Page',
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
