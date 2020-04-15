<template>
  <div id="countryContainer">
    <header> Select a country:</header>
    <country-select :countries="countries"></country-select>
    <!-- <country-detail :country="selectedCountry"/> -->
  </div>
</template>

<script>
import CountrySelect from './components/countrySelect.vue'
import CountryDetail from './components/countryDetail.vue'
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
</style>
