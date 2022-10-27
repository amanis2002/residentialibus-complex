<template>
  <section class="moving-info">
    <div class="moving-info__container _container">
      <div class="moving-info__content">
        <h1 class="moving-info__title main-title">Из «Яркого» в новый «Яркий»!</h1>
        <div class="moving-info__text main-text">
          <p>Расширяйтесь, не покидая наш уютный микрогород. Переезжайте в новые кварталы «Яркого»!</p>
          <p>Это удобно: детям не нужно менять школу и садик, вам — менять свои привычки. Старые друзья остаются с вами, а центр Уфы по-прежнему рядом.</p>
        </div>
      </div>
      <div class="moving-info__img _ibg">
        <img src="../assets/images/info/01.jpg" alt="City picture" title="City picture">
      </div>
    </div>
  </section>
</template>

<script>
export default {
}
</script>

<style lang="scss">
.moving-info{
  padding: 120px 0 87px 0;
  @media (max-width: $mobile + px) {
    padding: 120px 33px 87px;
  }
  @media (max-width: $mobileSmall + px) {
    padding: 44px 33px 47px;
  }
  &__container{
    @media (min-width: $tablet + px) {
      display: flex;
      gap: 0 40px;
      align-items: center;
      justify-content: space-between;
    }
  }
  &__content{
    flex: 0 1 415px;
    @media (max-width: $tablet + px) {
      margin: 0 0 35px 0;
    }
  }
  &__title{
    max-width: 387px;
    margin: 0 0 40px 0;
    color: #82B428;
    @media (max-width: $mobileSmall + px) {
      margin: 0 0 18px 0;
    }
  }
  &__text{

    p{
      &:not(:last-child){
        margin: 0 0 40px 0;
        @media (max-width: $mobileSmall + px) {
          margin: 0 0 20px 0;
        }
      }
    }
  }
  &__img{
    flex: 0 1 635px;
    height: 0;
    padding-bottom: 35.3%;
    border-radius: 10px;
    overflow: hidden;
    @media (max-width: $mobile + px) {
      padding-bottom: 60.6%;
    }
  }
}
</style>