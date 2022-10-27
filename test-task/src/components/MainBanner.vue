<template>
  <div class="main-banner">
    <div class="main-banner__container">
      <div class="main-banner__wrapper">
        <div class="main-banner__content" ref="content" >
          <div class="main-banner__group">
            <div class="main-banner__logo _img-wrapper">
              <a href=""><img src="../assets/images/logo.png" alt="Logo" title="Logo"></a>
            </div>
            <h1 class="main-banner__title">Встречайте новые яркие кварталЫ!</h1>
            <div class="main-banner__text">Здесь так же душевно и уютно, как в старом добром «Ярком», но ещё лучше,
              современнее и интереснее.
            </div>
            <button class="main-banner__btn base-button" @click="scrollToSection('apartments')">Посмотреть квартиры</button>
          </div>
          <span class="main-banner__circle main-banner__circle_green"></span>
          <span class="main-banner__circle main-banner__circle_blue"></span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  methods: {
    scrollToSection(link) {
      this.$emit("scroll", link);
    },
  }
}
</script>

<style lang="scss">
.main-banner {
  height: 100vh;
  padding: 6.3% 0 0;
  background: url("../assets/images/banner-bg.jpg") no-repeat center center fixed;
  -webkit-background-size: cover;
  -moz-background-size: cover;
  -o-background-size: cover;
  background-size: cover;
  @media (max-width: $tablet + px) {
    padding: 15% 0 0;
    height: 850px;
  }
  @media (max-width: $mobileSmall + px) {
    padding: 25% 0 0;
    height: 617px;
  }
  &__container {
    max-width: 1394px;
    box-sizing: content-box;
    padding: 0 20px;
    margin: 0 auto;
    @media (max-width: $pc + px) {
      max-width: 970px;
    }
    @media (max-width: $mobile + px) {
      max-width: none;
      padding: 0;
    }
  }

  &__wrapper {
    max-width: 664px;
    @media (max-width: $tablet + px) {
      max-width: 500px;

    }
    @media (max-width: $mobile + px) {
      position: relative;
      left: -56px;

    }
    @media (max-width: $mobileSmall + px) {
      max-width: 336px;
      position: relative;
      left: -36px;

    }
  }

  &__content {
    height: 0;
    padding-bottom: 100%;
    position: relative;
    border-radius: 50%;
    background: linear-gradient(147.64deg, #FFFFFF 13.56%, #F1F1F1 85.54%);
    display: flex;
    align-items: center;
    justify-content: center;
  }

  &__group{
    position: absolute;
    top: 15.4%;
    left: 21.4%;
    right: 19.6%;
  }

  &__circle {
    position: absolute;
    border-radius: 50%;

    &_green {
      width: 268px;
      height: 268px;
      top: -48px;
      right: -110px;
      background: linear-gradient(147.64deg, #C5D210 13.56%, #82B428 85.54%);
      @media (max-width: $tablet + px) {
        top: calc(100% - 50px);
        right: -40px;
        width: 212px;
        height: 212px;
      }
      @media (max-width: $mobileSmall + px) {
        top: calc(100% - 78px);
        right: -60px;
        width: 156px;
        height: 156px;
      }
    }

    &_blue {
      top: 220px;
      right: -185px;
      width: 105px;
      height: 105px;
      background: linear-gradient(147.64deg, #8DCEED 13.56%, #2DA3DC 85.54%);
      @media (max-width: $tablet + px) {
        top: -83px;
        right: 105px;
        width: 93.5px;
        height: 93.5px;
      }
      @media (max-width: $mobileSmall + px) {
        top: -83px;
        left: 136px;
        width: 82px;
        height: 82px;
      }
    }
  }

  &__logo {
    max-width: 242px;
    margin: 0 0 35.66px;
    @media (max-width: $tablet + px) {
      max-width: 176px;
      margin: 0 0 27.5px 0;
    }
    @media (max-width: $mobileSmall + px) {
      max-width: 109.16px;
      margin: 0 0 20px 0;
    }
  }

  &__title {
    font-weight: 800;
    font-size: 48px;
    line-height: 125%;
    text-transform: uppercase;
    color: #82B428;
    margin: 0 0 23px 0;
    @media (max-width: $tablet + px) {
      font-size: 36px;
      margin: 0 0 13.5px 0;
    }
    @media (max-width: $mobileSmall + px) {
      font-size: 24px;
      margin: 0 0 4px 0;
    }
  }

  &__text {
    font-weight: 400;
    font-size: 24px;
    line-height: 110%;
    color: #2B2422;
    margin: 0 0 21px 0;
    @media (max-width: $tablet + px) {
      font-size: 18px;
      margin: 0 0 18px 0;
    }
    @media (max-width: $mobileSmall + px) {
      font-size: 12px;
      margin: 0 0 15.54px 0;
    }
  }

  &__btn {
    padding: 0 22px;
    background: linear-gradient(34.66deg, #BC1822 16.88%, #E53322 76%);
    &.base-button{
      @media (max-width: $mobileSmall + px) {
        height: 30.42px;
        font-size: 12px;
      }
    }
    @media (max-width: $mobileSmall + px) {
      padding: 0 13px;
    }
  }
}
</style>