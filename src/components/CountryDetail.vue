<template lang="html">
<div>
    <h2>Country Name:</h2>
    <p>Population:</p>
    <p>{{selectedCountry.name}}</p>
    <img class="lrg-flag"/>
</div>
  
</template>

<script>
export default {
    name:"country-detail",
    props:['selectedCountry']

}
</script>

<style lang="css" scoped>

</style>