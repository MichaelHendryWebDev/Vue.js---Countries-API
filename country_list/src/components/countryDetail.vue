<template lang="html">
  <div v-if="country">
    <h1>hello</h1>
  </div>

</template>

<script>
import { eventBus } from '../main.js';

export default {
  name: 'country-detail',
  props: ['country']
}
</script>

<style lang="css" scoped>
</style>
