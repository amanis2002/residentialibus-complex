<template>
<section class="contact">
  <div class="contact__container _container">
    <form action="" class="contact__form">
      <div class="contact__items">
        <div class="contact__item">
          <input type="text" class="contact__input base-input" placeholder="Имя">
        </div>
        <div class="contact__item">
          <input type="text" class="contact__input base-input" placeholder="Телефон">
        </div>
      </div>
      <button class="contact__btn green-button">
        <span class="btn__text" v-if="showButtonText">Отправить</span>
        <span class="btn__text" v-else>Оставить заявку</span>
      </button>
    </form>
    <div class="contact__content">
      <h1 class="contact__title main-title">Хочу жить
        в новом квартале!</h1>
      <div class="contact__text">Оставьте свои контакты в форме и мы свяжемся с вами, поможем выбрать квартиру и расскажем, как сделать переезд ещё проще.
      </div>
    </div>
  </div>

</section>
</template>

<script>
 export default {
   data(){
     return{
       showButtonText: true,
     }
   },
   created() {
     window.addEventListener("resize", this.resizeBrowserHandler);
   },
   beforeUnmount() {
     window.removeEventListener("resize", this.resizeBrowserHandler);
   },
   methods: {
     resizeBrowserHandler (e) {
       // mobile screen
       if (e.target.innerWidth < 767.98) {
         this.showButtonText = false;
       } else {
         this.showButtonText = true;
       }
     }
   }

 }
</script>

<style lang="scss">
.contact{
  background: linear-gradient(90deg, #212121 3.84%, rgba(12, 12, 12, 0.359375) 74.98%, rgba(0, 0, 0, 0) 100%), url("../assets/images/contact-bg.jpg") no-repeat center center fixed;
  background-blend-mode: multiply;
  background-size: cover;
  padding: 87px 0 77px 0;
  @media (max-width: $mobile + px) {
    padding: 87px 33px 77px;
  }
  @media (max-width: $mobileSmall + px) {
    padding: 221px 33px 47px ;
  }
  &__container{
    @media (min-width: $mobile + px) {
      display: flex;
      align-items: flex-start;
      justify-content: space-between;
      flex-direction: row-reverse;
      gap: 0 30px;
    }
  }
  &__content{
    flex: 0 1 411px;
  }
  &__form{
    flex: 0 1 562px;
    padding: 15px 0 0;
    @media (max-width: $mobile + px) {
      padding: 0;
      margin: 0 0 41px 0;
    }
  }
  &__title{
    color: #82B428;
    margin: 0 0 32px 0;
    @media (max-width: $mobileSmall + px) {
      margin: 0 0 16px 0;
    }
  }
  &__text{
    font-weight: 400;
    font-size: 24px;
    color: #FFFFFF;
    line-height: 110%;
    @media (max-width: $mobileSmall + px) {
      max-width: 266px;
      font-size: 18px;
    }
  }
  &__items{
    margin: 0 0 23px 0;
    @media (max-width: $mobileSmall + px) {
      margin: 0 0 15px 0;
    }
  }
  &__item{
    &:not(:last-child){
      margin: 0 0 11px 0;
      @media (max-width: $mobileSmall + px) {
        margin: 0 0 10px 0;
      }
    }
  }
  &__input{
    width: 100%;
  }
  &__btn{
    padding: 0 18px;
    @media (min-width: $mobile + px) {
      margin: 0 0 0 auto;
    }
    @media (min-width: $mobileSmall + px) {
      padding: 0 83px;
    }
  }
}

</style>