<template>
  <div class="input">
    <input
      type="number"
      :readonly="readonly"
      :value="modelValue"
      @input="$emit('update:modelValue', $event.target.value)"
    />
  </div>
</template>

<script>
export default {
  props: {
    modelValue: String,
    readonly: Boolean,
  },
  emits: ['update:modelValue'],
};
</script>

<style scoped>
.input input {
  -moz-appearance: textfield;
  appearance: none;
  background: rgba(255, 255, 255, 0.29);
  border-radius: 20px;
  font-weight: 900;
  font-size: 120px;

  text-align: right;

  color: #ffffff;

  padding: 28px 60px 39px;
  outline: 0;
  font-family: inherit;
  width: 100%;
  display: block;

  transition: border-color 0.3s;
  border: 10px solid transparent;
}

.input input::-webkit-outer-spin-button,
.input input::-webkit-inner-spin-button {
  -webkit-appearance: none;
  margin: 0;
}

.input input:read-only {
  background: rgba(255, 255, 255, 0.1);
}

.input input:focus:not(:read-only) {
  border-color: rgba(255, 255, 255, 0.6);
}
</style>
