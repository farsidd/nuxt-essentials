<template>
  <div>
    <h3>create page</h3>
  </div>
</template>

<script>
export default {
  layout: "",
  head() {
    return {
      title: "Create",
      meta: [
        {
          //hid and name values will remain same here and in every page
          hid: "description",
          name: "description",
          content: "Create Page content details",
        },
      ],
    };
  },
};
</script>

<style>
</style>
