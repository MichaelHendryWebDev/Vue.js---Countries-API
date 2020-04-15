<template>
  <div id="country-container">
    <header> Select a country:</header>
    <country-select :countries="countries"></country-select>
    <country-detail :country="selectedCountry"></country-detail>
  </div>
</template>

<script>
import CountryDetail from './components/CountryDetail.vue'

import CountrySelect from './components/CountrySelect.vue'
import { eventBus } from './main.js'

export default {
  name: 'App',
  data(){
    return {
      countries: [],
      selectedCountry: null
    };
  },
  mounted(){
    fetch('https://restcountries.eu/rest/v2/all')
    .then(res => res.json())
    .then(countries => this.countries = countries)

    eventBus.$on('country-selected', (country) => {
      this.selectedCountry = country;
    })
  },
  components: {
    "country-select": CountrySelect,
    "country-detail": CountryDetail
  }
}
</script>


<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.details {
  display: flex;
  justify-content: space-between;
  flex-direction: column;
}
</style>
