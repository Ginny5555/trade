<template>
<div class="form">
  <form action="">
    <div class="form-fields">
  <CustomInput
    placeholder="Name"
    v-model="name"
    id="name"
    :required="true"
    error-text="Required name"
  />

  <CustomInput
    placeholder="Email"
    v-model="email"
    type="email"
    id="email"
    :required="true"
    error-text="Incorrect email type"
  />
   <CustomTextarea
    placeholder="Text"
    v-model="text"
    type="text"
    id="text"
    :required="true"
    error-text="Incorrect email type"
  />
  </div>
        <CustomButton class="form-button"><template #text>Send</template></CustomButton>
  </form>
  </div>
</template>

<script setup>
import CustomInput from '../ui/CustomInput.vue';
import CustomTextarea from '../ui/CustomTextarea.vue';
import CustomButton from "../ui/CustomButton.vue";
import { ref } from 'vue'

const name = ref('')
const email = ref('')
const text = ref('')
</script>

<style scoped lang="scss">
$violet: #6248FF;
$white: #FFFFFF;
.form {
  width:100%;
  max-width:585px ;
  height: 471px;
  border: 2px solid $violet;
  border-radius:20px;
  background: $white;
  padding: 80px;
  box-sizing: border-box;
  margin-top:14px;
  &-fields {
    gap:24px;
    display: flex;
    flex-direction: column;
    margin-bottom:40px;
  }
  &-button {
    font-size:16px;
    line-height: 14px;
    letter-spacing: 0.03em;
    margin: 0 auto;

  }
}
@media (min-width: 768px) and (max-width: 1024px) {
.form {
  padding:80px 41px 80px 42px;
  margin:0 auto;
  &-fields {
    margin-bottom:40px;
  }
  &-button {
    margin: 0 auto;
  }
}
}
@media (max-width: 767px) {
.form {
  padding:48px 16px;
  height: 415px;
  margin-top:0;
   &-fields{
    margin-bottom:48px;
  }
  &-button {
    margin: 0 auto;
  }
}
}
</style>
