<template>
  <section class="steps-section">
    <div class="container">
      <CustomHeading class="steps-section__header">
        Getting Started Is
        <span class="custom-heading__highlight"> Fast & Easy</span>
      </CustomHeading>
      <div class="steps-section__box">
        <StepsItem
          v-for="(step, index) in steps"
          :key="index"
          :number="step.number"
          :title="step.title"
          :text="step.text"
          :reversed="step.reversed"
          :showLine="index !== steps.length - 1"
          :isFirst="index === 0"
          :isLast="index === steps.length - 1"
        />
      </div>
    </div>
  </section>
</template>

<script setup>
import StepsItem from "@/components/ui/StepsItem.vue";
import CustomHeading from "@/components/ui/CustomHeading.vue";
const steps = [
  {
    number: "01.",
    title: "Register",
    text: "Complete the simple registration to get your trading credentials.",
    reversed: false,
  },
  {
    number: "02.",
    title: "Verification",
    text: "Big Invest is required to verify your identity, upload your documents quickly and get approved in minutes.",
    reversed: true,
  },
  {
    number: "03.",
    title: "Deposit funds",
    text: "Big Invest accepts credit cards and bank wires. Just use the secure deposit form and follow the steps.",
    reversed: false,
  },
  {
    number: "04.",
    title: "Start Trading",
    text: "Once your deposit has been credited, you can begin trading instantly. In no time you will see profits rolling into your account.",
    reversed: true,
  },
];
</script>

<style lang="scss">
.steps-section__wrapper {
  display: flex;
  flex-direction: column;
  gap: 60px;
  align-items: center;
  width: 100%;
  max-width: 100%;
  box-sizing: border-box;
}
</style>
