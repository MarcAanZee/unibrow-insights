<template>
  <LineChart :chartData="testData" />
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import { LineChart } from 'vue-chart-3';
import { Chart, registerables } from "chart.js";

Chart.register(...registerables);

export default defineComponent({
  name: 'Home',
  components: { LineChart },
  setup() {
    const testData = {
      labels: ['1','2','3','4','5','6','7','8','9','10','11','12','13','14','15','16','17','18','19','20','21','22','23','24','25','26','27','28','29','30','31'],
      datasets: [
        {
          data: [3500, 3800, 4100, 3900, 3800, 3200, 3800, 3200, 3500, 3900, 3600, 3200, 3000, 3300, 3200, 2900, 3100, 3000, 3900, 4100, 3200, 3600, 3800, 3100, 3500, 3600, 3800, 4000, 3500, 3700, 3200],
          backgroundColor: ['#77CEFF', '#0079AF', '#123E6B', '#97B0C4', '#A5C8ED'],
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