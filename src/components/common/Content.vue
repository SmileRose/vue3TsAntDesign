<template>
  <div class="Rose-content">
    <a-form-model :model="form" :label-col="labelCol" :wrapper-col="wrapperCol">

      <a-form-model-item :label="form.name" v-if="attr.type==='input'">
        <a-input  />
      </a-form-model-item>

      <a-form-model-item label="Activity zone" v-else-if="attr.type==='select'">

        <a-select v-model="form.name" placeholder="">
          <a-select-option value="shanghai">
            Zone one
          </a-select-option>
          <a-select-option value="beijing">
            Zone two
          </a-select-option>
        </a-select>
      </a-form-model-item>
    </a-form-model>
  </div>
</template>

<script lang="ts">
  import {
    defineComponent,
    PropType
  } from 'vue';
  interface ComplexMessage {
    name: '',
      region: undefined,
      date1: undefined,
      delivery: false,
      type: string,
      resource: '',
      desc: '',
  }

  export default defineComponent({
    data() {
      return {
        labelCol: {
          span: 4
        },
        wrapperCol: {
          span: 14
        },

      };
    },
    props: {
      attr: Object as PropType < ComplexMessage >
    }

  })
</script>