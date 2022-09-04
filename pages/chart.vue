<template>
  <div style="max-width: 1200px; height: 500px ">
    <LineChart style="height: 100%" :chart-data="chartData" :chart-options="chartOptions" />
    <!-- //chart will take the parent div height 100% -->
    <button @click.prevent="changeData">Change Data</button>
  </div>
</template>

<script>
import LineChart from '~/components/LineChart.vue'

export default {
  name: 'App',
  components: {
    LineChart
  },
  methods: {
    changeData() {
      this.chartData.labels = ['1','2','3','4','5','6','7','8'];
    }
  },
  data() {
    return {
      chartData: {
        labels: [
          'January',
          'February',
          'March',
          'April',
          'May',
          'June',
          'July',
          'August'
        ],
        datasets: [
          {
            label: 'Data One',
            backgroundColor: '#f87979',
            data: [40, 39, 10, 40, 39, 80, 10, 100]
          }
        ]
      },
      chartOptions: {
        responsive: true,
        maintainAspectRatio: false
      }
    }
  },
  // computed: {
  //     chartData() { return /* mutable chart data */ },
  //     chartOptions() { return /* mutable chart options */ }
  //   }
}
</script>
