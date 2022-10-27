<template>
  <section class="moving-banner">
    <div class="moving-banner__container" ref="container">
      <div class="moving-banner__content">
        <h1 class="moving-banner__title main-title">Просто переезжайте</h1>
        <div class="moving-banner__text main-text" ref="text-content">
          <p>Переехать в новый квартал проще, чем вы думаете. Выбираете квартиру, оформляете ипотеку и делаете первый
            взнос.</p>
          <p ref="text-paragraph">Мы в это время по программе «Трейд-ин» находим покупателя на вашу старую квартиру. Деньгами от продажи
            гасите ипотеку, и вот вы уже житель нового квартала «Яркого». Поздравляем!</p>
        </div>
      </div>
      <div class="moving-banner__img _ibg" ref="image" >
        <img src="../assets/images/info/02.jpg" alt="City picture" title="City picture">
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      windowWidth: 0
    }
  },
  mounted() {
    window.addEventListener('resize', this.handleResize);
    this.handleResize();
  },
  beforeUnmount() {
    window.removeEventListener('resize', this.handleResize);
  },
  methods: {
    handleResize() {
      this.windowWidth = window.innerWidth;
      this.moveElement()
    },
    moveElement(){
      const textContent = this.$refs["text-content"];
      const textParagraph = this.$refs["text-paragraph"];
      const img = this.$refs["image"]
      const container = this.$refs["container"]
      if(window.innerWidth <= 991.98){
        textContent.insertBefore(img, textParagraph)
      }
      else container.append(img)
    }
  },
}
</script>

<style lang="scss">
.moving-banner {
  padding: 0 0 100px 0;
  @media (max-width: $mobileSmall + px) {
    padding: 0 0 42px 0;
  }
  &__container {
    max-width: 1110px;
    box-sizing: content-box;
    padding: 0 20px;
    margin: 0 auto;

    @media (max-width: $pc + px) {
      max-width: 970px;
    }
    @media (min-width: $tablet + px) {
      display: flex;
      gap: 0 40px;
      align-items: center;
      justify-content: space-between;
    }
    @media (max-width: $tablet + px) {
      max-width: none;
      padding: 0;
    }
  }

  &__content {
    flex: 0 1 415px;
  }

  &__title {
    margin: 0 0 40px 0;
    color: #2DA3DC;
    @media (max-width: $tablet + px) {
      padding: 0 20px;
    }
    @media (max-width: $mobileSmall + px) {
      margin: 0 0 7px 0;
      padding: 0 31px;
    }
  }

  &__text {
    p {
      @media (max-width: $tablet + px) {
        padding: 0 20px;
      }
      @media (max-width: $mobileSmall + px) {
        padding: 0 31px;
      }
    }
  }

  &__img {
    flex: 0 1 627px;
    height: 0;
    padding-bottom: 40.5%;
    @media (max-width: $tablet + px) {
      margin: 19px 0 26px 0;
    }
    @media (max-width: $mobileSmall + px) {
      padding-bottom: 67%;
    }
  }
}
</style>