<template>
 <header id="header" class="w-full fixed top-0 left-0">
    <nav>
        <!-- Logo -->
        <a href="#" class="nav__logo font-bold text-2xl">Hong Food</a>

        <!-- Menu -->
        <div class="nav__menu" :class="is_ShowMenu ? 'show_menu' : ''">
            <ul class="nav__list">
                <li class="nav__item" v-for="(item, index) in nav_item" :key="index">
                    <router-link :to="item.href" class="nav__link" @click="is_ShowMenu = false"
                        :class="$route.path == item.href ? 'active-link' : ''">
                        {{ item.title }}
                    </router-link>
                </li>
            </ul>

            <!-- Darkness -->
            <div class="nav__dark">
                <span class="change-theme-name">{{is_Dark ? 'Dark mode' : 'Light mode'}}</span>
                <i class="ml-2" :class="is_Dark ? 'far fa-sun' : 'far fa-moon'" @click="change_Dark_Mode"></i>
            </div>

            <!-- Cancel -->
            <i class="fas fa-times nav__close" @click="is_ShowMenu = false"></i>
        </div>

        <!-- Toggle Menu -->
        <div class="nav__toggle" >
            <i class="fas fa-bars" @click="is_ShowMenu = true;"></i>
        </div>
    </nav>
</header>
</template>

<script>
import { reactive, ref } from 'vue'
export default {

    setup(){   
        const nav_item =  reactive([
            { href: "/", title: 'Home', },
            { href: "/about", title: 'About', },
            { href: "/menu", title: 'Menu', },
            { href: "/place", title: 'Place', },
        ]);

        const is_ShowMenu = ref(false);
        const is_Dark = ref(false);

        const change_Dark_Mode = ()=>{
            is_Dark.value = !is_Dark.value
            if(is_Dark.value){
                document.body.classList.add('dark-theme');
            }else{
                document.body.classList.remove('dark-theme');
            }
        }

        return {nav_item, is_ShowMenu, is_Dark, change_Dark_Mode}
    }

}
</script>

<style>
    nav{
        background: var(--body-bg-color);
        color: var(--text-color);
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 1rem;
        height: var(--header-height);
        box-shadow: var(--section-shadow);
        z-index: 100;
    }


    @media screen and (max-width: 767px) {
        .nav__menu {
            position: fixed;
            background-color: var(--nav-bg-color);
            top: 0;
            right: -100%;
            width: 70%;
            height: 100%;
            box-shadow: -1px 0 4px rgba(14, 55, 63, 0.15);
            padding: 3rem;
            transition: .6s;
        }
        .nav__list{
            display: flex;
            flex-direction: column;
            row-gap: 2.5em;
            text-transform: uppercase;
        }
        
        .nav__toggle, .nav__close{
            font-size: 1.5rem;
            position: absolute;
            top: .75rem;
            right: .75rem;
            cursor: pointer;
        }
        
        .nav__dark{
            position: absolute;
            bottom: 3rem;
            cursor: pointer;
        }

        /* 展開 */
        .show_menu{
            right: 0;
            z-index: 10; 
        }
    }


    @media screen and (min-width: 768px) {
        nav .nav__menu{
            display: flex;
        }

        .nav__menu ul.nav__list{
            display: flex;
            column-gap: 3rem;
        }

        /* 文字不要顯示(只有在 width < 768 顯示) */
        .nav__menu .nav__dark{
            margin-left: 1.5rem;
        }
        .nav__menu .nav__dark span{
            display: none;
        }
        /* 隱藏功能按鈕 */
        nav .nav__toggle, .nav__close{
            display: none;
        }
    }
    
    .nav__dark i{
        cursor: pointer;
    }

    .nav__item{
        position: relative;
    }

    /* Active link */
    .active-link {
        position: relative;
        color: var(--title-color);
    }

    .active-link::before{
        content: '';
        height: 2px;
        background: var(--text-color);
        position: absolute;
        bottom: -0.25rem;
        width: 100%;
    }

   


</style>