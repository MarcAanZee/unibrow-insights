<template>
    <section class="monthly-data">
        <h3 class="monthly-data__title">
            Monthly Forecasted Data
        </h3>

        <div class="monthly-data__inner-wrapper">
            <div class="monthly-data__block monthly-data__revenue">
                <h4 class="monthly-data__block-title">
                    Revenue
                </h4>

                <p class="monthly-data__block-items">
                    <span class="monthly-data__block-items-main monthly-data__block-revenue-month">
                        {{ RevenueMonth }}
                    </span>
                    <br>
                    <span class="monthly-data__block-items-secondary monthly-data__block-revenue-month-forecast">
                        {{ RevenueMonthForecast }}
                    </span>
                </p>
            </div>

            <div class="monthly-data__block monthly-data__cost">
                <h4 class="monthly-data__block-title">
                    Cost
                </h4>
            </div>

            <div class="monthly-data__block monthly-data__margin">
                <h4 class="monthly-data__block-title">
                    Margin
                </h4>
            </div>
        </div>
    </section>
</template>

<script>
export default {
    data() {
        return {
            RevenueMonth: "25,968.92",
            RevenueMonthForecast: "61,925.88"
        }
    }
}
</script>

<style lang="scss">
    @import "../../scss/global.scss",
    "monthly-data";
</style>