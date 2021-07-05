<template>
  <button
    type="button"
    class="currency-button"
    :class="{ selected: selected }"
  >
    {{ currency.sign }}
  </button>
</template>

<script>
import { currenciesByCode } from "../constants/currencies";

export default {
  props: {
    code: String,
    selected: Boolean,
  },
  computed: {
    currency() {
      return currenciesByCode[this.code];
    },
  },
};
</script>

<style scoped>
.currency-button {
  border: 0;
  background: rgba(255, 255, 255, 0.5);
  border-radius: 50%;
  width: 48px;
  height: 48px;

  display: flex;
  align-items: center;
  justify-content: center;

  font-weight: 900;
  font-size: 32px;

  color: #ffffff;

  font-family: "Source Sans Pro", sans-serif;

  cursor: pointer;
  transition: all 0.3s;
}

.currency-button:hover {
  background-color: rgba(255, 255, 255, 0.7);
}

.currency-button.selected {
  box-shadow: 0 0 0 3px #7b61ff;
  background-color: #fff;
  color: #7b61ff;
}

.currency-button.selected:hover {
  color: rgba(123, 97, 255, 0.8);
}
</style>
