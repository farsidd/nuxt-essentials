<template>
  <div>
    <h3>{{quote.quote}}</h3>
    <br>
  </div>
</template>

<script>
export default {
props: {
  quote: {
    type: Object,
    required: true
  }
}
}
</script>

<style>

</style>
