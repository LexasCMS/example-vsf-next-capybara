<template>
  <SfFooter :column="4" multiple id="footer">
    <SfFooterColumn title="Orders">
      <SfList>
        <SfListItem v-for="item in orders" :key="item.link">
          <NuxtLink :to="item.link">
            <SfMenuItem :label="item.text" />
          </NuxtLink>
        </SfListItem>
      </SfList>
    </SfFooterColumn>
    <SfFooterColumn title="Help">
      <SfList>
        <SfListItem v-for="item in help" :key="item.link">
          <NuxtLink :to="item.link">
            <SfMenuItem :label="item.text" />
          </NuxtLink>
        </SfListItem>
      </SfList>
    </SfFooterColumn>
    <SfFooterColumn title="About Us">
      <SfList>
        <SfListItem v-for="item in aboutUs" :key="item.link">
          <NuxtLink :to="item.link">
            <SfMenuItem :label="item.text" />
          </NuxtLink>
        </SfListItem>
      </SfList>
    </SfFooterColumn>
    <SfFooterColumn title="Others">
      <SfList>
        <SfListItem v-for="item in others" :key="item.link">
          <NuxtLink :to="item.link">
            <SfMenuItem :label="item.text" />
          </NuxtLink>
        </SfListItem>
      </SfList>
    </SfFooterColumn>
    <SfFooterColumn title="Social">
      <div class="footer__socials">
        <SfImage class="footer__social-image" v-for="item in social" :key="item" :src="'/icons/'+item+'.svg'" width="12" height="12" />
      </div>
    </SfFooterColumn>
  </SfFooter>
</template>

<script>
import { SfFooter, SfList, SfImage, SfMenuItem } from '@storefront-ui/vue';

export default {
  components: {
    SfFooter,
    SfList,
    SfImage,
    SfMenuItem
  },
  data() {
    return {
      orders: [
        { text: 'Delivery', link: '/static/delivery' },
        { text: 'Return Policy', link: '/static/returns' }
      ],
      help: [
        { text: 'Customer service', link: '/static/customer-service' },
        { text: 'Size guide', link: '/static/size-guide' },
        { text: 'Contact us', link: '/static/contact' }
      ],
      aboutUs: [
        { text: 'About us', link: '/static/about-us' },
        { text: 'Customer service', link: '/static/customer-service' },
        { text: 'Store locator', link: '/static/store-locator' }
      ],
      others: [
        { text: 'Legal notice', link: '/static/legal' },
        { text: 'Privacy policy', link: '/static/privacy' }
      ],
      social: ['facebook', 'pinterest', 'twitter', 'youtube'],
      isMobile: false,
      desktopMin: 1024
    };
  }
};
</script>

<style lang="scss">
.sf-footer {
  &__container {
    --footer-margin: var(--spacer-sm);
    @include for-desktop {
      --footer-margin: var(--spacer-3xl) auto var(--spacer-xl);
      --footer-padding: 0;
    }
  }
}
.footer {
  &__socials {
    display: flex;
    justify-content: space-between;
    margin: 0 0 var(--spacer-lg) 0;
    padding: var(--spacer-base) var(--spacer-xl);
    @include for-desktop {
      justify-content: flex-start;
      padding: var(--spacer-base) 0;
    }
  }
  &__social-image {
    margin: 0 var(--spacer-lg) 0 0;
  }
}
</style>
