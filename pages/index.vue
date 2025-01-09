<template>
  <div >
    <CarouselBanner :isMbScreen="isMbScreen" />
    <MenuGame :isMbScreen="isMbScreen" />
    <ExclusiveGames :isMbScreen="isMbScreen" />
    <AllProviders :isMbScreen="isMbScreen" />
  </div>
</template>

<script setup>
import CarouselBanner from "~/components/CarouselBanner.vue";
import MenuGame from "~/components/MenuGame.vue";
import ExclusiveGames from "~/components/ExclusiveGames.vue";
import AllProviders from "~/components/AllProviders.vue";
const screenWidth = ref(0);
const isMbScreen = computed(
  () => screenWidth.value <= 1200 && screenWidth.value > 1
);
const updateWidth = () => {
  if (typeof window !== "undefined") {
    screenWidth.value = window.innerWidth;
  }
};
onMounted(() => {
  // Update width on mount
  updateWidth();
  // Listen for resize events
  window.addEventListener("resize", updateWidth);
});
onUnmounted(() => {
  window.removeEventListener("resize", updateWidth);
});
</script>

<style scoped lang="scss">
// SCSS cho trang in
</style>
