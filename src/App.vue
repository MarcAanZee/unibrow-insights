<script setup>
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup
import PageHeader from './components/page-header/PageHeader.vue'
import MonthlyData from './components/monthly-data/MonthlyData.vue'
import ForecastGraph from './components/forecast-graph/ForecastGraph.vue'
import DailyData from './components/daily-data/DailyData.vue'
</script>

<template>
  <PageHeader msg="Unibrow Insights" />
  <MonthlyData />
  <ForecastGraph />
  <DailyData />
</template>

<style lang="scss">
  @import "scss/global.scss";
</style>
