<template>
  <div class="home">
    <div class="product-cards-container">
      <ProductSummaryCard
        v-for="product in items"
        :key="product.id"
        :product="product"
        v-on:view-product="viewProduct($event)"
      />
    </div>
  </div>
</template>

<script>
import items from "../data/items";
import ProductSummaryCard from "../components/products/ProductSummaryCard.vue";
// import ProductDescriptionDrawer from "../components/products/ProductDescriptionDrawer.vue";
export default {
  name: "Home",
  components: {
    ProductSummaryCard,
    // ProductDescriptionDrawer,
  },
  data() {
    return {
      items,
      product: null,
    };
  },
  methods: {
    viewProduct(product) {
      this.product = product;
    },
  },
};
</script>
<style lang="scss">
.product-cards-container {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}
</style>
