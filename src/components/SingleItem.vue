<template>
  <div class="col-xl-3 col-lg-4 col-md-6 col-sm-6">
    <router-link :to="'/category/' + gallery.id">
      <div class="card category-item" @mouseover="mouseOver">
        <img
          :src="'../assets/images/' + gallery.image"
          class="card-img-top"
          :alt="gallery.title"
        />
        <div class="card-body">
          <p class="card-text">{{ gallery.title }}</p>
          <small v-if="gallery.photos.length > 0"
            >{{ gallery.photos.length }} fotiek</small
          >
        </div>
      </div>
    </router-link>
  </div>
</template>

<script>
import { ref } from 'vue';
export default {
  props: {
    gallery: {
      type: Object,
    },
  },
  setup() {
    const active = ref(false);
    const mouseOver = () => {
      active.value = !active.value;
      console.log('hover');
    };

    return { mouseOver };
  },
};
</script>

<style lang="scss" scoped></style>
