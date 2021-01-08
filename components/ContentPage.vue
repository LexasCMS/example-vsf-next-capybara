<template>
  <div>
    <ContentPageSection
      v-for="section in page.sections"
      :key="section.id"
      :section="section"
    />
  </div>
</template>

<script>
import ContentPageSection from './ContentPage/Section';

export default {
  components: {
    ContentPageSection
  },

  props: {
    page: {
      type: Object,
      required: true
    }
  }
}
</script>