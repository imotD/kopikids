<template>
  <div id="app">
    <b-container>
      <Header />
      <b-row>
        <b-col>
          <ProductList />
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>
<script>
import Header from "@/components/Header.vue";
import ProductList from "@/components/ProductList.vue";
export default {
  name: "App",
  components: {
    Header,
    ProductList,
  },
};
</script>
