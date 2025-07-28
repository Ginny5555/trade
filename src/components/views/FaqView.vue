<template>
  <section class="faq container">

    <CustomHeading>
      Frequently asked <span class="custom-heading__highlight-full">questions</span>
    </CustomHeading>
    <div class="accordion">
      <div
        class="accordion__item"
        v-for="(item, index) in faqItems"
        :key="index"
        :class="{ open: openIndex === index }"
      >
        <div class="summary" @click="toggle(index)">
          <h3 class="summary-text">{{ item.question }}</h3>
          <span class="icon"
            ><svg
              width="32"
              height="32"
              viewBox="0 0 32 32"
              fill="none"
              xmlns="http://www.w3.org/2000/svg"
            >
              <path
                fill-rule="evenodd"
                clip-rule="evenodd"
                d="M16 7C16.2652 7 16.5196 7.10536 16.7071 7.29289C16.8946 7.48043 17 7.73478 17 8V16C17 16.2652 16.8946 16.5196 16.7071 16.7071C16.5196 16.8946 16.2652 17 16 17H8C7.73478 17 7.48043 16.8946 7.29289 16.7071C7.10536 16.5196 7 16.2652 7 16C7 15.7348 7.10536 15.4804 7.29289 15.2929C7.48043 15.1054 7.73478 15 8 15H15V8C15 7.73478 15.1054 7.48043 15.2929 7.29289C15.4804 7.10536 15.7348 7 16 7Z"
                fill="black"
              />
              <path
                fill-rule="evenodd"
                clip-rule="evenodd"
                d="M15 16C15 15.7348 15.1054 15.4804 15.2929 15.2929C15.4804 15.1054 15.7348 15 16 15H24C24.2652 15 24.5196 15.1054 24.7071 15.2929C24.8946 15.4804 25 15.7348 25 16C25 16.2652 24.8946 16.5196 24.7071 16.7071C24.5196 16.8946 24.2652 17 24 17H17V24C17 24.2652 16.8946 24.5196 16.7071 24.7071C16.5196 24.8946 16.2652 25 16 25C15.7348 25 15.4804 24.8946 15.2929 24.7071C15.1054 24.5196 15 24.2652 15 24V16Z"
                fill="black"
              /></svg
          ></span>
        </div>
        <div class="accordion__content" ref="contents">
          <p class="accordion__content-text">{{ item.answer }}</p>
        </div>
      </div>
      </div>
  </section>
</template>

<script setup>
import { ref, onMounted, nextTick } from "vue";
import CustomHeading from "@/components/ui/CustomHeading.vue";

const faqItems = ref([
  {
    question: "How do I change my details?",
    answer:
      "We provide only the best trading software. The trading terminal MetaTrader4 is the most popular and convenient platform for access to global exchanges. You can work anywhere. All you need is the Internet because the necessary trading tools are already collected in one place and are available in a couple of clicks. Use only the best and develop with us!",
  },
  {
    question: "What platforms will I be able to use?",
    answer:
      "We provide only the best trading software. The trading terminal MetaTrader4 is the most popular and convenient platform for access to global exchanges. You can work anywhere. All you need is the Internet because the necessary trading tools are already collected in one place and are available in a couple of clicks. Use only the best and develop with us!",
  },
  {
    question: "How do I change my details?",
    answer:
      "We provide only the best trading software. The trading terminal MetaTrader4 is the most popular and convenient platform for access to global exchanges. You can work anywhere. All you need is the Internet because the necessary trading tools are already collected in one place and are available in a couple of clicks. Use only the best and develop with us!",
  },
  {
    question: "How do I change my details?",
    answer:
      "We provide only the best trading software. The trading terminal MetaTrader4 is the most popular and convenient platform for access to global exchanges. You can work anywhere. All you need is the Internet because the necessary trading tools are already collected in one place and are available in a couple of clicks. Use only the best and develop with us!",
  },
  {
    question: "How do I change my details?",
    answer:
      "We provide only the best trading software. The trading terminal MetaTrader4 is the most popular and convenient platform for access to global exchanges. You can work anywhere. All you need is the Internet because the necessary trading tools are already collected in one place and are available in a couple of clicks. Use only the best and develop with us!",
  },
  {
    question: "How do I change my details?",
    answer:
      "We provide only the best trading software. The trading terminal MetaTrader4 is the most popular and convenient platform for access to global exchanges. You can work anywhere. All you need is the Internet because the necessary trading tools are already collected in one place and are available in a couple of clicks. Use only the best and develop with us!",
  },
  {
    question: "How do I change my details?",
    answer:
      "We provide only the best trading software. The trading terminal MetaTrader4 is the most popular and convenient platform for access to global exchanges. You can work anywhere. All you need is the Internet because the necessary trading tools are already collected in one place and are available in a couple of clicks. Use only the best and develop with us!",
  },
]);

const openIndex = ref(1); // <-- второй блок открыт по умолчанию (индекс 1)
const contents = ref([]);

const toggle = async (index) => {
  if (openIndex.value === index) {
    openIndex.value = null;
  } else {
    openIndex.value = index;
  }

  await nextTick();

  contents.value.forEach((el, i) => {
    el.style.maxHeight = openIndex.value === i ? el.scrollHeight + "px" : "0px";
  });
};

onMounted(() => {
  contents.value.forEach((el, i) => {
    el.style.maxHeight = i === openIndex.value ? el.scrollHeight + "px" : "0px";
  });
});
</script>


<style scoped lang="scss">
</style>
