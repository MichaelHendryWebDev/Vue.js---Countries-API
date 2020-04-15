<template lang="html">
<div>
  <ul>
    <list-item v-for="(country, index) in countries" :country="country" :key="index"></list-item>
  </ul>

</div>
</template>

<script>

import ListItem from './ListItem.vue';
export default {
  name: 'countries-list',
  props: ['countries'],
  components: {
    "list-item": ListItem
  }
}
</script>

<style lang="css" scoped>
</style>

<!-- <option v-for="(country, index) in countries" v-bind:value="country" :key="index">{{country.name}}</option> -->
