<template>
  <div>
    <h1>hello</h1>
    <h3 v-for="quote in quotes" :key="quote.id">{{quote.quote}}</h3>
    <!-- <QuoteCard v-for="(quote, index) in quotes" :key="index" :quote="quote" /> -->

  </div>
</template>

<script>
import axios from '@nuxtjs/axios'
import QuoteCard from '~/components/QuoteCard.vue';
export default {
  data() {
    return {
      quotes: null,
      test: false
    }
  },
  async asyncData({ $axios }) {
      return $axios.get("https://dummyjson.com/quotes").then(res => {
          return {
             quotes: res.data.quotes
          };
      });
  },
   created() {
      //  this.$axios.get("https://dummyjson.com/quotes").then(res => {
      //    {
      //     this.quotes = res.data.quotes
      //   }
      // })
  },
  methods: {
    getQuotes() {
    this.$axios.get("https://dummyjson.com/quotes").then(res => {
      this.quotes = res.data.quotes,
        this.test = true
    } )
    }
  },
  mounted() {
    // setTimeout(() => {
    //   this.getQuotes()
    // }, 5000);
  },
  components: { QuoteCard }
}
</script>

<style>
</style>
