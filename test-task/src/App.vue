<template>
  <div class="wrapper">
    <div class="content">
      <router-view/>
    </div>
    <FooterComponent></FooterComponent>
  </div>
</template>

<style lang="scss">
  .wrapper {
    display: flex;
    flex-direction: column;
    height: 100vh;
}
  .content {
    flex: 1 0 auto;
  }

  .footer {
    flex: 0 0 auto;
  }
</style>
<script>
import FooterComponent from "@/components/FooterComponent";
export default {
  components: {FooterComponent}
}
</script>
