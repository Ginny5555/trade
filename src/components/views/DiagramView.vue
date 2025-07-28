<template>
  <section id="diagram" class="diagram">
    <div class="diagram-wrapper container">
      <div class="diagram-wrapper__text">
        <h1>Trade everywhere. Invest here!</h1>
        <p class="diagram-wrapper__text-paragraph">
          We provide only the best trading software. The trading terminal
          MetaTrader4 is the most popular and convenient platform for access to
          global exchanges. You can work anywhere.
        </p>
        <CustomButton class="diagram-wrapper__text-button"
          ><template #text>Start trading</template></CustomButton
        >
      </div>
      <div class="diagram-wrapper__img"></div>
    </div>
  </section>
</template>

<script setup>
import CustomButton from "../ui/CustomButton.vue";
</script>

<style lang="scss">
@import "@/assets/styles/style.scss";
.diagram {
  @include opacity-purple;
}
</style>
