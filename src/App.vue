<template>
  <div id="app">
    <b-container>
      <Header />
      <b-row>
        <b-col lg="8">
          <ProductList />
        </b-col>
        <b-col lg="4">
          <Cart />
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>
<script>
import Header from "@/components/Header.vue";
import ProductList from "@/components/ProductList.vue";
import Cart from "@/components/Cart.vue";
export default {
  name: "App",
  components: {
    Header,
    ProductList,
    Cart
  },
};
</script>
