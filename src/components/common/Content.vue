<template>
  <div class="Rose-content">

    <a-form :model="form" :label-col="labelCol" :wrapper-col="wrapperCol" layout="horizontal" labelAlign="right">

      <a-form-item label="输入框" v-if="attr.type=='input'">
        <a-input block />
      </a-form-item>
      <a-form-item label="输入框" v-else-if="attr.type=='textarea'">
        <a-textarea v-model:value="value2" placeholder="textarea with clear icon" allow-clear :rows="4" />
      </a-form-item>

      <a-form-item label="下拉框" v-else-if="attr.type=='select'">

        <a-select v-model:value="attr.region" placeholder="please select your zone">
          <a-select-option value="shanghai">
            Zone one
          </a-select-option>
          <a-select-option value="beijing">
            Zone two
          </a-select-option>
        </a-select>
      </a-form-item>
    </a-form>

  </div>
</template>

<script lang="ts">
  import {
    defineComponent,
    PropType
  } from 'vue';

  interface ComplexMessage {
    text: '',
      icon: undefined,
      date1: undefined,
      type: string,
      resource: '',
      desc: '',
  }

  interface FormState {
    name: string;
    region: string | undefined;
    date1: Moment | undefined;
    delivery: boolean;
    type: string[];
    resource: string;
    desc: string;
  }

  export default defineComponent({
    data() {
      return {
        labelCol: {span: 4, offset: 0},
        wrapperCol: {span: 16},

      };
    },
    props: {
      attr: Object as PropType < ComplexMessage >
    }

  })
</script>