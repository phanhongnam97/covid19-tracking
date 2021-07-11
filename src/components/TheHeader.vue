<template>
  <header class="text-center bg-blue-800 text-white p-4 mb-10">
    <div class="text-3xl md:text-5xl font-bold mb-3">
      <i class="fa fa-viruses"></i>
      Covid-19 Tracker
      </div>
    <p>API by <a href="https://covid19api.com" target="_blank" class="text-blue-300">covid19api.com</a></p>
  </header>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';

@Options({
  name: 'Header',

})
export default class Header extends Vue {
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

</style>
