<template>
  <transition name="toast">
    <div v-if="showToast === true" class="toast-container">
      <div :class="toastAccent"></div>
      <awesome-icon
        v-if="toastType === 'info'"
        name="info-circle"
        scale="3.5"
        class="toast-container__toast-logo color-yellow-300"
      />
      <awesome-icon
        v-else-if="toastType === 'success'"
        name="check-circle"
        scale="3.5"
        class="toast-container__toast-logo color-green-300"
      />
      <awesome-icon
        v-else
        name="exclamation-circle"
        scale="3.5"
        class="toast-container__toast-logo color-red-300"
      />
      <div class="toast-container__toast-message">
        <p v-if="toastType === 'info'" class="color-grey-200">Info</p>
        <p v-else-if="toastType === 'success'" class="color-grey-200">
          Success
        </p>
        <p v-else class="color-grey-200">Error</p>
        <span class="color-grey-400">{{ toastMessage }}</span>
      </div>
      <awesome-icon
        name="times"
        class="toast-container__close-logo"
        @click="closeToast"
      />
    </div>
  </transition>
</template>

<script>
export default {
  props: {
    toastType: {
      type: String,
      default: 'info',
    },
    toastMessage: {
      type: String,
      default: 'I am a message',
    },
    toastShow: {
      type: Boolean,
      default: false,
    },
  },
  data() {
    return {
      showToast: this.toastShow,
    }
  },
  computed: {
    toastAccent() {
      let toastAccentClass = 'toast-container__toast-accent--'
      if (this.toastType === 'error') return (toastAccentClass += 'error')
      if (this.toastType === 'success') return (toastAccentClass += 'success')
      return (toastAccentClass += 'info')
    },
  },
  created() {
    this.autoClose()
  },
  methods: {
    closeToast() {
      this.showToast = false
    },
    autoClose() {
      setTimeout(() => (this.showToast = false), 2000)
    },
  },
}
</script>

<style lang="scss" scoped>
.toast-enter-active {
  transition: all 0.3s ease;
}
.toast-leave-active {
  transition: all 0.8s ease-in;
}
.toast-enter,
.toast-leave-to {
  transform: translateX(10px);
  opacity: 0;
}
</style>
