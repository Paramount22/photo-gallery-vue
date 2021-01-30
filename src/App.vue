<template>
  <div>
    <header></header>
    <section class="galleries-set container">
      <h3>Fotogaléria</h3>
      <h4>Kategórie</h4>

      <div class="items">
        <div class="row">
          <ListItems :galleries="galleries" />
          <div class="col-xl-3 col-lg-4 col-md-6 col-sm-6">
            <a href="#" data-toggle="modal" data-target="#add-new-category">
              <div class="card add-card">
                <div class="card-body add-category">
                  <!-- Button trigger modal -->
                  <i class="fas fa-plus"></i>
                  <p class="card-text modal-text">Pridať kategóriu</p>
                </div>
              </div>
            </a>
          </div>
          <!-- Modal -->
          <div
            class="modal fade"
            id="add-new-category"
            tabindex="-1"
            aria-labelledby="add-new-categoryLabel"
            aria-hidden="true"
          >
            <div class="modal-dialog modal-dialog-centered">
              <div class="modal-content">
                <div class="modal-header">
                  <h5 class="modal-title" id="add-new-categoryLabel">
                    Pridať kategóriu
                  </h5>

                  <button
                    type="link"
                    class="close-modal"
                    data-dismiss="modal"
                    aria-label="Close"
                  >
                    <span class="close-mark" aria-hidden="true">&times; </span>
                    <span class="close-word">Zavrieť</span>
                  </button>
                </div>
                <div class="modal-body">
                  <button type="button" class="btn btn-success modal-button">
                    <i class="fas fa-plus"></i> Pridať
                  </button>
                  <form>
                    <input
                      type="text"
                      class="modal-input"
                      placeholder="Zadajte názov kategórie"
                    />
                  </form>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
import { ref } from 'vue';
import { data } from './data';
import ListItems from './components/ListItems';

export default {
  components: {
    ListItems,
  },
  setup() {
    const galleries = ref(data);

    return {
      galleries,
    };
  },
};
</script>
