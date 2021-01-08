<template>
  <div id="home">
    <ContentPage v-if="content[0]" :page="content[0]" />
  </div>
</template>
<script>
import { useContent } from 'vsf-lexascms';
import { onSSR } from '@vue-storefront/core';
import ContentPage from '~/components/ContentPage.vue';

export default {
  name: 'Home',

  components: {
    ContentPage
  },
  
  setup() {
    const { search, content, loading, error } = useContent();
    
    onSSR(async () => {
      await search({
        type: 'collection',
        contentType: 'contentPage',
        params: {
          filter: {
            slug: { _eq: 'homepage' }
          },
          page: {
            limit: 1,
            sections: {
              limit: 5,
              bannerItems: {
                limit: 5
              },
              featuredCategories: {
                limit: 4
              }
            }
          },
          include: 'sections,' + // Content Page Sections
                   'sections.bannerItems,sections.bannerItems.backgroundImage,' + // Promo Banner Items
                   'sections.featuredCategories,sections.featuredCategories.backgroundImage,' + // Featured Categories
                   'sections.backgroundImage', // Newsletter Signup
        }
      });
    });

    return { content };
  }
};
</script>
