<template>
  <section class="testimonial-slider container">
    <div class="testimonial-slider__top">
      <CustomHeading class="full-deskop">
        People love Big
        <span class="custom-heading__highlight-full full-desktop">Invest</span>
      </CustomHeading>
      <CustomHeading class="full-mobile">
        People love
        <span class="custom-heading__highlight-full full-mobile"
          >Big Invest</span
        >
      </CustomHeading>
      <div class="testimonial-slider__nav testimonial-slider__nav-desktop">
        <button @click="prevSlide" class="testimonial-slider__btn">
          <svg
            width="24"
            height="24"
            viewBox="0 0 24 24"
            fill="none"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              d="M14.1587 7.17621C14.3133 7.02005 14.4 6.80917 14.4 6.58941C14.4 6.36965 14.3133 6.15877 14.1587 6.00261C14.0827 5.92551 13.9922 5.86428 13.8924 5.82249C13.7926 5.7807 13.6855 5.75918 13.5773 5.75918C13.4691 5.75918 13.3619 5.7807 13.2621 5.82249C13.1623 5.86428 13.0718 5.92551 12.9959 6.00261L8.39986 10.6922C8.24546 10.8487 8.15888 11.0598 8.15888 11.2796C8.15888 11.4995 8.24546 11.7105 8.39986 11.867L12.9959 16.5566C13.0718 16.6337 13.1623 16.6949 13.2621 16.7367C13.3619 16.7785 13.4691 16.8 13.5773 16.8C13.6855 16.8 13.7926 16.7785 13.8924 16.7367C13.9922 16.6949 14.0827 16.6337 14.1587 16.5566C14.3133 16.4005 14.4 16.1896 14.4 15.9698C14.4 15.7501 14.3133 15.5392 14.1587 15.383L10.3895 11.2778L14.1587 7.17621Z"
              fill="black"
            />
          </svg>
        </button>
        <button @click="nextSlide" class="testimonial-slider__btn">
          <svg
            width="24"
            height="24"
            viewBox="0 0 24 24"
            fill="none"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              d="M9.84134 7.17621C9.68671 7.02005 9.59998 6.80917 9.59998 6.58941C9.59998 6.36965 9.68671 6.15877 9.84134 6.00261C9.91726 5.92551 10.0078 5.86428 10.1076 5.82249C10.2074 5.7807 10.3145 5.75918 10.4227 5.75918C10.5309 5.75918 10.6381 5.7807 10.7379 5.82249C10.8377 5.86428 10.9282 5.92551 11.0041 6.00261L15.6001 10.6922C15.7545 10.8487 15.8411 11.0598 15.8411 11.2796C15.8411 11.4995 15.7545 11.7105 15.6001 11.867L11.0041 16.5566C10.9282 16.6337 10.8377 16.6949 10.7379 16.7367C10.6381 16.7785 10.5309 16.8 10.4227 16.8C10.3145 16.8 10.2074 16.7785 10.1076 16.7367C10.0078 16.6949 9.91726 16.6337 9.84134 16.5566C9.68671 16.4005 9.59998 16.1896 9.59998 15.9698C9.59998 15.7501 9.68671 15.5392 9.84134 15.383L13.6105 11.2778L9.84134 7.17621Z"
              fill="black"
            />
          </svg>
        </button>
      </div>
    </div>

    <div class="testimonial-slider__layout">
      <button
        @click="prevSlide"
        class="testimonial-slider__btn testimonial-slider__btn-tablet testimonial-slider__btn-left"
      >
        <svg
          width="24"
          height="24"
          viewBox="0 0 24 24"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            d="M14.1587 7.17621C14.3133 7.02005 14.4 6.80917 14.4 6.58941C14.4 6.36965 14.3133 6.15877 14.1587 6.00261C14.0827 5.92551 13.9922 5.86428 13.8924 5.82249C13.7926 5.7807 13.6855 5.75918 13.5773 5.75918C13.4691 5.75918 13.3619 5.7807 13.2621 5.82249C13.1623 5.86428 13.0718 5.92551 12.9959 6.00261L8.39986 10.6922C8.24546 10.8487 8.15888 11.0598 8.15888 11.2796C8.15888 11.4995 8.24546 11.7105 8.39986 11.867L12.9959 16.5566C13.0718 16.6337 13.1623 16.6949 13.2621 16.7367C13.3619 16.7785 13.4691 16.8 13.5773 16.8C13.6855 16.8 13.7926 16.7785 13.8924 16.7367C13.9922 16.6949 14.0827 16.6337 14.1587 16.5566C14.3133 16.4005 14.4 16.1896 14.4 15.9698C14.4 15.7501 14.3133 15.5392 14.1587 15.383L10.3895 11.2778L14.1587 7.17621Z"
            fill="black"
          />
        </svg>
      </button>
      <transition name="fade-slide" mode="out-in">
        <div
          class="testimonial-slider__slide"
          @touchstart="startSwipe"
          @touchend="endSwipe"
          :key="currentIndex"
        >
          <div class="testimonial-slider__slide-inner">
            <div
              class="testimonial-slider__quote testimonial-slider__quote-desktop"
            >
              <img src="@/assets/quote.svg" alt="quote" />
            </div>

            <div class="testimonial-slider__content">
              <div class="testimonial-slider__author">
                <img
                  class="testimonial-slider__avatar"
                  :src="currentSlide.avatar"
                  alt="avatar"
                />
                <div class="testimonial-slider__info">
                  <p class="testimonial-slider__name">
                    {{ currentSlide.name }}
                  </p>
                  <p class="testimonial-slider__role">
                    {{ currentSlide.role }}
                  </p>

                  <div
                    class="testimonial-slider__quote testimonial-slider__quote-mobile"
                  >
                    <img src="@/assets/quote.svg" alt="quote" />
                  </div>
                </div>
              </div>

              <span class="testimonial-slider__text">{{
                currentSlide.text
              }}</span>
              <p class="testimonial-slider__count">
                0{{ currentIndex + 1 }} / 0{{ slides.length }}
              </p>
            </div>
          </div>
        </div>
      </transition>
      <div class="testimonial-slider__nav testimonial-slider__nav-mobile">
        <button @click="prevSlide" class="testimonial-slider__btn">
          <svg
            width="24"
            height="24"
            viewBox="0 0 24 24"
            fill="none"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              d="M14.1587 7.17621C14.3133 7.02005 14.4 6.80917 14.4 6.58941C14.4 6.36965 14.3133 6.15877 14.1587 6.00261C14.0827 5.92551 13.9922 5.86428 13.8924 5.82249C13.7926 5.7807 13.6855 5.75918 13.5773 5.75918C13.4691 5.75918 13.3619 5.7807 13.2621 5.82249C13.1623 5.86428 13.0718 5.92551 12.9959 6.00261L8.39986 10.6922C8.24546 10.8487 8.15888 11.0598 8.15888 11.2796C8.15888 11.4995 8.24546 11.7105 8.39986 11.867L12.9959 16.5566C13.0718 16.6337 13.1623 16.6949 13.2621 16.7367C13.3619 16.7785 13.4691 16.8 13.5773 16.8C13.6855 16.8 13.7926 16.7785 13.8924 16.7367C13.9922 16.6949 14.0827 16.6337 14.1587 16.5566C14.3133 16.4005 14.4 16.1896 14.4 15.9698C14.4 15.7501 14.3133 15.5392 14.1587 15.383L10.3895 11.2778L14.1587 7.17621Z"
              fill="black"
            />
          </svg>
        </button>
        <p class="testimonial-slider__count">
          0{{ currentIndex + 1 }} / 0{{ slides.length }}
        </p>
        <button @click="nextSlide" class="testimonial-slider__btn">
          <svg
            width="24"
            height="24"
            viewBox="0 0 24 24"
            fill="none"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              d="M9.84134 7.17621C9.68671 7.02005 9.59998 6.80917 9.59998 6.58941C9.59998 6.36965 9.68671 6.15877 9.84134 6.00261C9.91726 5.92551 10.0078 5.86428 10.1076 5.82249C10.2074 5.7807 10.3145 5.75918 10.4227 5.75918C10.5309 5.75918 10.6381 5.7807 10.7379 5.82249C10.8377 5.86428 10.9282 5.92551 11.0041 6.00261L15.6001 10.6922C15.7545 10.8487 15.8411 11.0598 15.8411 11.2796C15.8411 11.4995 15.7545 11.7105 15.6001 11.867L11.0041 16.5566C10.9282 16.6337 10.8377 16.6949 10.7379 16.7367C10.6381 16.7785 10.5309 16.8 10.4227 16.8C10.3145 16.8 10.2074 16.7785 10.1076 16.7367C10.0078 16.6949 9.91726 16.6337 9.84134 16.5566C9.68671 16.4005 9.59998 16.1896 9.59998 15.9698C9.59998 15.7501 9.68671 15.5392 9.84134 15.383L13.6105 11.2778L9.84134 7.17621Z"
              fill="black"
            />
          </svg>
        </button>
      </div>
      <div class="testimonial-slider__mobile-controls">
        <button
          @click="nextSlide"
          class="testimonial-slider__btn testimonial-slider__btn-tablet testimonial-slider__btn-right"
        >
          <svg
            width="24"
            height="24"
            viewBox="0 0 24 24"
            fill="none"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              d="M9.84134 7.17621C9.68671 7.02005 9.59998 6.80917 9.59998 6.58941C9.59998 6.36965 9.68671 6.15877 9.84134 6.00261C9.91726 5.92551 10.0078 5.86428 10.1076 5.82249C10.2074 5.7807 10.3145 5.75918 10.4227 5.75918C10.5309 5.75918 10.6381 5.7807 10.7379 5.82249C10.8377 5.86428 10.9282 5.92551 11.0041 6.00261L15.6001 10.6922C15.7545 10.8487 15.8411 11.0598 15.8411 11.2796C15.8411 11.4995 15.7545 11.7105 15.6001 11.867L11.0041 16.5566C10.9282 16.6337 10.8377 16.6949 10.7379 16.7367C10.6381 16.7785 10.5309 16.8 10.4227 16.8C10.3145 16.8 10.2074 16.7785 10.1076 16.7367C10.0078 16.6949 9.91726 16.6337 9.84134 16.5566C9.68671 16.4005 9.59998 16.1896 9.59998 15.9698C9.59998 15.7501 9.68671 15.5392 9.84134 15.383L13.6105 11.2778L9.84134 7.17621Z"
              fill="black"
            />
          </svg>
        </button>
      </div>
    </div>
  </section>
</template>


<script setup>
import { ref, computed } from "vue";
import avatar1 from "@/assets/Avatar1.png";
import CustomHeading from "@/components/ui/CustomHeading.vue";
const slides = ref([
  {
    name: "Albert Abello",
    role: "Director of Growth",
    avatar: avatar1,
    text: "This magical product actually works! It has radically changed the way we build our audiences. Increasing new customer sales by 6x in our most mature market.",
  },
  {
    name: "Jane Smith",
    role: "Director of Growth",
    avatar: avatar1,
    text: "This magical product actually works! It has radically changed the way we build our audiences. Increasing new customer sales by 6x in our most mature market.",
  },
  {
    name: "Albert Abello",
    role: "Director of Growth",
    avatar: avatar1,
    text: "This magical product actually works! It has radically changed the way we build our audiences. Increasing new customer sales by 6x in our most mature market.",
  },
  {
    name: "Jane Smith",
    role: "Director of Growth",
    avatar: avatar1,
    text: "This magical product actually works! It has radically changed the way we build our audiences. Increasing new customer sales by 6x in our most mature market.",
  },
]);

const currentIndex = ref(0);
const currentSlide = computed(() => slides.value[currentIndex.value]);

function nextSlide() {
  currentIndex.value = (currentIndex.value + 1) % slides.value.length;
}
function prevSlide() {
  currentIndex.value =
    (currentIndex.value - 1 + slides.value.length) % slides.value.length;
}

let touchStartX = 0;
function startSwipe(e) {
  touchStartX = e.changedTouches[0].clientX;
}
function endSwipe(e) {
  const touchEndX = e.changedTouches[0].clientX;
  const delta = touchStartX - touchEndX;
  if (delta > 50) nextSlide();
  else if (delta < -50) prevSlide();
}
</script>

<style scoped lang="scss">
@import "@/assets/styles/style.scss";
.custom-heading__highlight-full {
  width: 355px;
  display: block;
  margin-bottom: 39px;
  height: 72px;
}
.testimonial-slider {
  justify-content: space-between;
  display: flex;
  .full-deskop {
    display: block;
  }
  .full-mobile {
    display: none;
  }
  &__top {
    margin-bottom: 24px;
    & .testimonial-slider__title {
      font-size: 32px;
      font-weight: bold;

      span {
        background-color: #f1edff;
        color: #000;
      }
    }

    & .testimonial-slider__nav-desktop {
      display: flex;
      gap: 10px;
    }
  }

  &__layout {
    display: flex;
    align-items: center;
    justify-content: space-between;
    position: relative;
  }

  &__btn {
    background: transparent;
    width: 48px;
    height: 48px;
    font-size: 24px;
    border-radius: 50%;
    cursor: pointer;
    padding: 12px;
    border: 1px solid #e0e0e0;
    &:hover {
      border: 1px solid #6248ff;
    }

    &-tablet {
      display: none;
    }

    &-left {
      position: absolute;
      left: 0;
      top: 50%;
      transform: translateY(-50%);
    }

    &-right {
      position: absolute;
      right: 0;
      top: 50%;
      transform: translateY(-50%);
    }
  }

  &__slide {
    text-align: left;

    &-inner {
      display: flex;
      gap: 15px;
      align-items: center;
    }
  }

  &__quote {
    flex-shrink: 0;

    &-mobile {
      display: none;
    }

    img {
      width: 33px;
      height: 27px;
    }
  }

  &__content {
    flex: 1;

    & .testimonial-slider__text {
      font-size: 24px;
      line-height: 28px;
      text-align: left;
      font-family: "Museo Sans Cyrl", sans-serif;
      font-weight: 500;
      margin-top: 17px;
      max-width: 570px;
      width: 100%;
      display: block;
    }
  }
  &__nav-mobile {
    display: none;
  }
  &__author {
    display: flex;
    flex-direction: row;
    align-items: center;
    margin-top: 27px;
    gap: 30px;

    & .testimonial-slider__avatar {
      width: 73px;
      height: 73px;
      border-radius: 50%;
    }

    & .testimonial-slider__info {
      .testimonial-slider__name {
        font-weight: 500;
        font-family: "Museo Sans Cyrl", sans-serif;
      }

      .testimonial-slider__role {
        font-size: 16px;
        line-height: 27px;
        color: #4f4f4f;
      }
    }
  }
  &__count {
    margin-top: 12px;
    color: #6248ff;
    font-weight: 600;
    font-size: 14px;
  }
}
/* Адаптив для мобильных */
@media (min-width: 768px) and (max-width: 1024px) {
  .custom-heading__highlight-full {
    width: 168px;
    display: block;
  }
  .testimonial-slider {
    flex-direction: column;

    &__count {
      margin-top: 32px;
    }
    &__top {
      max-height: 140px;
      margin-bottom: 0;
      .testimonial-slider__nav-desktop {
        display: none;
      }
    }
    &__nav-mobile {
      display: none;
    }
    &__layout {
      justify-content: center;
      flex-direction: column;
      margin-top: 48px;
    }

    &__slide {
      text-align: center;
      &-inner {
        flex-direction: column;
        align-items: center;
      }
    }

    &__quote {
      order: 2;
      width: 40px;
      margin-top: 12px;
      margin: 0 auto;

      &-desktop {
        display: none;
      }
      &-mobile {
        display: block;
      }
    }

    &__author {
      flex-direction: column;
      align-items: center;
      margin-top: 0;
      gap: 0;
    }
    &__avatar {
      margin-bottom: 10px;
    }

    &__content {
      .testimonial-slider__text {
        text-align: center;
        margin-top: 16px;
        max-width: 508px;
      }
    }

    &__btn {
      &-tablet {
        display: inline-block;
      }
    }
    &__role {
      margin-bottom: 16px;
    }
  }
}
@media (max-width: 767px) {
  .custom-heading__highlight-full {
    width: 254px;
    display: block;
    margin-bottom: 32px;
    height:50px;
  }
  .testimonial-slider {
    .full-deskop {
      display: none;
    }
    .full-mobile {
      display: block;

    }
    flex-direction: column;
    &__nav {
      &-mobile {
        display: flex;
        width: 100%;
        margin-top: 24px;
        justify-content: space-between;
      }
    }
    &__role {
      margin-bottom: 24px;
    }
    &__text {
    }
    &__top {
      margin-bottom: 0;
      .testimonial-slider__nav-desktop {
        display: none;
      }
    }
    &__content {
      & .testimonial-slider__count {
        display: none;
      }
      .testimonial-slider__text {
        margin-top: 24px;
        max-width: 280px;
        text-align: center;
      }
    }
    &__layout {
      flex-direction: column;
      align-items: center;
    }
    &__avatar {
      margin-bottom: 8px;
    }
    &__author {
      flex-direction: column;
      align-items: center;
      margin-top: 0;
      gap: 0;
    }
    &__info {
      text-align: center;
    }
    &__quote {
      order: 2;
      width: 40px;
      margin: 0 auto;
      &-desktop {
        display: none;
      }
      &-mobile {
        display: block;
      }
    }

    .testimonial-slider__mobile-controls {
      margin-top: 0;
    }
  }

  .testimonial-slider .testimonial-slider__btn-tablet {
    position: static !important;
    transform: none !important;
    margin: 0 8px;
  }

  .testimonial-slider__mobile-controls {
    display: flex;
    justify-content: center;
    margin-top: 16px;
  }
}
/* Анимация появления */
.fade-slide-enter-active,
.fade-slide-leave-active {
  transition: all 0.4s ease;
}
.fade-slide-enter-from {
  opacity: 0;
  transform: translateX(40px);
}
.fade-slide-leave-to {
  opacity: 0;
  transform: translateX(-40px);
}
</style>
