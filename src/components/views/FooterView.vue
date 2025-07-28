<template>
  <div class="footer container">

    <div class="footer__mobile">
      <div class="footer__logo">LOGO</div>
      <nav class="footer__nav">
        <ul>
          <li v-for="(link, i) in links" :key="i">
            <a :href="link.href" :class="{ 'footer__link--bold': link.bold }">{{ link.text }}</a>
          </li>
        </ul>
      </nav>
    </div>

    <div class="footer__center">
      <div class="footer__logo footer-desktop">LOGO</div>
      <div class="footer-wrapper">
      <div class="footer__block">
        <h3 class="rules">Information and high risk warning:</h3>
        <p class="details">{{ riskText }}</p>
      </div>

      <div class="footer__block">
        <h3 class="rules">Legal disclaimer:</h3>
        <p class="details">{{ legalText }}</p>
      </div>
      </div>
       <nav class="footer__nav footer-desktop">
        <ul>
          <li v-for="(link, i) in links" :key="i">
            <a :href="link.href" :class="{ 'footer__link--bold': link.bold }">{{ link.text }}</a>
          </li>
        </ul>
      </nav>
    </div>

    <div class="footer__bottom">
      <p class="footer__bottom-copyright">Copyright 2020, All Right Reserved</p>
      <ul class="footer__links">
        <li v-for="(item, i) in policyLinks" :key="i">
          <a :href="item.href">{{ item.text }}</a>
        </li>
      </ul>

    </div>
  </div>
</template>

<script setup>
const links = [
  { text: 'About us', href: '#about' },
  { text: 'Instructions', href: '#instructions' },
  { text: 'Platforms', href: '#platforms' },
  { text: 'Contact Us', href: '#contact' },
  { text: 'Sign in', href: '#signin' },
  { text: 'Sign up for free', href: '#signup', bold: true },
]

const policyLinks = [
  { text: 'Terms and Conditions', href: '#' },
  { text: 'Privacy Policy', href: '#' },
  { text: 'Risk Warnings', href: '#' },
  { text: 'Anti-Money Laundering', href: '#' },
]

const riskText = `Trading with foreign exchange (FX), contract for differences (CFDs) and precious metals carries a high level of risk that may not be suitable for all investors. Leverage creates additional risk and loss exposure. Before you decide to trade foreign exchange or contract for differences, carefully consider your investment objectives, experience level, and risk tolerance.`
const legalText = `Forex trading entails significant risks and is not appropriate for all investors. The possibility of incurring substantial losses should be taken into account. It is therefore important to understand the possible consequences of investing. Traders should weigh their earning potential against the risks involved and act accordingly. Interactive Trade Ltd operating under brand and using domenLink domain within the European Economic Area.`
</script>


<style scoped lang="scss">
@import "@/assets/styles/style.scss";

</style>


