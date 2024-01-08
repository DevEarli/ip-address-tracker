<script>
import Card from "../components/Card.vue";

export default {
  components: {
    Card,
  },
  data() {
    search: "";
  },
  methods: {
    getData() {
      this.$emit("get-data", this.search);
    },
  },
};
</script>

<template>
  <div
    class="bg-[url('/pattern-bg-mobile.png')] lg:bg-[url('/pattern-bg-desktop.png')] w-full h-60"
  >
    <h1 class="text-white text-2xl font-bold py-5 text-center">
      IP Address Tracker
    </h1>
    <div class="flex justify-center">
      <input
        class="w-9/12 md:w-3/5 lg:w-2/6 py-3 px-4 rounded-s-xl outline-none"
        type="text"
        placeholder="Search for any IP address or domain"
        v-model="search"
      />
      <button
        class="bg-black hover:opacity-70 py-3 px-4 rounded-e-xl"
        @click="getData"
      >
        <img src="/icon-arrow.svg" alt="" />
      </button>
    </div>
    <!-- <Card /> -->
  </div>
</template>
