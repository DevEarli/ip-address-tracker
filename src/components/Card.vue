<script>
export default {
  props: {
    ip: {
      type: String,
      default: "-",
    },
    location: {
      type: String,
      default: "-",
    },
    timezone: {
      type: String,
      default: "-",
    },
    isp: {
      type: String,
      default: "-",
    },
  },
};
</script>

<template>
  <div
    class="bg-white rounded-lg py-5 md:py-10 px-6 w-10/12 md:w-fit md:max-h-40 md:flex md:flex-row flex-column md:items-stretch items-center md:text-left text-center inset-x-1/2 absolute z-[1000] translate-y-[-30%] md:translate-y-[-50%] translate-x-[-50%] overflow-scroll"
  >
    <div class="md:pr-10 mb-3 flex-1 h-auto border-grey-500 md:border-r-2">
      <p class="text-gray-500 text-xs font-black mb-2">IP ADDRESS</p>
      <p v-text="ip" class="font-bold text-md md:text-2xl"></p>
    </div>
    <div class="md:px-6 mb-3 min-w-min border-grey-500 md:border-r-2">
      <p class="text-gray-500 text-xs font-bold mb-2">LOCATION</p>
      <p v-text="location" class="font-bold text-md md:text-2xl"></p>
    </div>
    <div
      class="md:px-6 mb-3 min-w-min md:w-[200px] border-grey-500 md:border-r-2"
    >
      <p class="text-gray-500 text-xs font-bold mb-2">TIMEZONE</p>
      <p v-text="timezone" class="font-bold text-md md:text-2xl"></p>
    </div>
    <div class="md:px-6 mb-3 min-w-min md:w-[200px] border-grey-500">
      <p class="text-gray-500 text-xs font-bold mb-2">ISP</p>
      <p v-text="isp" class="font-bold text-md md:text-2xl"></p>
    </div>
  </div>
</template>
