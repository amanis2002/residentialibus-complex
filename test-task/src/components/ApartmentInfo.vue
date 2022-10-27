<template>
  <div class="apartment-info">
    <div class="apartment-info__container _container">
      <div class="apartment-info__characteristics">
        <div class="apartment-info__items">
          <CardComponent class="apartment-info__item" :card="item" v-for="(item, index) in characteristics"
                         :key="index"></CardComponent>
        </div>
        <swiper class="apartment-info__swiper" :space-between="20" :speed="600" :pagination="{clicable: true}">
          <swiper-slide v-for="(item, index) in characteristics" :key="index">
            <CardComponent class="apartment-info__item" :card="item"></CardComponent>
          </swiper-slide>
        </swiper>
      </div>
      <div class="apartment-info__banner">
        <div class="apartment-info__content">
          <h1 class="apartment-info__title">Квартиры с чистовой отделкой</h1>
          <button class="apartment-info__btn green-button" @click="scrollToSection('apartments')">Посмотреть квартиры</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import CardComponent from "@/components/CardComponent";
import {Swiper, SwiperSlide} from "swiper/vue";
import SwiperCore, {Pagination} from 'swiper';

SwiperCore.use([Pagination]);
export default {
  components: {CardComponent, Swiper, SwiperSlide},
  data() {
    return {
      characteristics: [
        {title: 'Эффективные планировки', image: require('../assets/images/characteristics/01.png')},
        {title: 'Высокие потолки', image: require('../assets/images/characteristics/02.jpg')},
        {title: 'Двухкамерные стеклопакеты', image: require('../assets/images/characteristics/03.jpg')},
      ],
    }
  },
  methods: {
    scrollToSection(link) {
      this.$emit("scroll", link);
    },
  }
}
</script>

<style lang="scss">
.apartment-info {
  padding: 0 0 100px 0;
  @media (max-width: $mobile + px) {
    padding: 0 22px 100px;
  }
  @media (max-width: $mobileSmall + px) {
    padding: 0 22px 65px;
  }

  &__characteristics {
    margin: 0 0 21px 0;
    @media (max-width: $mobileSmall + px) {
      margin: 0 0 27px 0;
    }
  }

  &__swiper {
    @media (min-width: $mobile + px) {
      display: none;
    }
    filter: drop-shadow(8px 8px 15px rgba(0, 0, 0, 0.12));
    border-radius: 20px;
    height: 660px;

    .swiper-slide {
      height: 618px
    }

    .swiper-pagination {
      display: flex;
      align-items: center;
      justify-content: center;
      bottom: 0;

      &-bullet {
        margin: 0 5.92px !important;
        width: 7.73px;
        height: 7.73px;
        background: #C4C4C4;

        &-active {
          width: 10.16px;
          height: 10.16px;
          background: #2DA3DC;
        }
      }
    }
  }

  &__items {
    display: flex;
    flex-wrap: wrap;
    gap: 30px;
    @media (max-width: $mobile + px) {
      display: none;
    }
  }

  &__item {
    flex: 0 1 calc(33.3333% - 20px);
    .card {
      &__content {
        @media (max-width: $mobile + px) {
          padding: 51px 29px;
          align-items: center;
          text-align: center;
        }
      }

      &__name {
        @media (max-width: $mobile + px) {
          font-weight: 800;
          font-size: 24px;
          line-height: 97.8%;
        }
      }
    }
  }

  &__banner {
    height: 350px;
    position: relative;
    background: url("../assets/images/apartment-bg.jpg") no-repeat;
    background-size: cover;
    @media (max-width: $mobile + px) {
      filter: drop-shadow(8px 8px 15px rgba(0, 0, 0, 0.12));
      border-radius: 20px;
      height: 613px;
      background: url("../assets/images/apartment-mobile.jpg") no-repeat 45%;
      background-size: cover;
    }
  }

  &__content {
    max-width: 284px;
    @media (min-width: $mobile + px) {
      position: absolute;
      top: 99px;
      right: 45px;
    }
    @media (max-width: $mobile + px) {
      margin: 0 auto;
      padding: 57px 0 27px 0;
      display: flex;
      justify-content: space-between;
      flex-direction: column;
      height: 100%;
    }
  }

  &__title {
    font-weight: 800;
    font-size: 36px;
    line-height: 45px;
    text-transform: uppercase;
    color: #646865;
    margin: 0 0 30px 0;
    @media (max-width: $mobile + px) {
      text-align: center;
    }
  }

  &__btn {
    padding: 0 14px;
    @media (max-width: $mobileSmall + px) {
      margin: 0 auto;
      height: 51px !important;
      padding: 0 22px;
    }
  }
}
</style>