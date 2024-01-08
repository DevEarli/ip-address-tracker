<script>
var map;
var marker;

export default {
  props: ["data"],
  mounted() {
    map = L.map("map", {
      center: [51.505, -0.09],
      zoom: 13,
    });
    L.tileLayer("https://tile.openstreetmap.org/{z}/{x}/{y}.png", {
      attribution:
        '&copy; <a href="https://www.openstreetmap.org/copyright">OpenStreetMap</a> contributors',
    }).addTo(map);

    marker = L.marker([51.505, -0.09]);
    marker.addTo(map);
  },
  watch: {
    data() {
      const { lat, lng } = this.data.location;
      map.setView([lat, lng], 13, {
        animate: true,
      });

      marker.remove();
      marker = L.marker([lat, lng]);

      marker.addTo(map);
    },
  },
};
</script>

<template>
  <div id="map"></div>
</template>

<style scoped>
#map {
  height: 61vh;
}
</style>
