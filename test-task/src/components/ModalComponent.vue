<template>
  <transition name="fade" appear>
    <div class="modal" v-if="showModal">
      <div class="modal__container">
        <span class="modal__close _ibg" @click="hideModal"
          ><img src="../assets/icons/x.svg" alt="Close icon" title="Close icon"
        /></span>
        <div class="modal__body">
          <slot></slot>
        </div>
      </div>
    </div>
  </transition>
</template>

<script>

export default {
  name: "ModalComponent",
  props: {
    showModal: {
      type: Boolean,
      required: false,
    },
  },

  watch: {
    showModal: function () {
      if (this.showModal) {
        window.scrollTo(0, 0);
        document.documentElement.style.overflow = "hidden";
      } else {
        document.documentElement.style.overflow = "auto";
      }
    },
  },
  methods: {
    hideModal() {
      this.$emit("hideModal", false);
    },
  },
};
</script>

<style lang="scss" scoped>
.modal {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  z-index: 98;
  transition: 0.4s ease-out;

  background-color: rgba(0, 0, 0, 0.3);
  text-align: center;
  @media (min-width: $mobile + px) {
    display: flex;
    align-items: center;
    justify-content: center;
  }
  &__container {
    position: relative;
  }

  &__body {
    position: relative;
    background: #ffffff;
    box-shadow: 2px 4px 16px rgba(0, 0, 0, 0.2);
    border-radius: 20px;
    display: flex;
    align-items: center;
    justify-content: center;
    //@media (min-width: $tablet + px) {
    //  width: 800px;
    //  height: 450px;
    //}
    //@media (max-width: $tablet + px) {
    //  margin: 0 auto;
    //  width: 70%;
    //  padding: 40px 0;
    //}
    //
    @media (max-width: $mobile + px) {
      border-radius: 0;
      height: 100vh;
    }
  }

  &__close {
    cursor: pointer;
    position: absolute !important;
    right: 30px;
    top: 30px;
    width: 30px;
    height: 30px;
    z-index: 22;
    @media (max-width: $tablet + px) {
      top: 30px;
      right: 40px;
      width: 25px;
      height: 25px;
    }
    @media (max-width: $mobileSmall + px) {
      top: 15px;
      right: 15px;
      width: 20px;
      height: 20px;
    }
  }
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
</style>
