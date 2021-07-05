<template>
  <div class="currency-switcher">
    <CurrencySign :code="modelValue" />
    <div class="buttons">
      <CurrencyButton
        v-for="currency in currencies"
        :key="currency.code"
        :code="currency.code"
        :selected="currency.code === modelValue"
        @click="$emit('update:modelValue', currency.code)"
        class="button"
      />
    </div>
  </div>
</template>

<script>
import { currencies } from "../constants/currencies";
import CurrencyButton from "./CurrencyButton.vue";
import CurrencySign from "./CurrencySign.vue";

export default {
  components: { CurrencyButton, CurrencySign },
  props: {
    modelValue: String,
  },
  emits: ['update:modelValue'],
  data() {
    return {
      currencies,
    };
  },
};
</script>

<style scoped>
.currency-switcher {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.buttons {
  display: flex;
  margin-top: 16px;
}

.button {
  margin: 0 4px;
}
</style>
