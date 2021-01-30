<template>
  <SingleItem
    v-for="gallery in galleries"
    :key="gallery.id"
    :gallery="gallery"
  />
</template>

<script>
import SingleItem from '@/components/SingleItem';
export default {
  components: {
    SingleItem,
  },
  props: {
    galleries: {
      type: Array,
    },
  },
  setup() {
    return {};
  },
};
</script>

<style lang="scss" scoped></style>
