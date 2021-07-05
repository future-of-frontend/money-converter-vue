<template>
  <div>
    <div class="row">
      <Input v-model="value" class="input" />
      <CurrencySwitcher v-model="from" />
    </div>
    <div class="row">
      <Input readonly v-model="result" class="input" />
      <CurrencySwitcher v-model="to" />
    </div>
  </div>
</template>

<script>
import CurrencySwitcher from "./CurrencySwitcher.vue";
import Input from "./Input.vue";
import { CurrencyCodes, ratesByCode } from "../constants/currencies";
import round from "../helpers/round";

export default {
  components: { Input, CurrencySwitcher },
  data() {
    return {
      value: "",
      from: CurrencyCodes.UAH,
      to: CurrencyCodes.USD,
    };
  },
  computed: {
    result() {
      const result = round(
        (this.value * ratesByCode[this.from]) / ratesByCode[this.to]
      );
      return result ? result.toString() : "";
    },
  },
};
</script>

<style scoped>
.row {
  display: flex;
  align-items: center;
}

.row + .row {
  margin-top: 90px;
}

.input {
  margin-right: 32px;
  flex-grow: 1;
}
</style>
