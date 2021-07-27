<template>
  <a-select
    v-model:value="value1"
    style="width: 120px"
    @focus="focus"
    ref="select"
    @change="handleChange"
  >
    <a-select-option value="jack">Jack</a-select-option>
    <a-select-option value="lucy">Lucy</a-select-option>
    <a-select-option value="disabled" disabled>Disabled</a-select-option>
    <a-select-option value="Yiminghe">yiminghe</a-select-option>
  </a-select>
</template>
<script>
import { defineComponent, ref } from 'vue';
export default defineComponent({
  setup() {
    const focus = () => {
      console.log('focus');
    };

    const handleChange = value => {
      console.log(`selected ${value}`);
    };

    return {
      focus,
      handleChange,
      value1: ref('lucy'),
    };
  },
});
</script>