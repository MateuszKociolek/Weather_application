<template>
    <div class="mt-4">
        <button class="btn btn-success" @click="getData($store.state.cityName)">Fetch data</button>
        <h2 class="mt-3">{{ name }}</h2>
        <div class="card mb-4 align-items-center">
            <div class="card-body d-flex align-items-center">
                <p class="mb-0 mx-5 h3">{{ weather }}</p>
                <img :src="icon" class="ml-auto" style="max-width: 50px;" alt="Weather icon">
            </div>
        </div>

        <div class="row">
            <div v-for="(item, index) in data" :key="index" class="col-md-6 mb-4">
                <div class="card">
                    <div class="card-body">
                        <p class="card-text" v-if="item != null">{{ index }} : {{ item }}
                             <span v-if="index=='Ciśnienie'">hPa</span>
                             <span v-if="index != 'Wilgotność' && index != 'Ciśnienie'">℃</span>
                        </p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            name: null,
            data: {
                Temparatura: null,
                Odczuwalna: null,
                Minimalna: null,
                Maksymalna: null,
                Ciśnienie: null,
                Wilgotność: null,
            },
            weather: null,
            icon: null,
        }
    },
    methods: {
        async getData(cityName){
            try {
                const response = await fetch(`https://api.openweathermap.org/data/2.5/weather?q=${cityName}&appid=1d7ff9fdaabc10854694d1d51c0462d3`);
                if (!response.ok) {
                    throw new Error('Nie udało się pobrać danych');
                }
                var res = await response.json();
                this.data["Temparatura"] = (res["main"]["temp"] - 273.15).toFixed(0);
                this.data["Odczuwalna"] = (res["main"]["feels_like"] - 273.15).toFixed(0);
                this.data["Minimalna"] = (res["main"]["temp_min"] - 273.15).toFixed(0) ;
                this.data["Maksymalna"] = (res["main"]["temp_max"] - 273.15).toFixed(0);
                this.data["Ciśnienie"] = res["main"]["pressure"];
                this.data["Wilgotność"] = res["main"]["humidity"];
                var iconId = res["weather"][0]["icon"]
                console.log(iconId)
                this.icon = `https://openweathermap.org/img/wn/${iconId}@2x.png`
                this.name = res["name"]
                this.weather = res["weather"][0]["main"]
            } catch (error) {
                console.error('Błąd pobierania danych:', error);
            }
        },
    },

    mounted() {
        this.getData("Bielsko-Biala");
    },
}
</script>

<style>
    
</style>