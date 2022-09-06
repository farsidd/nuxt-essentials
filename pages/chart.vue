<template>
  <div style="max-width: 1200px; height: 500px">
    <LineChart style="height: 100%" :chart-data="chartData" :chart-options="chartOptions" />
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
        //we will push undelivered msgs data to zero index of array
        this.chartData.datasets[0].data = [40, 39, 10, 40, 39, 80, 10, 100, 15,56,78,32]
                //we will push delivered msgs data to zero index of array
                this.chartData.datasets[1].data = [3, 6, 10, 17, 19, 20, 22, 24, 40, 68,45,89]
                //we will push total msgs data to zero index of array
                this.chartData.datasets[2].data = [21, 29, 30, 34, 46, 49, 78, 79, 89, 99,25,78]
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
            label: "Undelivered",
            // backgroundColor: "#f87979",
            data: [1, 6, 10, 5, 9, 6, 7, 15],
            backgroundColor: "rgba(246, 71, 71, 0.5)",
        borderColor: "#36495d",
        borderWidth: 3,
        fill: true,
          },
          {
            label: "Delivered",
            backgroundColor: "rgba(3, 201, 169, 0.5)",
            data: [40, 39, 10, 40, 39, 80, 10, 100],
            fill: true,
          },

          {
            label: "Total",
            // backgroundColor: "#f87979",
            data: [41, 45, 20, 45, 44, 86, 17, 115],
            backgroundColor: "rgba(159, 90, 253, 0.5)",
        borderColor: "#47b784",
        borderWidth: 3,
        fill: true,
          },
        ],
      },
      chartOptions: {
        lineTension: 0.5,
        responsive: true,
        maintainAspectRatio: false,
    //     scales: {
    //   yAxes: [
    //     {
    //       ticks: {
    //         beginAtZero: true,
    //         padding: 25
    //       }
    //     }
    //   ]
    // }
      },
    };
  },
  // computed: {
  //     chartData() { return /* mutable chart data */ },
  //     chartOptions() { return /* mutable chart options */ }
  //   }
};
</script>
