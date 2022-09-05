<template>
  <div style="max-width: 1200px; height: 500px">
    <LineChart
      style="height: 100%"
      :chart-data="chartData"
      :chart-options="chartOptions"
    />
    <!-- //chart will take the parent div height 100% -->
    <select v-model="selected" @change="test(selected)">
      <option disabled value="">Please select one</option>
      <option value="1-w">1 Week</option>
      <option value="2-w">2 Weeks</option>
      <option value="3-w">3 Weeks</option>
      <option value="1-m">1 Month</option>
      <option value="1-y">1 Year</option>
    </select>
  </div>
</template>

<script>
import LineChart from "~/components/LineChart.vue";

export default {
  name: "App",
  components: {
    LineChart,
  },
  methods: {
    changeData() {
      this.chartData.labels = ["1", "2", "3", "4", "5", "6", "7", "8"];
    },
    test(value) {
      if (value == "1-w") {
        this.chartData.labels = [
          "dd:mm:yy",
          "dd:mm:yy",
          "dd:mm:yy",
          "dd:mm:yy",
          "dd:mm:yy",
          "dd:mm:yy",
          "dd:mm:yy",
          "dd:mm:yy",
        ];
      }
      if (value == "2-w") {
        this.chartData.labels = [
          "dd:mm:yy",
          "dd:mm:yy",
          "dd:mm:yy",
          "dd:mm:yy",
          "dd:mm:yy",
          "dd:mm:yy",
          "dd:mm:yy",
          "dd:mm:yy",
          "dd:mm:yy",
          "dd:mm:yy",
          "dd:mm:yy",
          "dd:mm:yy",
          "dd:mm:yy",
          "dd:mm:yy",
          "dd:mm:yy",
          "dd:mm:yy",
        ];
      }
      if (value == "3-w") {
        this.chartData.labels = [
          "dd:mm:yy",
          "dd:mm:yy",
          "dd:mm:yy",
          "dd:mm:yy",
          "dd:mm:yy",
          "dd:mm:yy",
          "dd:mm:yy",
          "dd:mm:yy",
          "dd:mm:yy",
          "dd:mm:yy",
          "dd:mm:yy",
          "dd:mm:yy",
          "dd:mm:yy",
          "dd:mm:yy",
          "dd:mm:yy",
          "dd:mm:yy",
          "dd:mm:yy",
          "dd:mm:yy",
          "dd:mm:yy",
          "dd:mm:yy",
          "dd:mm:yy",
          "dd:mm:yy",
          "dd:mm:yy",
          "dd:mm:yy",
        ];
      }
      if (value == "1-m") {
        this.chartData.labels = [
          "January",
          "February",
          "March",
          "April",
          "May",
          "June",
          "July",
          "August",
          "September",
          "October",
          "November",
          "December"
        ];
      }
      if (value == "1-y") {
        this.chartData.labels = [
          "2022",
          "2021",
          "2020",
          "2019",
          "2018",
        ];
      }
    },
  },
  data() {
    return {
      selected: "",
      chartData: {
        labels: [
        "dd:mm:yy",
          "dd:mm:yy",
          "dd:mm:yy",
          "dd:mm:yy",
          "dd:mm:yy",
          "dd:mm:yy",
          "dd:mm:yy",
          "dd:mm:yy",
        ],
        datasets: [
          {
            label: "Delivered",
            backgroundColor: "#f87979",
            data: [40, 39, 10, 40, 39, 80, 10, 100],
          },
          {
            label: "Undelivered",
            backgroundColor: "#f87979",
            data: [1, 6, 10, 5, 9, 6, 7, 15],
          },
          {
            label: "Total",
            backgroundColor: "#f87979",
            data: [41, 45, 20, 45, 44, 86, 17, 115],
          },
        ],
      },
      chartOptions: {
        responsive: true,
        maintainAspectRatio: false,
      },
    };
  },
  // computed: {
  //     chartData() { return /* mutable chart data */ },
  //     chartOptions() { return /* mutable chart options */ }
  //   }
};
</script>
