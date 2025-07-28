<template>
  <section class="contact">
    <div class="container">
      <div class="contact-wrapper">
        <div class="contact-info">
          <CustomHeading class="contact-info__header"> Contact us! </CustomHeading>
          <p>The support staff and customer service are available to help you with any questions or needs you might have. Just drop us a line.</p>
          <div class="contact-info__details">
            <span class="details">This site is owned and operated by Kode Tech Solutions LTD</span>
            <div class="info-contacts">
              <div class="info-contacts__item">
                <span class="info-contacts__item-title">Phone:</span>
                <span class="details">442038857261</span>
              </div>
              <div class="info-contacts__item">
                <span class="info-contacts__item-title">Email:</span>
                <span class="details">help@google.com</span>
              </div>
              <div class="info-contacts__item">
                <span class="info-contacts__item-title">Address:</span>
                <span class="details">Trust Company Complex, Ajeltake Road, Ajeltake Island, Majuro, Republic of the Marshall Islands, MH 96960</span>
              </div>
            </div>
          </div>
        </div>
        <FormView />
      </div>
    </div>
  </section>
</template>

<script setup>
import FormView from "./FormView.vue";
import CustomHeading from "@/components/ui/CustomHeading.vue";
</script>

<style lang="scss">
@import "@/assets/styles/style.scss";

</style>
