<template>
  <SfSection :title-heading="section.title" class="section">
    <SfCarousel class="carousel" :settings="{ peek: 16, breakpoints: { 1023: { peek: 0, perView: 2 } } }">
      <SfCarouselItem class="carousel__item" v-for="(product, i) in products" :key="i">
        <SfProductCard
          data-cy="home-url_product"
          :title="product.title"
          :image="product.image"
          :regular-price="product.price.regular"
          :max-rating="product.rating.max"
          :score-rating="product.rating.score"
          :show-add-to-cart-button="true"
          :is-on-wishlist="product.isOnWishlist"
          link="/"
          class="carousel__item__product"
          @click:wishlist="toggleWishlist(i)"
        />
      </SfCarouselItem>
    </SfCarousel>
  </SfSection>
</template>

<script>
import {
  SfCarousel,
  SfProductCard,
  SfSection
} from '@storefront-ui/vue';

export default {
  components: {
    SfCarousel,
    SfProductCard,
    SfSection
  },

  props: {
    section: {
      type: Object,
      required: true
    }
  },

  data () {
    return {
      products: [
        {
          title: 'Cream Beach Bag',
          image: '/homepage/productA.webp',
          price: { regular: '50.00 $' },
          rating: { max: 5, score: 4 },
          isOnWishlist: true
        },
        {
          title: 'Cream Beach Bag',
          image: '/homepage/productB.webp',
          price: { regular: '50.00 $' },
          rating: { max: 5, score: 4 },
          isOnWishlist: false
        },
        {
          title: 'Cream Beach Bag',
          image: '/homepage/productC.webp',
          price: { regular: '50.00 $' },
          rating: { max: 5, score: 4 },
          isOnWishlist: false
        },
        {
          title: 'Cream Beach Bag',
          image: '/homepage/productA.webp',
          price: { regular: '50.00 $' },
          rating: { max: 5, score: 4 },
          isOnWishlist: false
        },
        {
          title: 'Cream Beach Bag',
          image: '/homepage/productB.webp',
          price: { regular: '50.00 $' },
          rating: { max: 5, score: 4 },
          isOnWishlist: false
        },
        {
          title: 'Cream Beach Bag',
          image: '/homepage/productC.webp',
          price: { regular: '50.00 $' },
          rating: { max: 5, score: 4 },
          isOnWishlist: false
        },
        {
          title: 'Cream Beach Bag',
          image: '/homepage/productA.webp',
          price: { regular: '50.00 $' },
          rating: { max: 5, score: 4 },
          isOnWishlist: false
        },
        {
          title: 'Cream Beach Bag',
          image: '/homepage/productB.webp',
          price: { regular: '50.00 $' },
          rating: { max: 5, score: 4 },
          isOnWishlist: false
        }
      ]
    }
  },

  methods: {
    toggleWishlist(index) {
      this.products[index].isOnWishlist = !this.products[index].isOnWishlist;
    }
  }
}
</script>
