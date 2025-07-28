<template>
  <main>
    <header>
      <MenuView />
    </header>
    <aside>
      <DiagramView />
      <StepsView />
      <SliderView />
      <FaqView />
      <ContactView />
    </aside>
    <footer>
      <FooterView />
    </footer>
  </main>
</template>

<script setup>
import MenuView from "./views/MenuView.vue";
import DiagramView from "./views/DiagramView.vue";
import StepsView from "./views/StepsView.vue";
import FaqView from "./views/FaqView.vue";
import SliderView from "./views/SliderView.vue";
import ContactView from "./views/ContactView.vue";
import FooterView from "./views/FooterView.vue";
</script>

<style>
</style>
