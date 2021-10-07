<template>
  <Navigation/>

  <router-view></router-view>

  <!--========== SCROLL TOP ==========-->
    <a href="#" class="scrolltop" id="scroll-top" title="回到最上面">
        <i class="fas fa-chevron-up"></i>
    </a>

  <Footer/>
</template>

<script>
import Navigation from '@/components/Navigation';
import Footer from '@/components/Footer';
export default {
  components:{
    Navigation: Navigation,
    Footer: Footer,
  },

  setup(){
   /*==================== SHOW SCROLL TOP ====================*/ 
  function scrollTop(){
      const scrollTop = document.getElementById('scroll-top');
      // When the scroll is higher than 560 viewport height, add the show-scroll class to the a tag with the scroll-top class
      if(this.scrollY >= 560) scrollTop.classList.add('show-scroll'); else scrollTop.classList.remove('show-scroll')
  }
  window.addEventListener('scroll', scrollTop)
    return {}
  }
}
</script>



<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins&display=swap');
  *{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: 'Poppins', sans-serif;
    scroll-behavior: smooth;
  }

  a{
    text-decoration: none;
  }
  li{
    list-style: none;
  }

  :root{
        /*========== Colors ==========*/
        /* Change favorite color to match images */
        /*Green dark 190 - Green 171 - Grren Blue 200*/
        --hue-color: 171;
        --header-height: 4rem;
        --body-bg-color: hsl(var(--hue-color), 100%, 99%);
        --body-bg-color-alt: hsl(var(--hue-color), 20%, 80%);
        --nav-bg-color: hsl(var(--hue-color), 5%, 99%);
        --text-color: hsl(var(--hue-color), 24%, 35%);
        --title-color: hsl(var(--hue-color), 24%, 35%);
        --text-light-color: hsl(var(--hue-color), 8%, 60%);

        /* Font Size */
        --title-size: 1.4rem;
        --sub-title-size: 1.15rem;
        --general-size: 1rem;
        --content-size: 0.825rem;

        /* Shadow */
        --section-shadow: 1px 0 4px rgba(14, 55, 63, 0.15);

    }

    body{
        background: var(--body-bg-color);
        color: var(--text-color);
        transition: .5s;
    }
    
    /*========== Variables Dark theme ==========*/
    body.dark-theme {
        --body-bg-color: hsl(var(--hue-color), 29%, 12%);
        --body-bg-color-alt: hsl(var(--hue-color), 25%, 40%);
        --nav-bg-color: hsl(var(--hue-color), 29%, 22%);
        --text-color: hsl(var(--hue-color), 8%, 75%);
        --title-color: hsl(var(--hue-color), 24%, 95%);        
        /* Shadow */
        --section-shadow:  1px -1px 4px rgba(209, 221, 221, 0.836);
    }

    
    @media screen and (min-width: 768px) {
      :root{
        --title-size: 1.5rem;
        --sub-title-size: 1.25rem;
        --general-size: 1rem;
        --content-size: 0.85rem;
      }
    }
    @media screen and (min-width: 968px) {
      :root{
        --title-size: 1.75rem;
        --sub-title-size: 1.5rem;
        --general-size: 1.25rem;
        --content-size: 1rem;
      }
    }
    
  /* Change background header */
  .scroll-header{
    box-shadow: 0 2px 4px rgba(0,0,0,.1);
  }

  /* Scroll top */
  .scrolltop{
    position: fixed;
    right: 1rem;
    bottom: -20%;
    display: flex;
    justify-content: center;
    align-items: center;
    padding: .625rem;
    background-color: var(--body-bg-color) ;
    border: 2px solid var(--text-light-color) ;
    border-radius: .4rem;
    z-index: 100;
    transition: .4s;
    visibility: hidden;
  }

  .scrolltop__icon{
    font-size: 1.8rem;
    color: var(--text-light-color);
  }

  /* Show scrolltop */
  .show-scroll{
    visibility: visible;
    bottom: 2.5rem;
  }

  
</style>