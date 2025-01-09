<template>
  <div>
    <div class="ct-header">
      <Header class="ct-container" />
    </div>
    <main>
      <slot />
    </main>
    <Footer class="ct-container" />
  </div>
</template>

<script setup>
import Header from "~/components/layouts/Header.vue";
import Footer from "~/components/layouts/Footer.vue";
</script>

<style scoped lang="scss">
.ct-header {
  position: fixed;
  top: 0;
  background-color: #03193a;
  z-index: 1;
  width: 100%;
  box-shadow: 0px 9px 35px rgba(3, 25, 58, 0.4);
}
main {
  margin-top: 6.8rem;
  overflow-y: hidden;
}
</style>
