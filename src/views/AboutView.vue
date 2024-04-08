<template>
  <div class="container">
    <h1 class="mb-4 text-success">Weather</h1>
    <CityInput/>
    <CityData/>
  </div>
</template>

<script>
  import CityData from "./weatherPage/cityData.vue";
  import CityInput from "./weatherPage/cityInput.vue";


  export default {
    components:{
      CityInput,
      CityData
    }
  }
</script>

<style lang="scss" scoped>

</style>