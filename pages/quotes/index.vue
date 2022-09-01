<template>
  <div>

    <!-- <h3 v-for="quote in quotes" :key="quote.id">{{quote.quote}}</h3> -->
    <!-- <QuoteCard v-for="(quote, index) in quotes" :key="index" :quote="quote" /> -->

  </div>
</template>

<script>
import QuoteCard from '~/components/QuoteCard.vue';
export default {
  components: {
    QuoteCard
  },
  async mounted() {
    // by using await keyword it will wait 5 seconds and then run any code below this request
    // if you did'nt use await or async then the below code run immediately
    const res = await this.$axios.get('https://jsonplaceholder.typicode.com/todos/6?_delay=5000')
    console.log('5 seconds completed')
  },

  // asyncData technique used to render component with all the required data and then show it
  // to make it pure server side render which is good for SEO.
  // Otherwise if we fetch data in created or mounted hook it will not contain the data if you check page code
  // asyncData run on server side so if we want to use axios, error, params or anything to do something we will do like this

  //  asyncData({ $axios }) {
  //     return $axios.get("https://dummyjson.com/quotes").then(res => {
  //         return {
  //            quotes: res.data.quotes
  //         };
  //     });
  // },

  // Now we will use the same strategy but with async & await keyword. await will not allow javascript to run further until
  // the response not received

  // async asyncData({ $axios }) {
  //   try {
  //     const res = await $axios.get("https://dummyjson.com/quotes")
  //     return {
  //       quotes: res.data.quotes
  //     };
  //   }
  //   catch {
  //     (e) => {
  //         console.log(e)
  //     }

  //   }


  // },
}
</script>

<style>
</style>
