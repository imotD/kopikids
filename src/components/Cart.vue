<template>
  <div>
    <b-list-group>
      <b-list-group-item>
        <b-button-close></b-button-close>
        <b-media>
          <template #aside>
            <b-img
              src="https://mothercare.cdn.imgeng.in/media/catalog/product/cache/9eddba54ba18d67f61cc4c1639cb8516/l/v/lvf002_1_wid_1200_hei_1200.jpg"
              width="64"
              alt="placeholder"
            ></b-img>
          </template>

          <h5 class="mt-0">Judul</h5>
          <p class="mb-0">
            <b-button pill size="sm" class="btn-qty" variant="primary"
              >-</b-button
            >
            X 1
            <b-button pill size="sm" class="btn-qty" variant="primary"
              >+</b-button
            >
          </p>
        </b-media>
      </b-list-group-item>
    </b-list-group>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
.btn-qty {
  width: 30px;
}
</style>
