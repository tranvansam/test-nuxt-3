<template>
  <div class="menu-container ct-container">
    <div v-for="(item, index) in menuItems" :key="index" class="menu-item">
      <img :src="item.icon" :alt="item.text" class="menu-icon" />
      <span class="menu-text">{{ item.text }}</span>
    </div>
  </div>
</template>

<script setup>
import search from "@/assets/icons/search.svg";
import diamond from "@/assets/icons/diamond.svg";
import vip from "@/assets/icons/vip.svg";
import hotMatch from "@/assets/icons/hot-match.svg";
import games from "@/assets/icons/games.svg";
import promotion from "@/assets/icons/promotion.svg";
import providers from "@/assets/icons/providers.svg";
import p2p from "@/assets/icons/p2p.svg";
const { isMbScreen } = defineProps({
  isMbScreen: {
    type: Boolean,
    default: false,
  },
});
const menuItems = computed(() => {
  if (isMbScreen) {
    return [
      { icon: search, text: "Search" },
      { icon: games, text: "Games" },
      { icon: providers, text: "Providers" },
    ];
  }
  return [
    { icon: diamond, text: "Diamond mine" },
    { icon: vip, text: "VIP" },
    { icon: promotion, text: "Promotion" },
    { icon: hotMatch, text: "Hot Match" },
    { icon: p2p, text: "P2P Transaction" },
    { icon: games, text: "Games" },
    { icon: providers, text: "Providers" },
  ];
});
</script>
<style scoped lang="scss">
.menu-container {
  margin-top: 40px;
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 20px; /* Khoảng cách giữa các khối */
  padding-bottom: 3rem;
  .menu-item {
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: center;
    border: 1px solid rgba(255, 255, 255, 0.1);
    border-radius: 10px; /* Bo góc */
    padding: 10px 20px; /* Khoảng cách trong khối */
    min-width: 17rem; /* Chiều rộng tối thiểu */
    height: 5.7rem; /* Chiều cao khối */
    cursor: pointer;
    transition: all 0.3s ease;

    &:hover {
      background-color: rgba(255, 255, 255, 0.1); /* Hiệu ứng hover */
      transform: scale(1.05); /* Phóng to nhẹ */
    }

    .menu-icon {
      margin-right: 1.3rem; /* Khoảng cách giữa icon và text */
    }

    .menu-text {
      color: white; /* Màu chữ */
      font-size: 1.6rem; /* Kích thước chữ */
      line-height: 22.4px;
      font-weight: 400;
      white-space: nowrap; /* Ngăn chữ bị xuống dòng */
    }
  }
  @media (max-width: 960px) {
    gap: .6rem; /* Khoảng cách giữa các khối */
    .menu-item {
      min-width: 12.2rem; /* Chiều rộng tối thiểu */
      height: 5rem; /* Chiều cao khối */
      cursor: pointer;
      transition: all 0.3s ease;

      .menu-text {
        color: white; /* Màu chữ */
        font-size: 1.4rem; /* Kích thước chữ */
        line-height: 1.4rem;
        font-weight: 400;
        white-space: nowrap; /* Ngăn chữ bị xuống dòng */
      }
    }
  }
}
</style>
