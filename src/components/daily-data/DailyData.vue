<template>
    <section class="daily-data">
        <h3 class="daily-data__title">
            Daily Statistics
        </h3>

        <div class="daily-data__inner-wrapper">
            <div class="daily-data__block" v-for="item in items" :key="item.title">
                <h4 class="daily-data__block-title">
                    {{ item.title }}
                </h4>

                <p class="daily-data__block-items-main">
                    {{ item.data }}
                </p>
            </div>
        </div>
    </section>
</template>

<script>
export default {
    data() {
        return {
            items: [
                { 
                    title: 'CTR',
                    data: '1.00%'
                },
                { 
                    title: 'CPC',
                    data: '1.19'
                },
                { 
                    title: 'CPM',
                    data: '11.85'
                },
                { 
                    title: 'CR',
                    data: '5.13%'
                },
                { 
                    title: 'CPA',
                    data: '23.09'
                },
            ],
        }
    }
}
</script>

<style lang="scss">
    @import "../../scss/global.scss",
    "daily-data";
</style>