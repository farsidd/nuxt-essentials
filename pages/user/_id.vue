<template>
  <div><h3>page with id: {{id}} loaded</h3></div>
</template>

<script>
export default {
  //if you want to set meta information dynamically
  head() {
    return {
      title: "Create",
      meta: [
        {
          //hid and name values will remain same here and in every page
          hid: "description",
          name: "description",
          content: "Create Page content details for id: " + this.id,
        },
      ],
    };
  },
  computed: {
    id() {
    return  this.$route.params.id
    }
  }
}
</script>

<style>

</style>
