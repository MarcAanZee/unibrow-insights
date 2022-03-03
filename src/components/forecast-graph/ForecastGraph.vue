<template>
  <LineChart :chartData="testData" />
</template>

<script lang="ts">
import forecastData from "../../data.json";
import { defineComponent } from 'vue';
import { LineChart } from 'vue-chart-3';
import { Chart, registerables } from "chart.js";

Chart.register(...registerables);

export default defineComponent({
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
          data: forecastData.purchase.predictions,
          backgroundColor: ['#3c1e5f'],
          fill: true,
          borderColor: "#ffffff00",
          lineTension: 0.4,
        },
        {
          data: forecastData.revenue.predictions,
          backgroundColor: ['#ff6964'],
          fill: true,
          borderColor: "#ffffff00",
          lineTension: 0.4,
        },
      ],
    };

    return { testData };
  },
});
</script>

<style lang="scss">
    @import "../../scss/global.scss",
    "forecast-graph";
</style>