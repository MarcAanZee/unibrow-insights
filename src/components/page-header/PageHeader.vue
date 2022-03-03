<template>
  <section class="page-header">
      <div class="page-header__title">
        <h1 class="page-header__title-campaign">{{ campaignName }}</h1>
        <h2 class="page-header__title-client">{{ clientName }}</h2>
      </div>

      <div class="page-header__campaign-status">
          <div class="page-header__campaign-status-indicator" :id="isActive.campaignStatusSymbol"></div>
          <span class="page-header__campaign-status-text">{{ isActive.campaignStatus }}</span>
      </div>
  </section>
</template>

<script>
import forecastData from "../../data.json";

export default {
    data() {
        return {
            campaignName : forecastData.name,
            clientName : forecastData.client_name,
            
        }
    },
    computed: {
        isActive() {
            let activity = "";

            if(forecastData.is_active === true) {
                activity = "Active"
            } else {
                activity = "Not active"
            }

            return {
                campaignStatusSymbol: forecastData.is_active,
                campaignStatus : activity
            }
        }
    }
}
    
</script>

<style lang="scss">
@import "../../scss/global.scss",
"page-header";
</style>