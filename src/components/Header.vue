<template>
  <div>
    <b-navbar toggleable="lg" variant="outline" class="bg-light mb-3">
      <b-navbar-brand href="#">Kopikids</b-navbar-brand>

      <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

      <b-collapse id="nav-collapse" is-nav>
        <!-- Right aligned nav items -->
        <b-navbar-nav class="ml-auto">
          <b-button variant="info">
            Cart <b-badge variant="light">{{ totalQty }}</b-badge>
          </b-button>
        </b-navbar-nav>
      </b-collapse>
    </b-navbar>
  </div>
</template>

<script>
import { mapGetters } from "vuex";
export default {
  name: "ProductList",
  components: {},
  data() {
    return {
      // products,
    };
  },
  computed: {
    ...mapGetters(["cart"]),
    totalQty() {
      return this.cart.reduce((a, b) => a + b.qty, 0);
    },
  },
};
</script>

<style lang="scss" scoped></style>
