<template>
  <section class="discounts">
    <div class="discounts__wrapper">
      <div class="discounts__container _container">
        <h1 class="discounts__title main-title">Скидки для своих</h1>
        <div class="discounts__text main-text">
          Мы с вами давно знаем друг друга. А для друзей у нас всегда найдётся скидка! Для всех жителей Яркого,
          переезжающих в новые кварталы — скидка на квартиры 3%!
        </div>
        <button class="discounts__btn green-button" @click="showModal=true">Оставить заявку</button>
      </div>
    </div>
    <ModalComponent :showModal="showModal" @hideModal="showModal = false">
      <div class="contact-modal">
        <h2 class="contact-modal__title main-title">Оставить заявку</h2>
        <form action="" class="contact-modal__form">
          <div class="contact-modal__items">
            <div class="contact-modal__item">
              <input type="text" placeholder="Имя" class="contact-modal__input base-input">
            </div>
            <div class="contact-modal__item">
              <input type="text" placeholder="Телефон" class="contact-modal__input base-input">
            </div>
          </div>
          <div class="contact-modal__accept">
            <input type="checkbox" id="accept" class="contact-modal__checkbox">
            <label for="accept" class="contact-modal__text">Я согласен(-на) на <span>обработку персональных данных</span>
            </label>
          </div>
          <button class="contact-modal__btn blue-button">Отправить</button>
        </form>
      </div>
    </ModalComponent>
  </section>
</template>

<script>
import ModalComponent from "@/components/ModalComponent";

export default {
  components: {ModalComponent},
  data() {
    return {
      showModal: false,
    }
  }
}
</script>

<style lang="scss">
.discounts {
  padding: 0 0 100px 0;
  @media (max-width: $mobileSmall + px) {
    padding: 0 0 44px 0;
  }

  &__wrapper {
    background: url("../assets/images/discounts.jpg") no-repeat;
    background-size: cover;
    padding: 62px 0 69px 0;
    @media (max-width: $mobile + px) {
      padding: 62px 31px 69px;
    }
    @media (max-width: $mobileSmall + px) {
      padding: 39px 31px 314px;
      background: url("../assets/images/discounts-vertical.jpg") bottom no-repeat;
      background-size: cover;
    }
  }

  &__title {
    max-width: 387px;
    color: #2DA3DC;
    margin: 0 0 27px 0;
    @media (max-width: $mobileSmall + px) {
      max-width: 256px;
      margin: 0 0 19px 0;
    }
  }

  &__text {
    max-width: 442px;
    margin: 0 0 39px 0;
    @media (max-width: $mobileSmall + px) {
      max-width: 253px;
      margin: 0 0 24px 0;
    }
  }

  &__btn {
    padding: 0 22px;
    @media (max-width: $mobileSmall + px) {
      padding: 0 15px;
    }
  }
}

.contact-modal{
  padding: 81px 77px 58px;
  @media (max-width: $tablet + px) {
    padding: 50px 45px 35px;
  }
  @media (max-width: $mobileSmall + px) {
    padding: 50px 20px 35px;
  }
  &__title{
    color: #2DA3DC;
    margin: 0 0 39px 0;
    @media (max-width: $mobileSmall + px) {
      margin: 0 0 20px 0;
    }
  }
  &__items{
    margin: 0 0 22px 0;
  }
  &__item{
    max-width: 562px;
    &:not(:last-child){
      margin: 0 0 11px 0;
    }
  }
  &__input{
    width: 100%;
  }
  &__accept{
    padding: 0 20px;
    margin: 0 0 31px 0;
    display: flex;

    gap: 0 9px;
  }
  &__btn{
    width: 275px;
    margin: 0 0 0 auto;
    @media (max-width: $mobileSmall + px) {
      margin: 0 auto;
    }
  }
  &__checkbox{
    min-height: 20px;
    min-width: 20px;
    width: 20px;
    height: 20px;
  }
  &__checkbox{
    cursor: pointer;
    border: 1px solid #C4C4C4;
    box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.15);
    border-radius: 5px;
    appearance: none;
    -webkit-appearance: none;
    display: flex;
    align-items: center;
    justify-content: center;
    &:after{
      display: none;
      content: '';
      width: 12px;
      height: 9px;
      background: url("../assets/icons/check.svg");
      background-size: cover;
    }
    &:checked{
      background: #2B2422;
      &:after{
        display: block;
      }
    }
  }
  &__text{
    max-width: 500px;
    font-weight: 400;
    font-size: 19px;
    line-height: 120%;
    color: #2B2422;
    text-align: left;
    span{
      cursor: pointer;
      color: #30A3DD;
      text-decoration: underline;
    }
  }
}
</style>