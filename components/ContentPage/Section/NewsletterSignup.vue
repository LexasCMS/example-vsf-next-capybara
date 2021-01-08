<template>
  <SfCallToAction
    :title="section.title"
    :description="section.subtitle"
    :button-text="section.buttonText"
    :image="section.backgroundImage.url"
  />
</template>

<script>
import { SfCallToAction } from '@storefront-ui/vue';

export default {
  components: {
    SfCallToAction
  },

  props: {
    section: {
      type: Object,
      required: true
    }
  }
}
</script>