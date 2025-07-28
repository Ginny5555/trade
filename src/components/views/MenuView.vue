<template>
  <div class="nav">
    <div class="nav__container">
      <div class="nav-left">
        <div class="nav__logo">LOGO</div>

        <nav class="nav__links" :class="{ 'is-open': isMenuOpen }">
          <a href="#">How it works</a>
          <a href="#">About</a>
          <a href="#">Instructions</a>
          <a href="#">Accounts</a>
          <a href="#">Platforms</a>
          <a href="#">Contact</a>
        </nav>
      </div>
      <div class="nav-right">
        <div class="nav__lang">
          <select>
            <option>EN</option>
            <option>UA</option>
          </select>
        </div>
        <CustomButton class="nav__btn"
          ><template #text>Sign in for free</template></CustomButton
        >

        <button class="nav__burger" @click="isMenuOpen = !isMenuOpen">
          <span v-if="!isMenuOpen">
            <svg
              width="24"
              height="24"
              viewBox="0 0 24 24"
              fill="none"
              xmlns="http://www.w3.org/2000/svg"
            >
              <path
                d="M20.05 11H3.95C3.42533 11 3 11.4253 3 11.95V12.05C3 12.5747 3.42533 13 3.95 13H20.05C20.5747 13 21 12.5747 21 12.05V11.95C21 11.4253 20.5747 11 20.05 11Z"
                fill="#333333"
              />
              <path
                d="M20.05 16H3.95C3.42533 16 3 16.4253 3 16.95V17.05C3 17.5747 3.42533 18 3.95 18H20.05C20.5747 18 21 17.5747 21 17.05V16.95C21 16.4253 20.5747 16 20.05 16Z"
                fill="#333333"
              />
              <path
                d="M20.05 6H3.95C3.42533 6 3 6.42533 3 6.95V7.05C3 7.57467 3.42533 8 3.95 8H20.05C20.5747 8 21 7.57467 21 7.05V6.95C21 6.42533 20.5747 6 20.05 6Z"
                fill="#333333"
              />
            </svg>
          </span>
          <span v-else>✕</span>
        </button>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";
import CustomButton from "../ui/CustomButton.vue";

const isMenuOpen = ref(false);
</script>

<style scoped lang="scss">
$grey: #333333;
$black: #000000;
.nav {
  padding: 20px 60px 20px 120px;
  display: block;
  &-left {
    display: flex;
  }
  &-right {
    display: flex;
    align-items: center;
    gap: 24px;
  }
  &__logo {
    display: block;
    font-size: 15px;
    line-height: 16px;
    font-weight: 700;
    font-family: "Museo Sans Cyrl", sans-serif;
    color: $grey;
    margin-right: 57px;
  }
  &__container {
    display: flex;
    flex-wrap: wrap;
    align-items: center;
    justify-content: space-between;
  }
  &__burger {
    display: none;
    background: none;
    border: none;
    cursor: pointer;
    padding: 6px 3px;
  }
  &__links {
    display: flex;
    flex-wrap: wrap;
    gap: 32px;
  }
  &__links a {
    display: block;
    font-family: "Museo Sans Cyrl", sans-serif;
    color: $grey;
    font-size: 15px;
    line-height: 16px;
    font-weight: 500;
    gap: 32px;
  }
  &__lang select {
    display: block;
    border: 1px solid $black;
    padding: 10px 16px;
    border-radius: 60px;
  }
  .nav__lang select {
    appearance: none;
    -webkit-appearance: none;
    -moz-appearance: none;

    padding: 12px 41px 12px 16px;
    border-radius: 60px;

    background-image: url("@/assets/arrow.svg");
    background-repeat: no-repeat;
    background-position: right 0.7rem center;
    background-size: 20px 20px;
  }

  .nav__lang select {
    font-size: 15px;
    line-height: 16px;
    font-family: "Museo Sans Cyrl", sans-serif;
    color: $grey;
  }
  &__btn {
    padding: 13px 24px;
    font-size: 14px;
    line-height: 14px;
  }
}

/* Адаптив */

@media (max-width: 1024px) {
  .nav__links,
  .nav__lang {
    display: none;
  }
  .nav {
    padding: 20px 40px;
    &__logo {
      display: none;
    }
    &__links.is-open {
      display: flex;
      flex-direction: column;
      width: 100%;
    }
    &__burger {
      display: block;
    }
    &-right {
      gap: 48px;
    }
  }
}

@media (max-width: 600px) {
  .nav {
    padding: 28px 20px;
    &__container {
      justify-content: space-between;
    }
    & .nav__btn {
      display: none;
    }
    &__logo {
      display: block;
    }
    &__burger {
      display: flex;
    }
  }
}
</style>
