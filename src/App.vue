<script>
import { isIP } from "is-ip";
import isValidDomain from "is-valid-domain";

import Header from "./components/Header.vue";
import Card from "./components/Card.vue";
import Map from "./components/Map.vue";

export default {
  components: {
    Header,
    Card,
    Map,
  },
  data() {
    return {
      data: {},
    };
  },
  methods: {
    async getData(search) {
      if (!search) return;
      let url = `https://geo.ipify.org/api/v2/country,city?apiKey=${import.meta.env.VITE_API_KEY}`;

      if (isIP(search)) {
        url += `&ipAddress=${search}`;
      } else if (isValidDomain(search)) {
        url += `&domain=${search}`;
      } else {
        return;
      }

      try {
        const response = await fetch(url);
        const data = await response.json();
        this.data = data;
      } catch (err) {
        console.log(err);
      }
    },
  },
};
</script>

<template>
  <div class="h-screen w-full">
    <Header @get-data="getData" />
    <Card
      v-if="Object.values(data).length"
      :ip="data.ip"
      :location="data.location.region"
      :timezone="data.location.timezone"
      :isp="data.isp"
    />
    <Map :data="data" />
  </div>
</template>
