<template>
  <div>
    <b-alert v-if="!cart.length" variant="info" show>
      No Product in cart!
    </b-alert>
    <b-alert v-if="orderLoading" variant="success" show>
      Order Successfully placed!
      <b-button-close @click="() => (orderLoading = false)"></b-button-close>
    </b-alert>
    <b-list-group>
      <b-list-group-item v-for="item in cart" :key="item.id">
        <b-button-close @click="removeItem(item.id)"></b-button-close>
        <b-media>
          <template #aside>
            <b-img :src="item.imgUrl" width="64" :alt="item.title"></b-img>
          </template>

          <h5 class="mt-0">{{ item.title }}</h5>
          <p class="mb-0">
            <b-button
              @click="reduceQty(item.id)"
              pill
              size="sm"
              class="btn-qty"
              variant="primary"
              >-</b-button
            >
            X {{ item.qty }}
            <b-button
              @click="addQty(item.id)"
              pill
              size="sm"
              class="btn-qty"
              variant="primary"
              >+</b-button
            >
          </p>
        </b-media>
      </b-list-group-item>
    </b-list-group>
    <b-button
      v-if="cart.length"
      :disabled="isLoading"
      @click="placeOrder()"
      variant="success"
      block
      size="lg"
      class="mt-3"
    >
      <span v-if="!isLoading"> Checkout(Rp.{{ totalPrice }}) </span>
      <b-spinner v-else label="Loading..."></b-spinner>
    </b-button>
  </div>
</template>

<script>
import { mapActions, mapGetters } from "vuex";

export default {
  name: "ProductList",
  components: {},
  data() {
    return {
      isLoading: false,
      orderLoading: false,
    };
  },
  computed: {
    ...mapGetters(["cart"]),
    totalPrice() {
      return this.cart.reduce((a, b) => a + b.qty * b.price, 0);
    },
  },
  methods: {
    ...mapActions(["addQty", "reduceQty", "removeItem", "emptyCart"]),
    placeOrder() {
      this.isLoading = true;
      setTimeout(() => {
        this.orderLoading = true;
        this.isLoading = false;
        this.emptyCart();
      }, 1000);
    },
  },
};
</script>

<style lang="scss" scoped>
.btn-qty {
  width: 30px;
}
</style>
