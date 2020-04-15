<template lang="html">
  <div class="details" v-if="country">
    <h3>Name: {{country.name}}</h3>
    <p>Population: {{country.population}}</p>
    <p>Capital: {{country.capital}}</p>

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
