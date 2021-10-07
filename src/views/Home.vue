<template>
  <section class="w-full">
       <div id="home-body" class="w-full flex justify-center relative mb-32">
        <div class="absolute top-1/2 z-10 transform -translate-y-1/2 font-bold flex flex-col items-center p-12">
          <h1 class="text-3xl md:text-5xl">美食天堂</h1>
          <h3 class="text-2xl md:text-3xl mt-2">Enjoying</h3>
          <p class="text-base md:text-lg mt-4">Lorem ipsum dolor sit amet consectetur, adipisicing elit. Dolorem, doloribus vel quibusdam at a dolores alias sed qui saepe dolore!</p>
        </div>
        <img src="@/assets/food.jpg" alt="food" class="md:w-full opacity-40 object-cover" >
      </div>

  </section>

    <section class="w-full flex flex-col items-center">
        <div id ="info" class="text-center">
          <h1 class="font-title">Hot Product Info</h1>
          <div id="info-item" class="w-full grid gap-2">
                <img src="@/assets/food01.jpg" alt="">
                <div class="flex flex-col p-4">
                  <h1 class="product-title">美味鬆餅</h1>
                  <p class="product-desc">Lorem ipsum dolor sit amet consectetur adipisicing elit. Dolores neque, accusamus dolor labore expedita sit! Tenetur blanditiis nobis eius inventore non repellat dolore consequatur doloremque!</p>
                </div>
          </div>

          <div id="info-item" class="w-full grid gap-2">
                <div class="flex flex-col p-4">
                  <h1 class="product-title">清新氣泡水果汁</h1>
                  <p class="product-desc">Lorem, ipsum dolor sit amet consectetur adipisicing elit. Magnam, voluptas et libero ratione odit adipisci eos? Sunt voluptatibus eligendi dolor voluptates eveniet mollitia fuga dicta unde suscipit, eos repellat commodi.</p>
                </div>
                <img src="@/assets/food02.jpg" alt="">
          </div>
          <div id="info-item" class="w-full grid gap-2">
                <img src="@/assets/food03.jpg" alt="">
                <div class="flex flex-col p-4">
                  <h1 class="product-title">香嫩肉丸子</h1>
                  <p class="product-desc">Lorem ipsum dolor sit amet consectetur adipisicing elit. Dolores neque, accusamus dolor labore expedita sit! Tenetur blanditiis nobis eius inventore non repellat dolore consequatur doloremque!</p>
                </div>
          </div>

          <div id="info-item" class="w-full grid gap-2">
                <div class="flex flex-col p-4">
                  <h1 class="product-title">夏威夷美味披薩</h1>
                  <p class="product-desc">Lorem, ipsum dolor sit amet consectetur adipisicing elit. Magnam, voluptas et libero ratione odit adipisci eos? Sunt voluptatibus eligendi dolor voluptates eveniet mollitia fuga dicta unde suscipit, eos repellat commodi.</p>
                </div>
                <img src="@/assets/food04.jpg" alt="">
          </div>



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
  section #home-body{
    height: calc(100vh - var(--header-height) );
    z-index: -1;
  }

  .font-title{
    font-size: var(--title-size);
    font-weight: 700;
    margin: 5rem 0 4rem;
  }

  #info{
      max-width: 1024px;
      width: calc(100% - 2rem);
  }

  #info-item{
    grid-template-columns: repeat(2, 1fr);
    gap: 1.5rem;
    margin-bottom: 6rem;
    padding: 0 2rem;
  }

  #info-item img{
    width: 455px;
    justify-self: center;
    align-self: center;
}

  .product-title{
    font-size: var(--sub-title-size);
    margin-bottom: 1rem;
    font-weight: bold;
  }

  .product-desc{
    font-size: var(--content-size);
    line-height: 1.5rem;
  }


  @media screen and (min-width: 768px) {
      #info-item{
        padding: 0 4rem;
    }
  }



 
</style>