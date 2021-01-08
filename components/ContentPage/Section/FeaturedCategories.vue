<template>
  <SfBannerGrid :banner-grid="1" class="section banner-grid">
    <template v-for="(featuredCategory, i) in section.featuredCategories" v-slot:[bannerGridSlots[i]]>
      <SfBanner
        :key="featuredCategory.id"
        :title="featuredCategory.title"
        :subtitle="featuredCategory.subtitle"
        :description="featuredCategory.description"
        :button-text="featuredCategory.buttonText"
        :image="featuredCategory.backgroundImage.url"
        :class="'sf-'+bannerGridSlots[i]"
      />
    </template>
  </SfBannerGrid>
</template>

<script>
import {
  SfBannerGrid,
  SfBanner
} from '@storefront-ui/vue';

export default {
  components: {
    SfBannerGrid,
    SfBanner
  },

  props: {
    section: {
      type: Object,
      required: true
    }
  },

  data () {
    return {
      bannerGridSlots: [
        'banner-A',
        'banner-B',
        'banner-C',
        'banner-D'
      ]
    };
  }
}
</script>

<style lang="scss" scoped>
@import "~@storefront-ui/shared/styles/helpers/breakpoints";

.banner-grid {
  margin: var(--spacer-base) 0;
  @include for-desktop {
    margin: var(--spacer-2xl) 0;
  }
}
.sf-banner-C {
  background-position: left;
}
</style>
