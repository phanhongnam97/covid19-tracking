<template>
  <the-header />
  <div class="container mx-auto flex-grow">
    <router-view />
  </div>
  <the-footer />
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import TheHeader from '@/components/TheHeader.vue';
import TheFooter from '@/components/TheFooter.vue';

export default defineComponent({
  components: {
    TheHeader,
    TheFooter,
  },
});
</script>

<style lang="scss">
html, body {
  height: 100vh;
}

#app {
  height: 100%;
  display: flex;
  flex-direction: column;
}
</style>
