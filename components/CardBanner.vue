<script setup>
defineProps({
  tag: {
    type: String,
    required: true,
  },
  tag: {
    type: String,
    required: true,
  },
  title: {
    type: String,
    required: true,
  },
  subtitle: {
    type: String,
    required: true,
  },
  buttonText: {
    type: String,
    required: true,
  },
  imageSrc: {
    type: String,
    required: true,
  },
  background: {
    type: String,
    default: `linear-gradient(to bottom, #147261, #082C25)`, // Giá trị mặc định cho button text
  },
});
</script>
<template>
  <div
    class="card-container"
    :style="{
      background,
    }"
  >
    <div class="card-content">
      <div class="card-left">
        <p class="tag">{{ tag }}</p>
        <p class="card-title">{{ title }}</p>
        <p class="card-subtitle">{{ subtitle }}</p>
        <button class="btn">{{ buttonText }}</button>
      </div>
      <div class="card-right">
        <img :src="imageSrc" alt="Piggy Christmas" class="card-image" />
      </div>
      <img :src="imageSrc" alt="Piggy Christmas" class="card-image-mb" />
    </div>
  </div>
</template>
<style scoped lang="scss">
.card-container {
  position: relative;
  width: 100%;
  height: 100%;
  border-radius: 2rem;
//   overflow: hidden;
  display: flex;
  justify-content: center;
  align-items: center;
  box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.2);
  .card-content {
    display: flex;
    justify-content: space-between;
    align-items: center;
    width: 100%;

    .card-left {
      flex: 1;
      display: flex;
      flex-direction: column;
      align-items: center;
      .tag {
        background-color: rgba(255, 255, 255, 0.2);
        color: #fff;
        font-size: 21px;
        line-height: 2.94rem;
        font-weight: 600;
        height: 4.1rem;
        display: flex;
        align-items: center;
        padding: 0px 16px;
        width: fit-content;
        border-radius: 50px;
        margin-bottom: 15px;
      }

      .card-title,
      .card-subtitle {
        font-size: 4.2rem;
        color: white;
        margin: 0;
        font-weight: 800;
        line-height: 58.8px;
      }
      .card-subtitle {
        max-width: 40rem;
      }

      .btn {
        margin-top: 15px;
        background-color: #ff0960;
        color: white;
        height: 5rem;
        width: 34rem;
        display: flex;
        align-items: center;
        justify-content: center;
        border: none;
        border-radius: 8px;
        font-size: 16px;
        font-weight: bold;
        text-transform: uppercase;
        cursor: pointer;
        transition: all 0.3s ease;
        font-weight: 600;
        font-size: 2.1rem;
        line-height: 2.1rem;
        &:hover {
          background-color: #ff567a;
        }
      }
    }

    .card-right {
      flex: 1;
      display: flex;
      justify-content: center;
      align-items: center;

      .card-image {
        max-width: 100%;
        height: auto;
        border-radius: 16px;
        object-fit: cover;
      }
    }
    .card-image-mb {
      display: none;
    }
  }
  @media (max-width: 960px) {
    .card-content {
      align-items: flex-end;
      height: 100%;
      padding-bottom: 55px;
      position: relative;
      .card-left {
        flex: 1;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: start;
        .tag {
          background-color: rgba(255, 255, 255, 0.2);
          color: #fff;
          font-size: 1.2rem;
          line-height: 1.68rem;
          font-weight: 600;
          height: 2.5rem;
          display: flex;
          align-items: center;
          padding: 0px 12px;
          width: fit-content;
          border-radius: 50px;
          margin-bottom: 15px;
        }

        .card-title,
        .card-subtitle {
          font-size: 2.4rem;
          color: white;
          margin: 0;
          font-weight: 500;
          line-height: 31.2px;
        }
        .card-subtitle {
          max-width: 40rem;
        }

        .btn {
          margin-top: 15px;
          height: 5rem;
          width: 25rem;
        }
      }
      .card-right {
        display: none;
      }
      .card-image-mb {
        display: block;
        position: absolute;
        left: 50%;
        transform: translateX(-50%);
        top: -42px;
        max-height: 200px;
      }
    }
  }
}
</style>
