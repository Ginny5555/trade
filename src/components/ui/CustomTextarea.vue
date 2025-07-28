<template>
  <div
    ref="wrapper"
    class="base-input"
    :data-type="type"
    :data-required="required"
    :data-error="errorText"
  >
    <textarea
      :id="id"
      :type="type"
      :placeholder="placeholder"
      class="base-input__field"
    />
    <p class="base-input__error"></p>
  </div>
</template>

<script setup>
import { onMounted, ref , defineProps} from 'vue'

 defineProps({
  type: { type: String, default: 'text' },
  id: String,
  placeholder: String,
  required: { type: Boolean, default: false },
  errorText: { type: String, default: 'Incorrect data' }
})

const wrapper = ref(null)

onMounted(() => {
  const input = wrapper.value.querySelector('textarea')
  const errorBlock = wrapper.value.querySelector('.base-input__error')
  const required = wrapper.value.dataset.required === 'true'
  const errorText = wrapper.value.dataset.error || 'Incorrect data'

  input.addEventListener('input', () => {
    input.classList.remove('valid', 'error')
    errorBlock.textContent = ''
  })

  input.addEventListener('blur', () => {
    const value = input.value.trim()
    let isValid = true

    if (required && !value) {
      isValid = false
    }



    if (isValid) {
      input.classList.add('valid')
    } else {
      input.classList.add('error')
      errorBlock.textContent = errorText
    }
  })
})
</script>

<style scoped lang="scss">
$green :#0eac00;
$grey-light:#828282;
$grey-dark: #4f4f4f;
$grey:#E0E0E0;
$red: #EB5757;

.base-input {
  position:relative;
  display: flex;
  flex-direction: column;

  &__field {
  border: 1px solid $grey;
  border-radius: 3px;
  padding: 7px 16px;
  font-size: 16px;
  line-height: 26px;
  color: $grey-dark;
  font-family: 'Montserrat', sans-serif;
  outline: none;
  box-sizing: border-box;
  height: 89px;
  width:100%;

  &::placeholder {
  color: $grey-light;
  font-size:16px;
  line-height:26px;
  font-family: 'Montserrat', sans-serif;
}
}
&__field:focus {
  border-color: $grey-dark;
}
&__field.valid {
  border-color: $green;
}
&__field.error {
  border-color: $red;
}
&__error {
  position:absolute;
  color: $red;
  font-size: 15px;
  line-height:16px;
  font-family: "Museo Sans Cyrl", sans-serif;
  bottom: -22px;
}
}


</style>
