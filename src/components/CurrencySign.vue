<template>
  <div class="currency-sign">
    <div class="sign">{{ currency.sign }}</div>
    <Flag :country="currency.country" class="flag" />
  </div>
</template>

<script>
import { currenciesByCode } from "../constants/currencies";
import Flag from "./Flag/Flag.vue";

export default {
  components: { Flag },
  props: {
    code: String,
  },
  computed: {
    currency() {
      return currenciesByCode[this.code];
    },
  },
};
</script>

<style scoped>
.currency-sign {
  width: 188px;
  height: 188px;
  position: relative;
}

.sign {
  width: 100%;
  height: 100%;

  display: flex;
  justify-content: center;
  align-items: center;

  background: rgba(255, 255, 255, 0.2);
  border-radius: 50%;
  font-size: 120px;

  color: #ffffff;
}

.flag {
  position: absolute;
  top: 0;
  right: 0;
}
</style>
