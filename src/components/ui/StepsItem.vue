<template>
  <div
    class="steps-section__item-wrapper"
    :class="[
      { 'steps-section__item-wrapper--reversed': reversed },
      {
        'is-first': isFirst,
        'is-last': isLast,
      },
    ]"
  >
    <div
      class="steps-section__item"
      :class="{
        'is-first': isFirst,
        'is-last': isLast,
      }"
    >
      <div class="steps-section__content">
        <span class="steps-section__number">{{ number }}</span>
        <h3 class="steps-section__title">{{ title }}</h3>
        <p class="steps-section__text">{{ text }}</p>
      </div>
    </div>

    <div
      v-if="showLine"
      class="steps-section__line"
      :class="{ 'steps-section__line--reversed': reversed }"
    ></div>
    <div class="steps-section__spacer"></div>
  </div>
</template>

<script setup>
import { defineProps } from "vue";
defineProps({
  number: String,
  title: String,
  text: String,
  reversed: {
    type: Boolean,
    default: false,
  },
  showLine: {
    type: Boolean,
    default: true,
  },
  isFirst: Boolean,
  isLast: Boolean,
});
</script>

<style scoped lang="scss">
</style>
