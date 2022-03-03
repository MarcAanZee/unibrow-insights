<template>
  <section class="forecast-graph">
      <LineChart :chartData="testData" />
  </section>
</template>

<script lang="ts">
import forecastData from "../../data.json";
import { LineChart } from 'vue-chart-3';
import { Chart, registerables } from "chart.js";

Chart.register(...registerables);

export default({
    data() {
       console.log(forecastData);
        return {
        forecast: forecastData,
      
    };
  },
  name: 'Home',
  components: { LineChart },
  setup() {
    const testData = {
      labels: ['1','2','3','4','5','6','7','8','9','10','11','12','13','14','15','16','17','18','19','20','21','22','23','24','25','26','27','28','29','30','31'],
      datasets: [
        {
          data: ['302', '290', '302', '302', '302', '302', '302', '302', '302', '302', '302', '302', '302', '302', '302', '302', '302', '302', '302',  '302', '302', '302', '302', '302', '302', '302', '302', '302', '302', '302', '302', '302', '302', '0'],
          label: "Margin",
          backgroundColor: ['#ffffff'],
          fill: false,
          borderColor: "#ffffff",
          lineTension: 0.4,
          beginAtZero: true,
        },
        {
          data: forecastData.purchase.predictions,
          label: "Purchase",
          backgroundColor: ['#3c1e5f'],
          fill: true,
          borderColor: "#ffffff00",
          lineTension: 0.4,
          beginAtZero: true
        },
        {
          data: forecastData.revenue.predictions,
          label: "revenue",
          backgroundColor: ['#ff6964'],
          fill: true,
          borderColor: "#ffffff00",
          lineTension: 0.4,
          beginAtZero: true
        },
      ],
    };
    
    Chart.defaults.plugins.legend.display = true;
    Chart.defaults.plugins.legend.align = "end";

    return { testData };
  },
});
</script>

<style lang="scss">
    @import "../../scss/global.scss",
    "forecast-graph";
</style>