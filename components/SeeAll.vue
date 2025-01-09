<script setup>
import seeAll from "@/assets/icons/see-all.svg";
defineProps({
  title: {
    type: String,
    required: true,
  },
  tag: {
    type: String,
    required: true,
  },
});
</script>
<template>
  <div class="see-all">
    <h3>{{ title }}</h3>
    <div class="btn">
      <p class="text">SEE ALL</p>
      <img :src="seeAll" alt="see all" />
    </div>
  </div>
</template>
<style scoped lang="scss">
.see-all {
  display: flex;
  justify-content: space-between;
  align-items: center;
  color: white;
  margin-bottom: 3.2rem;
  .btn {
    display: flex;
    align-items: center;
    gap: 8px;
    .text {
      color: white;
      font-size: 1.5rem;
      font-weight: 400;
      line-height: 2.1rem;
    }
  }
}
</style>
