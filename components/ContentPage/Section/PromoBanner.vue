<template>
  <SfHero class="section">
    <SfHeroItem
      v-for="promoBannerItem in section.bannerItems"
      :key="promoBannerItem.id"
      :title="promoBannerItem.title"
      :subtitle="promoBannerItem.subtitle"
      :button-text="promoBannerItem.buttonText"
      :image="promoBannerItem.backgroundImage.url"
      :class="promoBannerItem.alignment === 'Right' ? 'sf-hero-item--position-bg-top-left sf-hero-item--align-right' : ''"
    />
  </SfHero>
</template>

<script>
import { SfHero } from '@storefront-ui/vue';

export default {
  components: {
    SfHero
  },

  props: {
    section: {
      type: Object,
      required: true
    }
  }
}
</script>
