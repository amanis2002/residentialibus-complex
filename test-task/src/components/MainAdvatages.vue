<template>
  <section class="advantages">
    <div class="advantages__container _container">
      <h1 class="advantages__title main-title">Всё стало ещё лучше</h1>
      <div class="advantages__content">
        <div class="advantages__items">
           <CardComponent class="advantages__item" :card="advantage" v-for="(advantage, index) in advantages" :key="index" />
        </div>
        <swiper class="advantages__swiper" :space-between="20" :speed="600" :pagination="{clickable: true}">
          <swiper-slide v-for="(item, index) in advantages" :key="index">
            <CardComponent class="advantages__item" :card="item"></CardComponent>
          </swiper-slide>
        </swiper>
      </div>
    </div>
  </section>
</template>

<script>
import CardComponent from "@/components/CardComponent";
import {Swiper, SwiperSlide} from "swiper/vue";
import SwiperCore, {Pagination} from 'swiper';
SwiperCore.use([Pagination]);
export default {
  components: {Swiper, SwiperSlide, CardComponent},
  data(){
  return{
    advantages: [
      { title: 'Безопасные дворы без машин', text: 'Двор — это там, где отдыхают люди. А парковка — где отдыхают машины. И лучше это не смешивать. Поэтому в новых кварталах парковка вынесена за пределы двора. Дети играют в безопасном зелёном дворе, машины стоят по периметру квартала под присмотром камер.', image: require('@/assets/images/advantages/01.jpg')},
      { title: 'Трёхуровневое озеленение и двор, цветущий круглый год', text: 'Новые дворы «Яркого» — это настоящие парки. Растения здесь подобраны так, чтобы двор цвёл круглый год. А трёхуровневое озеленение защищает от ветра и солнца.', image: require('../assets/images/advantages/02.jpg')},
      { title: 'Игровые пространства для разного возраста', text: 'В новых дворах уникальные игровые пространства разделены по возрастам. Малыши играют с малышами, дети постарше со своими сверстниками. Безопасно, весело и никто никому не мешает.', image: require('../assets/images/advantages/03.jpg')},
      { title: 'Зоны отдыха во дворах-парках', text: 'Для нас дом — это место силы, где можно отдохнуть от работы, выдохнуть и подпитаться энергией. И гораздо приятнее делать это среди зелени в уютном пространстве двора-парка. Выходите на улицу, общайтесь с друзьями и наслаждайтесь жизнью.', image: require('../assets/images/advantages/04.jpg')},
      { title: 'Дизайнерские подъезды', text:'Просторные дизайнерские лобби с диванами, библиотеками и входом на уровне пола', image: require('../assets/images/advantages/05.jpg')},
      { title: 'Спорт прямо во дворе', text: 'На спорт всегда найдётся время, если им можно заниматься прямо во дворе. Поэтому в новых кварталах спроектировано 3 километра велодорожек с современным покрытием и 7 игровых зон. \n' +
            'Вышел из дома и уже на спорте!', image: require('../assets/images/advantages/06.jpg')},
    ]
  }
}
}
</script>

<style lang="scss">
.advantages{
  padding: 0 0 110px 0;
  @media (max-width: $mobile + px) {
    padding: 0 35px 110px;
  }
  @media (max-width: $mobileSmall + px) {
    padding: 0 35px 56.29px;
  }
  &__title{
    color: #2DA3DC;
    margin: 0 0 50px 0;
    @media (max-width: $mobileSmall + px) {
      max-width: 256px;
      color: #82B428;
      margin: 0 0 39px 0;
    }
  }
  &__items{
    display: flex;
    gap: 30px;
    flex-wrap: wrap;
    @media (max-width: $mobile + px) {
      display: none;
    }
  }
  &__swiper{
    height: 502.71px;
    .swiper-slide{
      height: 468px;
    }
    .swiper-pagination{
      bottom: 0!important;
      &-bullet{
        width: 8.71px;
        height: 8.71px;
        margin: 0 6.265px!important;
        &-active{
          background: #2DA3DC;
        }
      }
    }
    @media (min-width: $mobile + px) {
      display: none;
    }
  }
  &__item{
    flex: 0 1 calc(33.333% - 20px);
    @media (max-width: $tablet + px) {
      flex: 0 1 calc(50% - 15px);
    }
  }
}
</style>