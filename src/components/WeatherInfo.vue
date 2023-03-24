<script setup>
defineProps({
    city: Object
})

</script>

<template>
    <div>
        <h2>Thông tin thời tiết</h2>
        <h3>Thành phố: {{ city.name }}
        </h3>
        <img :src="`http://openweathermap.org/img/w/${city.weather?.[0].icon}.png`" alt="x">
        <h3>Mô tả: {{ city.weather?.[0].description }}</h3>
        <h3>Nhiệt độ: {{ (city.main?.temp - 273.15).toFixed(2) }}°C. Cảm giác như {{ (city.main?.feels_like -
            273.15).toFixed(2) }}°C
        </h3>
        <h3>Nhiệt độ cao nhất: {{ (city.main?.temp_max - 273.15).toFixed(2) }}°C</h3>
        <h3>Nhiệt độ thấp nhất: {{ (city.main?.temp_min - 273.15).toFixed(2) }}°C</h3>
        <h3>Áp suất khí quyển: {{ city.main?.pressure }} hPa</h3>
        <h3>Độ ẩm: {{ city.main?.humidity }}%</h3>
        <h3>Tầm nhìn: {{ city.visibility }} km</h3>
        <h3>Tốc độ gió: {{ city.wind?.speed }} m/s</h3>
    </div>
</template>