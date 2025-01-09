<script setup lang="ts">
import { Swiper, SwiperSlide } from "swiper/vue";
import { Navigation } from "swiper/modules";
import "swiper/swiper-bundle.css";
import { computed, ref } from "vue";
import SeeAll from "~/components/SeeAll.vue";
import pr1 from "@/assets/icons/pr1.svg";
import pr2 from "@/assets/icons/pr2.svg";
import pr3 from "@/assets/icons/pr3.svg";
import pr4 from "@/assets/icons/pr5.svg";
import pr5 from "@/assets/icons/pr6.svg";
import pr6 from "@/assets/icons/pr7.svg";
import pr7 from "@/assets/icons/pr8.svg";
import pr8 from "@/assets/icons/pr9.svg";
const { isMbScreen } = defineProps({
  isMbScreen: {
    type: Boolean,
    default: false,
  },
});
const list = [
  {
    name: "Evolution",
    num: 10,
    img: pr1,
  },
  {
    name: "Spribe",
    num: 23,
    img: pr2,
  },
  {
    name: "VeliPlay",
    num: 33,
    img: pr3,
  },
  {
    name: "Turbo Games",
    num: 3,
    img: pr4,
  },
  {
    name: "SmartSoft",
    num: 9,
    img: pr5,
  },
  {
    name: "100HP Gaming",
    num: 12,
    img: pr6,
  },
  {
    name: "BGaming",
    num: 8,
    img: pr7,
  },
  {
    name: "Wazdan",
    num: 22,
    img: pr8,
  },
];
// Swiper Options
const swiperOption = computed(() => {
  return {
    slidesPerView: isMbScreen ? 3 : 8,
    spaceBetween: 20,
    navigation: false,
    modules: [Navigation],
    loop: true,
  };
});
</script>

<template>
  <div class="all-providers ct-container">
    <SeeAll title="All Providers" />
    <div class="provider-card-wrap">
      <Swiper v-bind="swiperOption">
        <SwiperSlide
          v-for="(item, index) in list"
          :key="index + 'img'"
          class="image"
        >
          <div class="provider-card">
            <div class="wrap-img">
              <img :src="item?.img" alt="Game Thumbnail" class="card-image" />
            </div>
            <div class="content">
              <p class="title">{{ item?.name }}</p>
              <p class="total">{{ `${item?.num || 0} games` }}</p>
            </div>
          </div>
        </SwiperSlide>
      </Swiper>
    </div>
  </div>
</template>

<style scoped lang="scss">
.all-providers {
  margin-top: 4rem;
}
.provider-card-wrap {
  padding: 0 5.4rem;
  @media (max-width: 960px) {
    padding: 0;
  }
}
.provider-card {
  min-width: 15.6rem;
  height: 12.2rem;
  border-radius: 8px;
  overflow: hidden;
  .wrap-img {
    width: 100%;
    height: 6.8rem;
    display: flex;
    align-items: center;
    justify-content: center;
    background-color: #12294a;
  }
  .content {
    background-color: rgba(245, 249, 255, 0.05);
    width: 100%;
    height: 5.4rem;
    display: flex;
    align-items: center;
    flex-direction: column;
    justify-content: center;
    .title {
      font-size: 1.3rem;
      font-weight: 400;
      line-height: 1.82rem;
      color: white;
      text-decoration: underline;
    }
    .total {
      font-size: 1.1rem;
      font-weight: 400;
      line-height: 1.1rem;
      color: #90a2bd;
      text-decoration: underline;
    }
  }
  @media (max-width: 960px) {
    min-width: 12rem;
  }
}
</style>
