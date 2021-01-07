<template>
  <div>
    <b-row>
      <b-col cols="12" sm="4" v-for="item in products" :key="item.id">
        <b-card
          :title="item.title"
          :img-src="item.imgUrl"
          :img-alt="item.title"
          img-top
          tag="article"
          style="max-width: 20rem;"
          class="mb-2"
        >
          <b-card-text> Rp.{{ item.price }} </b-card-text>

          <b-button @click="addToCart(item)" variant="primary"
            >Add to Cart</b-button
          >
        </b-card>
      </b-col>
    </b-row>
  </div>
</template>

<script>
import { mapGetters, mapActions } from "vuex";

export default {
  name: "ProductList",
  components: {},
  data() {
    return {
      // products,
    };
  },
  mounted() {
    this.getProducts();
  },
  computed: {
    ...mapGetters(["products"]),
  },
  methods: {
    ...mapActions(["getProducts", "addToCart"]),
  },
};
</script>

<style lang="scss" scoped></style>
