<template>
  <div>
    <h1>Countries</h1>
    <label for="countries-select">Select Country</label>
    <select id="countries-select" v-model="selectedCountry">
      <option value="" disabled>Select Country</option>
      <option v-for="country in countries" :key= "country.alpha3Code" :value="country">
        {{country.name}}</option>
    </select>
    <!-- <img :src="selectedCountry.flag" width=200px height=auto> -->

    <country-detail></country-detail>
    <button>Add country to favourites</button>
    <favourite-countries></favourite-countries>

  </div>
</template>

<script>
import CountryDetail from './components/CountryDetail.vue'
import FavouriteListItem from './components/FavouriteListItem.vue'
export default {
  name: "app",
  data(){
    return {
      countries:[],
      selectedCountry:null,
      favouriteCountries:[]
    }
  },
  components:{
    "country-detail":CountryDetail,
    "favourite-countries":FavouriteListItem,
  },
  mounted(){
    this.getCountries()
  },
  methods: {
    getCountries: function(){
      fetch("https://restcountries.eu/rest/v2/all")
      .then(response => response.json())
      .then(data => this.countries = data)
    }
  }
}
</script>

<style>

</style>
