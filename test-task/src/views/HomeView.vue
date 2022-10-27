<template>
  <main class="page">
    <MainBanner @scroll="scrollTo"></MainBanner>
    <MovingInfo></MovingInfo>
    <MainAdvatages></MainAdvatages>
    <ApartmentTypes></ApartmentTypes>
    <ApartmentInfo @scroll="scrollTo"></ApartmentInfo>
    <BenefitsInfo></BenefitsInfo>
    <DiscountsInfo></DiscountsInfo>
    <MovingBanner></MovingBanner>
    <ContactPage></ContactPage>


  </main>
</template>

<script>
import MainBanner from "@/components/MainBanner";
import MainAdvatages from "@/components/MainAdvatages";
import ContactPage from "@/components/ContactPage";
import MovingInfo from "@/components/ MovingInfo";
import MovingBanner from "@/components/MovingBanner";
import DiscountsInfo from "@/components/DiscountsInfo";
import ApartmentInfo from "@/components/ApartmentInfo";
import ApartmentTypes from "@/components/ApartmentTypes";
import BenefitsInfo from "@/components/BenefitsInfo";

export default {
  components: {
    MovingInfo,
    MainAdvatages,
    ApartmentInfo,
    DiscountsInfo,
    MovingBanner,
    ContactPage,
    BenefitsInfo,
    MainBanner,
    ApartmentTypes
  },
  methods: {
    scrollTo(link) {
      const offsetTop = document.getElementById(link).offsetTop;
      document.getElementById(link).scrollIntoView({
        top: offsetTop,
        behavior: "smooth",
      });
    },
  },
}
</script>

<style lang="scss">

</style>
