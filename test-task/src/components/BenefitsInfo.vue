<template>
  <section class="benefits">
    <div class="benefits__container _container">
      <h1 class="benefits__title">Микрогород, прекрасный в деталях</h1>

      <div class="benefits__content">
        <div class="benefits__row" v-for="(row, index) in rows" :key="index">
          <CardComponent :class="`benefits__item-${index+1}`" :card="item" v-for="(item, index) in row" :key="index"
                         class="benefits__item"></CardComponent>
        </div>
      </div>

      <button class="benefits__btn" @click="showMore">
        <span v-if="!isOpen">Показать еще </span>
        <span v-else>Скрыть</span>
      </button>
      <swiper class="benefits__swiper" :space-between="20" :speed="600" :pagination="{clickable:true}">
        <swiper-slide v-for="(benefit, index) in benefits" :key="index">
          <CardComponent class="benefits__item" :card="benefit"></CardComponent>
        </swiper-slide>
      </swiper>
    </div>
  </section>
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
      benefits: [
        {
          title: 'Инфраструктура микрогорода',
          text: 'Двор — это там, где отдыхают люди. А парковка — где отдыхают машины. И лучше это не смешивать. Поэтому в новых кварталах парковка вынесена за пределы двора. Дети играют в безопасном зелёном дворе, машины стоят по периметру квартала под присмотром камер.',
          image: require('../assets/images/benefits/01.jpg')
        },
        {
          title: 'Видовые квартиры',
          text: 'Двор — это там, где отдыхают люди. А парковка — где отдыхают машины. И лучше это не смешивать. Поэтому в новых кварталах парковка вынесена за пределы двора. Дети играют в безопасном зелёном дворе, машины стоят по периметру квартала под присмотром камер.',
          image: require('../assets/images/benefits/02.jpg')
        },
        {
          title: 'Свой парк и набережная',
          text: 'Двор — это там, где отдыхают люди. А парковка — где отдыхают машины. И лучше это не смешивать. Поэтому в новых кварталах парковка вынесена за пределы двора. Дети играют в безопасном зелёном дворе, машины стоят по периметру квартала под присмотром камер.',
          image: require('../assets/images/benefits/03.jpg')
        },
        {
          title: 'Витражное остекление лоджий',
          text: 'Двор — это там, где отдыхают люди. А парковка — где отдыхают машины. И лучше это не смешивать. Поэтому в новых кварталах парковка вынесена за пределы двора. Дети играют в безопасном зелёном дворе, машины стоят по периметру квартала под присмотром камер.',
          image: require('../assets/images/benefits/04.jpg')
        },
        {
          title: 'Фасады, облицованные гранитом',
          text: 'Двор — это там, где отдыхают люди. А парковка — где отдыхают машины. И лучше это не смешивать. Поэтому в новых кварталах парковка вынесена за пределы двора. Дети играют в безопасном зелёном дворе, машины стоят по периметру квартала под присмотром камер.',
          image: require('../assets/images/benefits/05.jpg')
        },
        {
          title: 'Кладовые',
          text: 'Двор — это там, где отдыхают люди. А парковка — где отдыхают машины. И лучше это не смешивать. Поэтому в новых кварталах парковка вынесена за пределы двора. Дети играют в безопасном зелёном дворе, машины стоят по периметру квартала под присмотром камер.',
          image: require('../assets/images/benefits/06.jpg')
        },
        {
          title: 'Горячая вода 24/7',
          text: 'Двор — это там, где отдыхают люди. А парковка — где отдыхают машины. И лучше это не смешивать. Поэтому в новых кварталах парковка вынесена за пределы двора. Дети играют в безопасном зелёном дворе, машины стоят по периметру квартала под присмотром камер.',
          image: require('../assets/images/benefits/07.jpg')
        },
        {
          title: 'Колясочные',
          text: 'Двор — это там, где отдыхают люди. А парковка — где отдыхают машины. И лучше это не смешивать. Поэтому в новых кварталах парковка вынесена за пределы двора. Дети играют в безопасном зелёном дворе, машины стоят по периметру квартала под присмотром камер.',
          image: require('../assets/images/benefits/08.jpg')
        },
        {
          title: 'Места для ожидания в подъездах',
          text: 'Двор — это там, где отдыхают люди. А парковка — где отдыхают машины. И лучше это не смешивать. Поэтому в новых кварталах парковка вынесена за пределы двора. Дети играют в безопасном зелёном дворе, машины стоят по периметру квартала под присмотром камер.',
          image: require('../assets/images/benefits/09.jpg')
        },
        {
          title: 'Инфраструктура микрогорода',
          text: 'Двор — это там, где отдыхают люди. А парковка — где отдыхают машины. И лучше это не смешивать. Поэтому в новых кварталах парковка вынесена за пределы двора. Дети играют в безопасном зелёном дворе, машины стоят по периметру квартала под присмотром камер.',
          image: require('../assets/images/benefits/01.jpg')
        },
        {
          title: 'Видовые квартиры',
          text: 'Двор — это там, где отдыхают люди. А парковка — где отдыхают машины. И лучше это не смешивать. Поэтому в новых кварталах парковка вынесена за пределы двора. Дети играют в безопасном зелёном дворе, машины стоят по периметру квартала под присмотром камер.',
          image: require('../assets/images/benefits/02.jpg')
        },
        {
          title: 'Свой парк и набережная',
          text: 'Двор — это там, где отдыхают люди. А парковка — где отдыхают машины. И лучше это не смешивать. Поэтому в новых кварталах парковка вынесена за пределы двора. Дети играют в безопасном зелёном дворе, машины стоят по периметру квартала под присмотром камер.',
          image: require('../assets/images/benefits/03.jpg')
        },
      ],
      rows: [],
      isOpen: false,
    }
  },
  methods: {
    divideArray(number) {
      const array = this.benefits.slice(0, number);
      let size = 6; //размер подмассива
      for (let i = 0; i < Math.ceil(array.length / size); i++) {
        this.rows[i] = array.slice((i * size), (i * size) + size);
      }
    },
    showMore() {
      if (this.isOpen) {
        this.divideArray(9)
      } else this.divideArray(this.benefits.length + 1)
      this.isOpen = !this.isOpen;


    }
  },
  created() {
    +
        this.divideArray(9)
  },
}
</script>

<style lang="scss">
.benefits {
  padding: 0 0 100px 0;
  @media (max-width: $mobileSmall + px) {
    padding: 0 0 30.29px 0;
  }

  &__content {
    @media (max-width: $mobile + px) {
      display: none;
    }
  }

  &__row {
    display: flex;
    gap: 30px;
    flex-wrap: wrap;
    margin: 0 0 40px 0;
  }

  &__item {

    &-1 {
      flex: 1 1 350px;
    }

    &-2 {
      flex: 1 1 285px;
    }

    &-3 {
      flex: 1 1 415px;
    }

    &-4 {
      flex: 1 1 350px;
    }

    &-5 {
      flex: 1 1 350px;
    }

    &-6 {
      flex: 1 1 285px;
    }

    @media (max-width: $tablet + px) {
      flex: 0 1 calc(50% - 20px);
    }
  }

  &__title {
    display: none;
    @media (min-width: $mobileSmall + px) {
      max-width: 644px;
      display: block;
      font-weight: 800;
      font-size: 48px;
      line-height: 60px;
      text-align: center;
      text-transform: uppercase;
      color: #2DA3DC;
      margin: 0 auto 44px;
    }
  }

  &__btn {
    display: block;
    margin: 0 auto;
    font-weight: 800;
    font-size: 24px;
    line-height: 100%;
    color: #C5C5C5;
    @media (max-width: $mobile + px) {
      display: none;
    }
  }

  &__swiper {
    @media (min-width: $mobile + px) {
      display: none;
    }
    height: 658.71px;

    .swiper-slide {
      height: 617px;
    }

    .swiper-pagination {
      bottom: 0 !important;

      &-bullet {
        width: 8.71px;
        height: 8.71px;
        margin: 0 6.265px !important;

        &-active {
          background: #2DA3DC;
        }
      }
    }

    .card {
      border-radius: 0;

      &__content {
        @media (max-width: $mobile + px) {
          padding: 44px 29px;
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


}
</style>