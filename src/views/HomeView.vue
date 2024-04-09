<template>
    <div>
        <h1 class="text-success">Weather app</h1>
        <p class="h3 mb-3">
            Weather app made by <span class="text-success font-weight-bold">Mateusz Kociołek</span> in Vue.js and Bootstrap
        </p>
        <p class="h4 mb-4">
            I'am using <u>openWeatherApi</u> to get data about weather
        </p>
        <p class="h5">
            <span class="text-success">Usage:</span> <br>
            1. Click "Weather" in navigation bar <br>
            2. Write your city in input Field <br>
        </p>
        <br>
        <img class="image" src="https://cdn.shopify.com/s/files/1/0614/9947/4155/files/KITTEN-MEOW_480x480.jpg?v=1640061250" alt="meow">

    </div>
</template>

<script>
    export default {
        
    }
</script>

<style lang="css" scoped>
    .image {
        position: absolute;
        top: 55%;
        left: 41%;
        width: 500px;
        height: auto;
        margin:-60px 0 0 -60px;
        -webkit-animation:spin 4s linear infinite;
        -moz-animation:spin 4s linear infinite;
        animation:spin 4s linear infinite;
    }
    @-moz-keyframes spin { 
        100% { -moz-transform: rotate(360deg); } 
    }
    @-webkit-keyframes spin { 
        100% { -webkit-transform: rotate(360deg); } 
    }
    @keyframes spin { 
        100% { 
            -webkit-transform: rotate(360deg); 
            transform:rotate(360deg); 
        } 
    }

</style>