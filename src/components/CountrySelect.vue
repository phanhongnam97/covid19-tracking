<template>
  <select
  @change="onChange"
  v-model="selected" class="form-select mt-10 block w-full border p-3 rounded">
    <option value="0">Select Country</option>
    <option v-for="country in countries" :key="country.ID" :value="country.ID">{{
      country.Country
    }}</option>
  </select>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';

export default defineComponent({
  name: 'CountrySelect',

  props: {
    countries: Array,
  },

  setup(props, { emit }) {
    const selected = ref(0);
    const onChange = () => {
      const country = props.countries?.find((item: any) => item.ID === selected.value);

      emit('get-country', country);
    };

    return {
      selected,
      onChange,
    };
  },
});
</script>

<style></style>
