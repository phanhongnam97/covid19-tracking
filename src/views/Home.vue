<template>
  <main v-if="!states?.loading">
    <data-title :text="states.title" :dataDate="states.dataDate" />
    <data-boxes :stats="states.stats" />
    <country-select :countries="states.countries" @get-country="getCountryData" />
  </main>
  <main class="flex flex-col align-center justify-center text-center" v-else>
    <div class="text-gray-500 text-3xl mt-10 mb-6">
      Fetching data...
    </div>
    <img :src="states.loadingImage" class="w-24 m-auto" alt="loading" />
  </main>
</template>

<script lang="ts">
/* eslint-disable */
import { defineComponent, reactive } from "vue";
import DataTitle from "@/components/DataTitle.vue";
import DataBoxes from "@/components/DataBoxes.vue";
import CountrySelect from "@/components/CountrySelect.vue";

const loadingImage = require("@/assets/earth.svg");

export default defineComponent({
  components: { DataTitle, DataBoxes, CountrySelect },

  setup() {
    const states = reactive({
      loading: true, //
      title: "Global", //
      dataDate: "", //
      stats: {}, //
      countries: [],
      loadingImage
    });

    const fetchCovidData = async () => {
      const res = await fetch("https://api.covid19api.com/summary");
      const data = res.json();

      return data;
    };

    const getCountryData = (country: any) => {
      states.stats = country;
      states.title = country.Country;
    };

    fetchCovidData().then(data => {
      states.dataDate = data.Date;
      states.stats = data.Global;
      states.countries = data.Countries;
      states.loading = false;
    });

    return { states, getCountryData };
  }
});
</script>
