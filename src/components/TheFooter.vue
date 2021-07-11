<template>
  <footer
    class="flex flex-col justify-center items-center text-center
    w-full h-16 bg-blue-800 text-white bottom-0 mt-10 p-4">
        <span>Author: PHNam</span>
        <span>Copyright © {{ year }}. All rights reserved</span>
  </footer>
</template>

<script>

export default {
  name: 'TheFooter',
  data() {
    return {
      year: new Date().getFullYear(),
    };
  },
};
</script>

<style>

</style>
