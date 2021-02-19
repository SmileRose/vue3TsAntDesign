<template>
  <!-- <a-input v-model:value="value" placeholder="Basic usage" /> -->
  <div class="Rose-form-item">
    <a-form-item label="Activity name">
      <a-input v-model:value="formState.name" />
    </a-form-item>
  </div>
</template>
<script lang="ts">
  import {
    defineComponent,
    ref
  } from 'vue';
  export default defineComponent({
    setup() {
      const value = ref < string > ('');
      return {
        value,
      };
    },
  });
</script>