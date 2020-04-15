<template lang="html">
<select>
<option v-for="(country, index) in countries" v-bind:value="country" :key="index">{{country.name}}</option>
</select>
</template>

<script>
import { eventBus } from '../main.js';
import countries from '../App.vue';

export default {
  name: 'countries-select',
  props: ['countries'],
  components: {
    "countries": countries
  }
}
</script>

<style lang="css" scoped>
</style>
