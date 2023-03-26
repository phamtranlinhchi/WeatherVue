<script setup>
import { ref, computed } from 'vue'
import WeatherSelection from './components/WeatherSelection.vue';
import WeatherInfo from './components/WeatherInfo.vue';
const cities = [
  { name: 'Hà Nội', value: 'hanoi' },
  { name: 'Tokyo', value: 'tokyo' },
  { name: 'New York', value: 'new york' },
  { name: 'London', value: 'london' },
  { name: 'Seoul', value: 'seoul' }
]
const weatherSelectionRef = ref(null)
const weatherInfo = computed(() => weatherSelectionRef.value?.weatherInfo)
</script>

<template>
  <WeatherSelection ref="weatherSelectionRef" :cities="cities" />
  <WeatherInfo :city="weatherInfo" />
</template>