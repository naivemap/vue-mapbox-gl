<template>
  <div id="map"></div>
  <n-button>naive-ui</n-button>
</template>

<script lang="ts">
import { onMounted } from 'vue'
import mapboxgl from 'mapbox-gl'
import 'mapbox-gl/dist/mapbox-gl.css'

export default {
  setup() {
    // mounted
    onMounted(() => {
      console.log('Component is mounted!')
      mapboxgl.accessToken =
        'pk.eyJ1IjoiaHVhbmdsaWkiLCJhIjoiY2ptbjJsZXRsMHBlNzNsbGIycTk3eWU0biJ9.Pj_8_ER8nD7UQSSeOg4JZA'
      const map = new mapboxgl.Map({
        container: 'map', // container ID
        style: 'mapbox://styles/mapbox/streets-v11', // style URL
        center: [-74.5, 40], // starting position [lng, lat]
        zoom: 9, // starting zoom
      })
    })
  },
}
</script>

<style lang="less" scoped>
#map {
  height: 400px;
}
</style>
