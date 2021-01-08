<template>
  <div id="text-page">
    <SfHeading :level="1" :title="page.title" />
    <div class="text-page__content" v-html="$md.render(page.message)"></div>
  </div>
</template>

<script>
import { SfHeading } from '@storefront-ui/vue';

export default {
  components: {
    SfHeading
  },

  props: {
    page: {
      type: Object,
      required: true
    }
  }
}
</script>

<style type="text/css" scoped>
#text-page {
  max-width: 700px;
  margin: 0 auto;
}
#text-page .sf-heading {
  margin-top: 4rem;
}
.text-page__content {
  line-height: 1.6;
}
</style>
