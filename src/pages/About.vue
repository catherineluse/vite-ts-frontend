<script lang="ts">
import { defineComponent } from 'vue';
import { GoogleMap } from "google-map-ts-vue3";
import config from '../config';

export default defineComponent({
  name: "Map",
  setup() {
    return {
      googleMapsApiKey: config.googleMapsApiKey
    }
  },
  components: {
    GoogleMap
  }
})
</script>

<template>
  <BaseTemplate>
    <GoogleMap
    apiKey="googleMapsApiKey"
    libraries="geometry,drawing,places"
    :options="{
      center: { lat: 35.1, lng: 135.1 },
      zoom: 5,
    }"
    :markers="[
      {
        position: { lat: 35.1, lng: 135.1 },
        title: 'position1',
        draggable: false,
      },
      {
        position: { lat: 37.1, lng: 139.1 },
        title: 'position2',
        draggable: false,
      },
    ]"
    :polylines="[
      {
        path: [
          { lat: 35.1, lng: 135.1 },
          { lat: 37.1, lng: 139.1 },
        ],
        geodesic: true,
        strokeColor: '#ff0000',
        strokeOpacity: 1.0,
        strokeWeight: 2,
      },
      {
        path: [
          { lat: 38.1, lng: 136.1 },
          { lat: 34.1, lng: 135.1 },
          { lat: 37.1, lng: 139.1 },
        ],
        geodesic: true,
        strokeColor: '#ffffff',
        strokeOpacity: 1.0,
        strokeWeight: 2,
      },
    ]"
    :polygons="[
      {
        paths: [
          { lat: 30, lng: 140 },
          { lat: 31, lng: 141 },
          { lat: 30, lng: 145 },
          { lat: 33, lng: 140 },
        ],
        strokeColor: '#ff0000',
        strokeOpacity: 0.8,
        strokeWeight: 3,
        fillColor: '#ff0000',
        fillOpacity: 0.35,
      },
    ]"
    :circles="[
      {
        strokeColor: '#ff0000',
        strokeOpacity: 0.8,
        strokeWeight: 2,
        fillColor: '#ff0000',
        fillOpacity: 0.35,
        center: { lat: 39.1, lng: 140.1 },
        radius: 100000,
      },
    ]"
    :rectangles="[
      {
        strokeColor: '#ff0000',
        strokeOpacity: 0.8,
        strokeWeight: 2,
        fillColor: '#ff0000',
        fillOpacity: 0.35,
        bounds: {
          north: 30,
          south: 33,
          east: 133,
          west: 130,
        },
      },
    ]"
  />
  </BaseTemplate>
</template>
