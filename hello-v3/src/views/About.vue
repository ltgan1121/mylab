<template>

  <a-button type="primary" @click="showModal">Open Modal</a-button>
  <a-modal v-model:visible="visible" title="Basic Modal" @ok="handleOk" style="height:700px;">
    
  <a-select
    v-model:value="value1"
    style="width: 120px;"
    @focus="focus"
    ref="select"
    @change="handleChange"
  >
    <a-select-option value="jack">Jack</a-select-option>
    <a-select-option value="lucy">Lucy</a-select-option>
    <a-select-option value="disabled" disabled>Disabled</a-select-option>
    <a-select-option value="Yiminghe">yiminghe</a-select-option>
  </a-select>


  </a-modal>
</template>
<script lang="ts">
import { defineComponent, ref } from "vue";
export default defineComponent({
  setup() {
    const focus = () => {
      console.log("focus");
    };

    const visible = ref<boolean>(false);

    const showModal = () => {
      visible.value = true;
    };

    const handleOk = (e: MouseEvent) => {
      console.log(e);
      visible.value = false;
    };

    return {
      focus,
      value1: ref("lucy"),
       visible,
      showModal,
      handleOk
    };
  },
});
</script>
