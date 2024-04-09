<template>
  <div class="container">
    <h1 class="mb-4 text-success">Weather</h1>
    <CityInput/>
    <CityData/>
  </div>
</template>

<script>
  import CityData from "../components/weatherPage/cityData.vue";
  import CityInput from "../components/weatherPage/cityInput.vue";


  export default {
    components:{
      CityInput,
      CityData
    }
  }
</script>

<style lang="scss" scoped>

</style>