<template>
  <div class="col-xl-3 col-lg-4 col-md-6 col-sm-6">
    <router-link to="">
      <div class="card category-item">
        <img
          :src="'../assets/images/' + gallery.image"
          class="card-img-top"
          :alt="gallery.title"
        />
        <div class="card-body">
          <p class="card-text">{{ gallery.title }}</p>
          <small></small>
        </div>
      </div>
    </router-link>
  </div>
</template>

<script>
export default {
  props: {
    gallery: {
      type: Object,
    },
  },
  setup() {
    return {};
  },
};
</script>

<style lang="scss" scoped></style>
