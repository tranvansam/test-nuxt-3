<template>
  <header class="header">
    <div class="navbar">
      <a href="#" class="logo">
        <img src="@/assets/icons/menu.svg" alt="menu" class="menu" />
        <img src="@/assets/icons/logo.svg" alt="Logo" class="logo-img" />
      </a>
      <nav>
        <img src="@/assets/icons/search.svg" alt="Logo" class="btn-seach" />
        <ul class="nav-list">
          <li class="nav-item"><a class="text" href="#">Home</a></li>
          <li class="nav-item"><a class="text" href="#">Game</a></li>
          <li class="nav-item"><a class="text" href="#">Infor</a></li>
          <li class="nav-item"><a class="text" href="#">News</a></li>
          <li class="nav-item"><a class="text" href="#">Promotions</a></li>
          <li class="nav-item"><a class="text" href="#">VIP</a></li>
        </ul>
      </nav>
    </div>
    <div class="action-buttons">
      <button class="btn btn-login">Login</button>
      <button class="btn btn-registration">Registration</button>
    </div>
  </header>
</template>

<script setup></script>

<style scoped lang="scss">
.header {
  height: 6.8rem;
  display: flex;
  align-items: center;
  justify-content: space-between;
  // Navbar Container
  > .navbar {
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 5.7rem;
    > .logo {
      display: flex;
      align-items: center;
      .logo-img {
        width: 6.8rem;
        height: 3rem;
      }
    }
    > nav {
      display: flex;
      align-items: center;
      gap: 3.2rem;
      > .btn-search {
        height: 3rem;
        width: 3rem;
      }
      > .nav-list {
        display: flex;
        align-items: center;
        gap: 2.4rem;
        .nav-item {
          > a.text {
            text-decoration: none;
            color: inherit;
            text-transform: uppercase;
            font-size: 1.4rem;
            font-weight: 500;
            line-height: 1.96px;
            &:hover {
              color: #ffdd57;
            }
          }
        }
      }

      @media (max-width: 960px) {
        display: none;
      }
    }
  }
  > .action-buttons {
    display: flex;
    gap: 0.8rem;

    .btn {
      display: flex;
      align-items: center;
      padding-left: 1.2rem;
      padding-right: 1.2rem;
      height: 3.4rem;
      font-size: 1.4rem;
      line-height: 1.54rem;
      border: none;
      border-radius: 1rem;
      cursor: pointer;
      text-transform: uppercase;

      &.btn-login {
        background-color: #12294a;
        color: #ffffff;
        &:hover {
          background-color: #ffffff;
          color: #001f3f;
        }
      }

      &.btn-registration {
        background-color: #01af70;
        color: #ffffff;

        &:hover {
          background-color: #218838;
        }
      }
    }
  }
}
</style>
