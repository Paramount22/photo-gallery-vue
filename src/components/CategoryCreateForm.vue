<template>
  <form @submit.prevent="submitForm">
    <button
      @click="submitForm"
      type="button"
      class="btn btn-success modal-button"
    >
      <i class="fas fa-plus"></i> Pridať
    </button>
    <input
      ref="input"
      type="text"
      class="modal-input"
      placeholder="Zadajte názov kategórie"
      v-model="title"
    />
  </form>
</template>

<script>
import { ref, onMounted } from 'vue';
export default {
  name: 'CategoryCreateForm',
  setup(props, { emit }) {
    const title = ref('');
    const input = ref(null);

    const submitForm = () => {
      if (title.value == '') return;
      emit('new-category', title.value);
      title.value = '';
      //console.log(title.value);
    };

    onMounted(() => {});

    return {
      title,
      submitForm,
      input,
    };
  },
};
</script>

<style lang="scss" scoped></style>
