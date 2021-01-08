<template>
  <InstagramFeed :title="section.title" :subtitle="section.subtitle" />
</template>

<script>
import InstagramFeed from '../../InstagramFeed';

export default {
  components: {
    InstagramFeed
  },

  props: {
    section: {
      type: Object,
      required: true
    }
  }
};
</script>
