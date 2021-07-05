<template>
  <div class="wrapper">
    <h1 class="title">MoneyConvert® 2.0</h1>
    <Converter />
  </div>
</template>

<script>
import Converter from "./components/Converter.vue";

export default {
  components: {
    Converter,
  },
};
</script>

<style scoped>
.wrapper {
  min-height: 100vh;
  background: linear-gradient(90deg, #667eea 0%, #764ba2 100%);
  padding: 50px 70px;
}

.title {
  color: #fff;
  font-weight: 900;
  font-size: 100px;
  line-height: 126px;
  margin: 0 0 21px;
}
</style>
