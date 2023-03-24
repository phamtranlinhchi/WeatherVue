<script setup>
import WeatherSelection from './components/WeatherSelection.vue';
const cities = [
  { name: 'Hà Nội', value: 'hanoi' },
  { name: 'Tokyo', value: 'tokyo' },
  { name: 'New York', value: 'new york' },
  { name: 'London', value: 'london' },
  { name: 'Seoul', value: 'seoul' }
]
</script>

<template>
  <WeatherSelection :cities="cities" />
</template>