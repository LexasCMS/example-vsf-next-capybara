<template>
  <component :is="section.type" :section="section" />
</template>

<script>
import BestSellers from './Section/BestSellers';
import FeaturedCategories from './Section/FeaturedCategories';
import InstagramGallery from './Section/InstagramGallery';
import NewsletterSignup from './Section/NewsletterSignup';
import PromoBanner from './Section/PromoBanner';

export default {
  components: {
    bestSellers: BestSellers,
    featuredCategories: FeaturedCategories,
    instagramGallery: InstagramGallery,
    newsletterSignup: NewsletterSignup,
    promoBanner: PromoBanner
  },

  props: {
    section: {
      type: Object,
      required: true
    }
  }
}
</script>
