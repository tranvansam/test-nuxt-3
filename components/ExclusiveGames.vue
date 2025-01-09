<script setup lang="ts">
import { Swiper, SwiperSlide } from "swiper/vue";
import { Navigation } from "swiper/modules";
import "swiper/swiper-bundle.css";
import { computed, ref } from "vue";
import SeeAll from "~/components/SeeAll.vue";
import sHot from "@/assets/icons/hot.svg";
import sNew from "@/assets/icons/new.svg";
import xg1 from "@/assets/icons/xg1.svg";
import xg2 from "@/assets/icons/xg2.svg";
import xg3 from "@/assets/icons/xg3.svg";
import xg4 from "@/assets/icons/xg4.svg";
import xg5 from "@/assets/icons/xg5.svg";
import xg6 from "@/assets/icons/xg6.svg";
import xg8 from "@/assets/icons/xg8.svg";
import xg9 from "@/assets/icons/xg9.svg";
import xg10 from "@/assets/icons/xg10.svg";
const { isMbScreen } = defineProps({
  isMbScreen: {
    type: Boolean,
    default: false,
  },
});
const list = [
  {
    name: "100HP Gaming",
    status: "hot",
    img: xg1,
  },
  {
    name: "VeliPlay",
    status: "hot",
    img: xg2,
  },
  {
    name: "Evolution",
    status: "new",
    img: xg3,
  },
  {
    name: "VeliPlay",
    status: "new",
    img: xg4,
  },
  {
    name: "Onlyplay",
    status: "",
    img: xg5,
  },
  {
    name: "VeliPlay",
    status: "",
    img: xg6,
  },
  {
    name: "VeliPlay",
    status: "",
    img: xg8,
  },
  {
    name: "VeliPlay",
    status: "",
    img: xg9,
  },
  {
    name: "VeliPlay",
    status: "",
    img: xg10,
  },
  {
    name: "VeliPlay",
    status: "",
    img: xg9,
  },
];
// Swiper Options
const swiperOption = computed(() => {
  return {
    slidesPerView: isMbScreen ? 3 : 9,
    spaceBetween: 20,
    navigation: false,
    modules: [Navigation],
    loop: true,
  };
});
</script>

<template>
  <div class="exclusive-games ct-container">
    <SeeAll title="Exclusive Games" />
    <div class="show-game-wrap">
      <Swiper v-bind="swiperOption">
        <SwiperSlide
          v-for="(item, index) in list"
          :key="index + 'img'"
          class="image"
        >
          <div class="game-card">
            <img
              v-if="item.status === 'hot'"
              :src="sHot"
              alt="game hot"
              class="hot"
            />
            <img
              v-if="item.status === 'new'"
              :src="sNew"
              alt="game new"
              class="new"
            />
            <img :src="item?.img" alt="Game Thumbnail" class="card-image" />
            <p class="game-title">{{ item?.name }}</p>
          </div>
        </SwiperSlide>
      </Swiper>
    </div>
  </div>
</template>

<style scoped lang="scss">
.exclusive-games {
  margin-top: 3.2rem;
}
.game-card {
  position: relative;
  height: 21rem;
  width: 15.6rem;
  @media (max-width: 960px) {
    width: 12rem;
    height: 16rem;
  }
  .card-image {
    width: 100%;
    height: 100%;
    object-fit: contain;
  }
  .hot,
  .new {
    position: absolute;
    top: 1.4rem;
    left: 0;
  }
  .game-title {
    position: absolute;
    bottom: 10px;
    left: 50%;
    transform: translateX(-50%);
    font-size: 0.8rem;
    line-height: 0.8rem;
    font-weight: 500;
  }
}
@media screen and (max-width: 1200px) {
}

@media screen and (max-width: 600px) {
}
</style>
