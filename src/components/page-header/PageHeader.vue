<template>
  <section class="page-header">
      <div class="page-header__title">
        <h1 class="page-header__title-campaign">{{ campaignName }}</h1>
        <h2 class="page-header__title-client">{{ clientName }}</h2>
      </div>

      <div class="page-header__campaign-status">
          <div class="page-header__campaign-status-indicator"></div>
          <span class="page-header__campaign-status-text">{{ campaignStatus }}</span>
      </div>
  </section>
</template>

<script>

export default {

    data() {
        return {
            campaignName : "Verisure DE - V7 - SLP - € 300 discount - ZOE",
            clientName : "Verisure Deutschland GmbH",
            campaignStatus : "Active"
        }
    }

}
    
</script>

<style lang="scss">
@import "../../scss/global.scss",
"page-header";
</style>