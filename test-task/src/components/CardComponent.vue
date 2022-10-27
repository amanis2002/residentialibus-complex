<template>
  <div class="card" :style="{ backgroundImage: 'url(' + card.image + ')'}" :class="{'hover-effect': card.text}">
    <div class="card__content">
      <div class="card__name base-text">
        {{ card.title }}
      </div>
        <div class="card__text" v-if="card.text">
          {{ card.text }}
        </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    card: {
      type: Object,
      required: true
    }
  },
}
</script>

<style lang="scss">
.card {
  cursor: pointer;
  position: relative;
  height: 280px;
  overflow: hidden;
  background: no-repeat center center;
  background-size: cover;
  border-radius: 10px;
  @media (max-width: $mobile + px) {
    height: 100%;
  }

  &.hover-effect {
    .card__content {
      background: linear-gradient(180deg, rgba(0, 0, 0, 0) 0%, #000000 100%);
    }

    &:hover {
      .card__content {
        justify-content: flex-start;
        background: linear-gradient(180deg, rgba(0, 0, 0, 0.87) 0%, rgba(0, 0, 0, 0.87) 100%);
        height: 100%;
      }
      .card__text {
        display: block;
        opacity: 1;
      }
    }
  }

  &__content {
    display: flex;
    flex-direction: column;
    justify-content: flex-end;
    position: absolute;
    bottom: 0;
    left: 0;
    right: 0;
    height: 148px;
    transition: all 0.45s ease 0s;
    padding: 25px 25px 32px 28px;
    z-index: 3;
    background: linear-gradient(180deg, rgba(100, 104, 101, 0) 16.67%, #646865 100%);
    background-blend-mode: multiply;
    @media (max-width: $mobileSmall + px) {
      height: 154px;
      padding: 40px 20px 20px;
    }
  }

  &__text {
    display: none;
    transition: opacity 0.3s ease 0s;
    opacity: 0;
    font-weight: 500;
    font-size: 15px;
    line-height: 100%;
    color: #FFFFFF;
    margin: 23px 0 0 0;
  }
}

</style>