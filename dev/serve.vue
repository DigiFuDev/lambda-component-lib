<script>
import { defineComponent } from 'vue';
// Uncomment import and local "components" registration if library is not registered globally.
// import { LambdaComponentLibSample } from '@/entry.esm';

export default defineComponent({
  name: 'ServeDev',
  // components: {
  //  LambdaComponentLibSample,
  // }
});
</script>

<template>
  <div id="app">
    <lambda-component-lib-sample />
  </div>
</template>
