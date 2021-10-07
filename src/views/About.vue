<template>
  <section class="w-full flex flex-col items-center">

      <!-- About -->
       <div id="about-body">
          <div class="author-img flex flex-col items-center mb-8">
              <img src="@/assets/author.png" alt="" >
              <h1 class="font-bold mt-4 text-3xl md:text-4xl" >林哲弘</h1>
          </div>
          <div class="author-info">
              <div class="flex flex-col">
                <h1><i class="far fa-address-card"></i> 個人資訊簡介</h1>
                <h2>科系: {{author_info.department}}</h2>
                <h2>年齡: {{ getAge( author_info.birthday) }}</h2>
                <h2>生日: {{author_info.birthday}}</h2>
                <h2>手機: {{author_info.phone}}</h2>
              </div>
              <div class="flex flex-col">
                <h1><i class="fas fa-laptop-code"></i> 熟悉程式語言</h1>
                <h2 v-for="(item, index) in profession_Skill" :key="index">
                    {{item.skill_name}}
                    <div class="w-full bg-gray-300 h-2 relative">
                      <div class="bg-blue-400 h-2  percent" :style="{'width': item.skill_percent}"></div>
                      <label class="text-base absolute -top-6 right-0" for="">{{ item.skill_percent }}</label>
                    </div>
                </h2>
              </div>
          </div>
      </div>
     
     <div id="autobiography" class="flex flex-col justify-center items-center mb-32">
        <h1>自介</h1>
        <p>我是高雄科技大學(第一校區)資管系的學生，在大三開始自學網頁開發，從原本最基本的 HTML、CSS製作靜態網頁，又學會如何使用 Javascript、jQuery來製作動態網頁，後續了解如何使用框架、Plugin、API來讓開發過程更簡潔，現階段學習用 Laravel以及資料庫應用，慢慢擴展網頁開發的技能樹。</p>
     </div>




     <div id="side-project" class="flex flex-col justify-center items-center mb-32">
        <h1>Side Project</h1>
        <div class="project">
            <div class="project-item" v-for="(project, index) in projects" :key="index">
              <h2>{{project.name}}</h2>
              <img :src="project.img" alt="">
              <p>{{project.description}}</p>
            </div>
        </div>

     </div>
  </section>

</template>

<script>
import { reactive } from '@vue/reactivity'
export default {
    setup(){
        const author_info = reactive({
          birthday: "1999-10-21",
          department: "資訊管理系",
          phone: "0978-392-397"
        })

        const profession_Skill = reactive([
          {skill_name: 'HTML', skill_percent: '90%'},
          {skill_name: 'CSS', skill_percent: '80%'},
          {skill_name: 'JAVASCRIPT', skill_percent: '85%'},
          {skill_name: 'VUE.JS', skill_percent: '70%'},
          {skill_name: 'PHP', skill_percent: '50%'},
        ])

        const projects = reactive([
          {name: 'Project01', description: 'Desription01', img: 'https://picsum.photos/500/400?random=1'},
          {name: 'Project02', description: 'Desription02', img: 'https://picsum.photos/500/400?random=3'},
          {name: 'Project03', description: 'Desription03', img: 'https://picsum.photos/500/400?random=5'},
          {name: 'Project04', description: 'Desription04', img: 'https://picsum.photos/500/400?random=7'},
        ])

      const getAge = (birth)=>{
          birth = Date.parse(birth.replace('/-/g', "/"));
          if (birth) {
              let year = 1000 * 60 * 60 * 24 * 365;
              let now = new Date();
              let birthday = new Date(birth);
              return parseInt((now - birthday) / year);
          }
      }
      
      return {author_info, profession_Skill, projects, getAge}
    }
}
</script>

<style scoped>

  /* margin-top、fixed-height: 共兩個header-height */
 section{
    margin-top: var(--header-height);
  }


/* === About === */
  section #about-body{
    max-width: 1200px;
    width: 100%;
    z-index: -1;
    padding: 2rem;
    display: grid;
    grid-template-columns: repeat(1, 1fr);
    justify-items: center;
    align-items: center;
    margin-bottom: 8rem;
  }


  #about-body img{
    width: 240px;
    object-fit: cover;
    border-radius: 50%;
    background: radial-gradient(circle, rgba(66,101,155,1) 0%, rgba(69,129,190,1) 100%);
  }


/* Author Info */
  .author-info{
    width: 60%;
    height: 100%;
    display: grid;
    grid-template-columns: repeat(1, 1fr);
    gap: 2rem;
    justify-items: center;
  }

  /* info title */
  .author-info h1{
    font-size: var(--sub-title-size);
    font-weight: 700;
    position: relative;
    top: 0;
    left: -3rem;
  }

  /* info Content */
  .author-info h2{
    font-size: var(--general-size);
    font-weight: 700;
    margin-top: 0.5rem;
  }

/* === Autobiography === */
  #autobiography{
    max-width: 960px;
    width: 80%;
  }

  #autobiography h1,
  #side-project h1{
    font-size: var(--title-size);
    font-weight: 700;
    margin-bottom: 2rem;
  }

  #autobiography p{
    line-height: 2.5rem;
    font-size: var(--general-size);
    text-indent: 2rem;
  }

/* === Side Project === */
  #side-project{
    max-width: 1200px;
    width: 80%; 
  }  

  .project{
    display: grid;
    grid-template-columns: repeat(1, 1fr);
    gap: 4rem; 
    justify-items: center;
  }

  .project-item{
    padding: 1rem;
    border: 2px solid var(--text-color);
    border-radius: 0.5rem;
  }

  .project-item h2{
    font-size: var(--general-size);
    font-weight: 600;
    margin-bottom: 2rem;
  }

  .project-item p{
    font-size: var(--general-size);
  }


  @media screen and (min-width: 768px) {
      section #about-body{
        grid-template-columns: repeat(2, 1fr);
      }
      #about-body img{
        width: 280px;
      }

      .author-info{
        width: 100%;
        grid-template-columns: repeat(2, 1fr);
        align-items: center;
      }  
      .project{
        grid-template-columns: repeat(2, 1fr);
      }
      .project-item{
        width: 350px;
      }

  }

    @media screen and (min-width: 968px) {
      #about-body img{
          width: 360px;
      }

    .project{
        gap: 8rem;
    }
      .project-item{
          width: 400px;
      }
    }




 
</style>