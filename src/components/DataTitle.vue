<template>
  <div class="text-center">
    <h2 class="text-3xl font-bold">{{ text }}</h2>
    <div class="text-2xl mt-4 mb-10">
      {{ timestamp }}
    </div>
  </div>
</template>

<script lang="ts">
/* eslint-disable */
import { defineComponent, computed } from "vue";
import dayjs from "dayjs";

export default defineComponent({
  name: "DataTitle",
  props: {
    text: String, //
    dataDate: Date
  },

  setup(props) {
    const timestamp = computed(() => dayjs(props.dataDate).format("DD-MM-YYYY HH:mm:ss"));

    return {
      timestamp
    };
  }
});
</script>
