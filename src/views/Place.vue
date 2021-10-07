<template>
  <section class="w-full p-4 ">
      <h1>Place</h1>
  </section>
</template>

<script>
export default {

}
</script>

<style scoped>
 section{
    /* margin-top、fixed-height: 共兩個header-height */
    min-height: calc(100vh - var(--header-height));
    margin-top: var(--header-height);
  }
</style>
