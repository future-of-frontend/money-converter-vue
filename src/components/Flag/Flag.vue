<template>
  <component :is="icon" class="flag"></component>
</template>

<script>
import EU from "./Icons/EU";
import Poland from "./Icons/Poland";
import UK from "./Icons/UK";
import Ukraine from "./Icons/Ukraine";
import USA from "./Icons/USA";
import { CountryCodes } from "../../constants/currencies";

const iconLookup = {
  [CountryCodes.EUR]: EU,
  [CountryCodes.POL]: Poland,
  [CountryCodes.UKR]: Ukraine,
  [CountryCodes.USA]: USA,
  [CountryCodes.GBR]: UK,
};

export default {
  props: {
    country: String,
  },
  computed: {
    icon() {
      return iconLookup[this.country];
    },
  },
};
</script>

<style scoped>
.flag {
  display: inline-block;
}
</style>
