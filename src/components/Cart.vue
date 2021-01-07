<template>
  <div>
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
  </div>
</template>

<script>
import { mapActions, mapGetters } from "vuex";

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
  },
  methods: {
    ...mapActions(["addQty", "reduceQty", "removeItem"]),
  },
};
</script>

<style lang="scss" scoped>
.btn-qty {
  width: 30px;
}
</style>
