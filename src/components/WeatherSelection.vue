<script setup>
import { ref, watchEffect } from 'vue'
import WeatherInfo from './WeatherInfo.vue';

let selectedCity = ref('hanoi')
let weatherInfo = ref({});
defineProps({
    cities: Array,
})
watchEffect(async () => {
    try {
        const result = await (await fetch(`https://api.openweathermap.org/data/2.5/weather?q=${selectedCity.value}&appid=${import.meta.env.VITE_API_KEY}&lang=vi`)).json();
        if (result.cod == 200) {
            weatherInfo.value = result
        } else {
            alert(`Mã lỗi: ${result.cod} \nLỗi: ${result.message}`)
        }
    } catch (err) {
        alert(err);
    }
})
</script>

<template>
    <div>
        <select class="city-select" v-model="selectedCity">
            <option v-for="city in cities" :key="city.value" :value="city.value">{{ city.name }}</option>
        </select>
        <WeatherInfo :city="weatherInfo" />
    </div>
</template>


<style scoped>
.city-select {
    padding: 8px 16px;
    width: 200px;
}
</style>
