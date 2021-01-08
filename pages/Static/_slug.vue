<template>
  <TextPage v-if="content[0]" :page="content[0]" />
</template>
<script>
import { useContent } from 'vsf-lexascms';
import { onSSR } from '@vue-storefront/core';
import TextPage from '~/components/TextPage.vue';

export default {
  components: {
    TextPage
  },

  setup(_, context) {
    const { search, content, loading, error } = useContent();
    
    onSSR(async () => {
      await search({
        type: 'collection',
        contentType: 'textPage',
        params: {
          filter: {
            slug: { _eq: context.root.$route.params.slug }
          },
          page: { limit: 1 }
        }
      });
    });

    return { content };
  }
};
</script>
