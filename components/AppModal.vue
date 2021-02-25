<template>
  <transition name="fade">
    <div v-if="isVisible === true" class="modal-container">
      <div class="backdrop"></div>
      <main class="modal-container__modal-window">
        <header class="modal-container__modal-window__header">
          <h3>{{ modalHeader }}</h3>
          <awesome-icon
            name="times"
            class="modal-container__modal-window__close-logo"
            scale="1.3"
            @click="closeModal"
          />
        </header>
        <section class="modal-container__modal-window__body">
          <p>{{ modalBody }}</p>
        </section>
        <footer
          class="modal-container__modal-window__footer d-flex flex-row aic jsfe"
        >
          <button
            v-if="modalType === confirm"
            class="flex-w-30 btn-primary"
            @click="modalFunction"
          >
            Accept
          </button>
          <button v-else class="flex-w-30 btn-primary" @click="closeModal">
            Accept
          </button>
          &nbsp;
          <button
            v-if="modalType === confirm"
            class="flex-w-30 btn-secondary"
            @click="closeModal"
          >
            Cancel
          </button>
        </footer>
      </main>
    </div>
  </transition>
</template>

<script>
export default {
  props: {
    modalType: {
      type: String,
      default: 'Info',
    },
    modalHeader: {
      type: String,
      default: 'Information',
    },
    modalBody: {
      type: String,
      default: 'A really usefull information',
    },
    modalFunction: {
      type: Function,
      default: () => {},
    },
    modalShow: {
      type: Boolean,
      default: false,
    },
  },
  data() {
    return {
      isVisible: this.modalShow,
    }
  },
  methods: {
    closeModal() {
      this.isVisible = false
    },
  },
}
</script>

<style lang="scss" scoped>
.fade-enter-active {
  transition: all 0.3s ease;
}
.fade-leave-active {
  transition: all 0.4s ease-in;
}
.fade-enter,
.fade-leave-to {
  transform: translateX(10px);
  opacity: 0;
}
</style>
