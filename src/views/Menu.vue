<template>
  <section class="w-full p-4">
      <div id="menu-body" class="w-full flex justify-center relative" style="z-index: -1;">
        <h1 class="text-2xl absolute top-1/2 z-10 transform -translate-y-1/2 font-bold">Menu</h1>
        <img src="@/assets/food.jpg" alt="food" class="w-1/2" >
      </div>

  </section>
</template>

<script>
export default {

}
</script>
<style scoped>
   /* margin-top、fixed-height: 共兩個header-height */
 section{
    margin-top: var(--header-height);
  }
  section #menu-body{
    height: calc(100vh - var(--header-height) );
  }

</style>