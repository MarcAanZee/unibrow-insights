<template>
    <section class="monthly-data">
        <h3 class="monthly-data__title">
            Monthly Forecasted Data
        </h3>

        <div class="monthly-data__inner-wrapper">
            <div class="monthly-data__block" v-for="item in calcMonth" :key="item.title">
                <h4 class="monthly-data__block-title">
                    {{ item.title }}
                </h4>

                <p class="monthly-data__block-items-main">
                    {{ item.data }}
                </p>

                <p class="monthly-data__block-items-secondary">
                    {{ item.projectedData }}
                </p>
            </div>
        </div>
    </section>
</template>

<script>
import forecastData from "../../data.json";

export default {
    computed: {
        calcMonth() {
            // Revenue functions
            const totalRev = forecastData.revenue.predictions.reduce(
            (previousValue, currentValue) => previousValue + currentValue,
            0);

            const currentRev = forecastData.revenue.predictions.splice(0, 3).reduce(
            (previousValue, currentValue) => previousValue + currentValue,
            0);

            // Purchase functions
            const totalPur = forecastData.purchase.predictions.reduce(
            (previousValue, currentValue) => previousValue + currentValue,
            0);

            const currentPur = forecastData.purchase.predictions.splice(0, 3).reduce(
            (previousValue, currentValue) => previousValue + currentValue,
            0);

            return [
                { 
                    title: 'Revenue',
                    data: currentRev.toFixed(2),
                    projectedData: totalRev.toFixed(2)
                },
                { 
                    title: 'Cost',
                    data: currentPur.toFixed(2),
                    projectedData: totalPur.toFixed(2)
                },
                { 
                    title: 'Margin',
                    data: (currentRev - currentPur).toFixed(2),
                    projectedData: (totalRev - totalPur).toFixed(2) 
                },
            ]
        }    
    }
}
</script>

<style lang="scss">
    @import "../../scss/global.scss",
    "monthly-data";
</style>