<template>
  <input type="number" v-model="value" @input="$emit('input', value ? parseInt(value):0)" />
</template>

<script>
export default {
  name: "NumberInput",
  props: {
    defaultValue: Number,
  },
  data: function () {
    return {
      value: this.defaultValue,
    };
  },
};
</script>

<style scoped>
input {
  box-sizing: border-box;
  width: 100%;
  padding: 5px;
  text-align: center;
  margin-bottom: 5px;
}
</style>