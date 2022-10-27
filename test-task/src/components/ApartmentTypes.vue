<template>
  <section class="apartments" id="apartments">
    <div class="apartments__container ">
      <div class="apartments__header _container">
        <h1 class="apartments__title main-title">Квартиры для яркой жизни</h1>
      </div>
      <swiper class="apartments__swiper" :breakpoints="breakpoints" :speed="600"
              :pagination="{clickable: true}"
              :slides-per-view="'auto'">
        <swiper-slide class="apartments__slide">
          <div class="apartments__wrapper">
            <div class="apartments__img _ibg">
              <img src="../assets/images/apartments/02.jpg" alt="Apartment 1" title="Однокомнатная квартира">
            </div>
            <div class="apartments__content">
              <div class="apartments__top">
                <div class="apartments__info">
                  <div class="apartments__scheme _ibg">
                    <img src="../assets/images/apartments/schema.png" alt="Apartment schema" title="Apartment schema">
                  </div>
                  <div class="apartments__description">
                    <h2 class="apartments__type">1 комнатная квартира</h2>
                    <div class="apartments__text">Современная квартира с видом на центр города через панорамные окна. Эффективная планировка. Большая кухня-гостиная для вечеринок с друзьями.
                    </div>
                    <button class="apartments__btn green-button">Это моя квартира</button>
                  </div>
                </div>
                <div class="apartments__additional-info">
                  <div class="apartments__additional-text">
                    Доступно ещё 15 планировок!
                  </div>
                </div>
              </div>
              <div class="apartments__bottom">
                <div class="apartments__price">
                  <div class="apartments__name">Стоимость</div>
                  <div class="apartments__value">2,65 млн.Р <span>или </span><span>~ 12 000 Р/мес</span></div>
                </div>
                <div class="apartments__items">
                  <div class="apartments__item">
                    <div class="apartments__name">Площадь</div>
                    <div class="apartments__value">35 кв.м</div>
                  </div>
                  <div class="apartments__item">
                    <div class="apartments__name">Секция</div>
                    <div class="apartments__value">6</div>
                  </div>
                  <div class="apartments__item">
                    <div class="apartments__name">Этаж</div>
                    <div class="apartments__value">12</div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </swiper-slide>
        <swiper-slide class="apartments__slide">
          <div class="apartments__wrapper">
            <div class="apartments__img _ibg">
              <img src="../assets/images/apartments/01.png" alt="Apartment 1" title="Однокомнатная квартира">
            </div>
            <div class="apartments__content">
              <div class="apartments__top">
                <div class="apartments__info">
                  <div class="apartments__scheme _ibg">
                    <img src="../assets/images/apartments/schema.png" alt="Apartment schema" title="Apartment schema">
                  </div>
                  <div class="apartments__description">
                    <h2 class="apartments__type">1 комнатная квартира</h2>
                    <div class="apartments__text">Современная квартира с видом на центр города через панорамные окна. Эффективная планировка. Большая кухня-гостиная для вечеринок с друзьями.
                    </div>
                    <button class="apartments__btn green-button">Это моя квартира</button>
                  </div>
                </div>
                <div class="apartments__additional-info">
                  <div class="apartments__additional-text">
                    Доступно ещё 15 планировок!
                  </div>
                </div>
              </div>
              <div class="apartments__bottom">
                <div class="apartments__price">
                  <div class="apartments__name">Стоимость</div>
                  <div class="apartments__value">2,65 млн.Р <span>или </span><span>~ 12 000 Р/мес</span></div>
                </div>
                <div class="apartments__items">
                  <div class="apartments__item">
                    <div class="apartments__name">Площадь</div>
                    <div class="apartments__value">35 кв.м</div>
                  </div>
                  <div class="apartments__item">
                    <div class="apartments__name">Секция</div>
                    <div class="apartments__value">6</div>
                  </div>
                  <div class="apartments__item">
                    <div class="apartments__name">Этаж</div>
                    <div class="apartments__value">12</div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </swiper-slide>
      </swiper>
    </div>
  </section>
</template>

<script>
import {Swiper, SwiperSlide} from "swiper/vue";
import SwiperCore, {Pagination} from 'swiper';

SwiperCore.use([Pagination]);
export default {
  components: {Swiper, SwiperSlide},
  data() {
    return {
      breakpoints: {
        1366: {
          slidesPerView: 'auto',
          spaceBetween: 56,
        },
        767.98:{
          slidesPerView: 1,
          spaceBetween: 0,
        },
        0: {
          slidesPerView: 1,
          spaceBetween: 0,
        },
      }
    }
  }
}
</script>

<style lang="scss">
.apartments {
  padding: 0 0 100px 0;
  @media (max-width: $mobile + px) {
    padding: 0 0 80px 0;
  }
  @media (max-width: $mobileSmall + px) {
    padding: 0 0 20px 0;
  }

  &__container {
    @media (max-width: $laptop + px) {
      max-width: 1150px;
      box-sizing: content-box;
      margin: 0 auto;
    }
    @media (max-width: 1167px) {
      max-width: 1010px;
    }
    @media (max-width: $mobile + px) {
      max-width: none;
    }
  }

  &__header{
    &._container{
      @media (max-width: $mobile + px) {
        padding: 0 35px;
      }
    }
  }

  &__title {
    max-width: 343px;
    margin: 0 0 60px 0;
    color: #82B428;
    @media (max-width: $mobileSmall + px) {
      margin: 0 0 26px 0;
    }
  }

  &__swiper {
    padding: 0 0 60px 20px !important;
    @media (max-width: $laptop + px) {
      padding: 0 0 60px!important;
    }
    @media (max-width: $mobile + px) {
      padding: 0 0 30px!important;
    }
    .swiper-slide {
      height: auto;
      width: 1140px;
      @media (max-width: $laptop + px) {
        width: 100%;
        padding: 0 20px;
      }
      &:first-child {
        @media (min-width: $laptop + px) {
          margin-left: calc(50% - 565px);
        }
      }
    }

    .swiper-pagination {
      display: flex;
      align-items: center;
      justify-content: center;
      bottom: 0 !important;
      @media (max-width: $mobile + px) {
        display: none;
      }
      &-bullet {
        width: 12px;
        height: 12px;
        margin: 0 9px !important;

        &-active {
          background: #2DA3DC;
        }
      }
    }
  }

  &__wrapper {
    display: flex;
    height: 100%;
    overflow: hidden;
    background: #FFFFFF;
    box-shadow: 8px 8px 25px rgba(0, 0, 0, 0.25);
    border-radius: 20px;

    @media (max-width: $laptop + px) {
      box-shadow: 6.92192px 6.92192px 15px rgba(0, 0, 0, 0.25);
    }
  }

  &__img {
    flex: 0 0 360px;
    @media (max-width: $tablet + px) {
      flex: 0 0 220px;
    }
    @media (max-width: $mobile + px) {
      display: none;
    }
  }

  &__content {
    border: 1px solid #C5C5C5;
    border-radius: 20px;
    @media (min-width: $mobile + px) {
      padding: 70px 52px 69px 6px;
      border-left: none;
      border-bottom-left-radius: 0;
      border-top-left-radius: 0;
    }
    @media (max-width: $tablet + px) {
      padding: 70px 22px 69px 6px;
    }
    @media (max-width: $mobile + px) {
      padding: 24.23px 25px 48px;
    }
  }

  &__top {
    margin: 0 0 25px 0;
    @media (max-width: $mobile + px) {
      margin: 0 0 21px 0;
      padding: 0 0 17.42px 0;
      border-bottom: 0.43262px solid #000000;
      text-align: center;
    }
  }

  &__info {
    @media (min-width: $mobile + px) {
      display: flex;
      gap: 0 39px;
      align-items: flex-start;
    }
  }

  &__scheme {
    flex: 0 1 375px;
    padding-bottom: 39.4%;
    @media (max-width: $mobile + px) {
      //max-width: 375px;
      padding-bottom: 70%;
      margin: 0 auto 32.51px;
    }
    @media (max-width: $mobileSmall + px) {
      padding-bottom: 66.4%;
    }
  }

  &__description {
    flex: 0 1 308px;
  }

  &__type {
    font-weight: 800;
    font-size: 24px;
    line-height: 30px;
    margin: 0 0 37px 0;
    @media (max-width: $mobileSmall + px) {
      font-size: 17.6705px;
      margin: 0 0 10.54px;
    }
  }

  &__text {
    font-weight: 400;
    font-size: 17px;
    line-height: 23px;
    margin: 0 0 23px 0;
    @media (max-width: $mobileSmall + px) {
      font-size: 17.6705px;
      margin: 0 0 20.58px;
    }
  }

  &__additional-info {
    padding: 0 15px 0 24px;
    font-style: italic;
    @media (max-width: $mobile + px) {
      display: none;
    }
  }

  &__additional-text {
    font-weight: 400;
    font-size: 17px;
    line-height: 23px;
    padding: 0 0 13px 13px;
    border-bottom: 0.5px solid #000000;
  }

  &__btn {
    padding: 0 24px;
    @media (max-width: $tablet + px) {
      margin: 0 auto;
    }
    @media (max-width: $mobileSmall + px) {
      padding: 0 17px;
    }
  }

  &__bottom {
    @media (min-width: $pc + px) {
      display: flex;
      align-items: flex-start;
      justify-content: space-between;
      gap: 0 86px;
    }
    @media (min-width: $mobile + px) {
      padding: 0 13px 0 37px;
    }
  }

  &__price {
    flex: 0 0 291px;
    @media (max-width: $pc + px) {
      margin: 0 0 20px 0;
    }
  }

  &__items {
    flex: 0 1 100%;
    display: flex;
    align-items: flex-start;
    justify-content: space-between;
    @media (max-width: $laptop + px) {
      gap: 30px;
      justify-content: normal;
    }
  }

  &__name {
    font-weight: 400;
    font-size: 17px;
    line-height: 135%;
    color: #2B2422;
    margin: 0 0 2px 0;
    @media (max-width: $mobileSmall + px) {
      margin: 0 0 1px 0;
      font-size: 12.9959px;
    }

  }

  &__value {
    font-weight: 800;
    font-size: 22px;
    line-height: 127.272727%;
    color: #2B2422;
    span{
      @media (max-width: $mobile + px) {
        font-weight: 400;
      }
      &:first-child{
        @media (min-width: $mobile + px) {
          display: none;
        }
      }
    }
    @media (max-width: $mobileSmall + px) {
      font-size: 16.8203px;
    }
  }
}
</style>