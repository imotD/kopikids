<template>
  <div>
    <b-card
      :title="item.title"
      :img-src="item.imgUrl"
      :img-alt="item.title"
      img-top
      tag="article"
      style="max-width: 20rem;"
      class="mb-2"
      v-for="item in products"
      :key="item.id"
    >
      <b-card-text>
        ${{item.price}}
      </b-card-text>

      <b-button href="#" variant="primary">Add to Cart</b-button>
    </b-card>
  </div>
</template>

<script>
import products from "../db/product.json";

export default {
  name: "ProductList",
  components: {},
  data() {
    return {
      products,
    };
  },
};
</script>

<style lang="scss" scoped></style>
