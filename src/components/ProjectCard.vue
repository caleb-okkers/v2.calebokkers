<template>
    <div>
  
        <div class="card__container bd-container">
          <!-- Card Component Iterated Over -->
          <div
            v-for="(project, index) in projects"
            :key="index"
            class="card__glass" 
             data-aos="fade-up"
          >
            <img :src="project.image" alt="Project Image" class="card__img" />
  
            <div class="card__data">
              <h3 class="card__title">{{ project.name }}</h3>
              <span class="card__description">{{ project.description }}</span>
            </div>
  
            <div class="card__links">
              <a v-if="index !== 0" :href="project.github" target="_blank" class="card__button card__button--github">
                <i class="fa-brands fa-github fa-xl"></i>
              </a>
              <a
                :href="project.hosted"
                target="_blank"
                class="card__button card__button--hosted"
              >
              <img src="https://raw.githubusercontent.com/caleb-okkers/vueportfolio/16b6a8e7e2fce2e455bce1cacb5b5e84dd6e413f/src/assets/vercel-logo-svgrepo-com.svg" alt="Hosted" loading="lazy">
              </a>
            </div>
          </div>
        </div>
    </div>
  </template>
  
  <script>
  export default {
    name: "ProjectCard",
    computed: {
      // Fetches projects from Vuex store
      projects() {
        return this.$store.state.projects;
      },
    },
    mounted() {
        this.$store.dispatch('getProjects')
    }
  };
  </script>
  
  <style scoped>

  span {
    font-family: "Montserrat", sans-serif;
    font-optical-sizing: auto;
    font-weight: 300;
    font-style: normal;
    font-size: 0.85rem;
}

    .card__button img {
      width: 25px;
      border-radius: 50%;
    }

    .card__button i {
      width: 25px;
      border-radius: 50%;
    }

  /* Styles are the same as in your original component */
  @import url("https://fonts.googleapis.com/css2?family=Montserrat:wght@400;500;600&display=swap");
  
  /* :root {
    --first-color: #4d49bf;
    --second-color: #05dbf2;
    --body-color: #dfe9f2;
    --title-color: #1c1c22;
    --text-color: #58576b;
    --body-font: "Montserrat", sans-serif;
    --normal-font-size: 0.938rem;
    --h3-font-size: 1.125rem;
    --small-font-size: 0.75rem;
  } */
  
  @media screen and (min-width: 968px) {
    :root {
      --normal-font-size: 1rem;
      --h3-font-size: 1.25rem;
      --small-font-size: 0.813rem;
    }
  }
  
  *, ::before, ::after {
    box-sizing: border-box;
  }
  
  body {
    margin: 0;
    padding: 0;
    font-family: var(--body-font);
    font-size: var(--normal-font-size);
    color: #f4f4fb;
  }
  
  h3 {
    font-size: 1.4rem !important;
    margin: 0;
    background: linear-gradient(
    135deg,
    #bc26d6,
    #fe7ab6
  ); /* Your gradient colors */
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  color: #e669fb; /* Choose a color for the static text */
  }
  
  a {
    text-decoration: none !important;
  }
  
  img {
    max-width: 100%;
    height: auto;
  }
  
  .bd-container {
    max-width: 968px;
    width: calc(100% - 3rem);
    margin-left: 1.5rem;
    margin-right: 1.5rem;
  }
  
  
  
  .card__container {
    display: grid;
    gap: 1rem;
  }
  
  .card__glass {
    position: relative;
    overflow: hidden;
    text-align: center;
    padding: 2.5rem;
   
    border-radius: 5px;
    backdrop-filter: blur(10px);
    background: #111;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 1);
    color: #f4f4fb;
  }
  
  .card__img {
    width: 210px;
    height: 120px;
    border-radius: 5px;
    border: 2px solid #f4f4fb;
    margin-bottom: 1rem;
  }
  
  .card__data {
    margin-bottom: 1.5rem;
  }
  
  .card__title {
    font-size: var(--h3-font-size);
    color: var(--title-color);
    font-weight: 600;
    margin-bottom: 0.25rem;
  }
  
  .card__description {
    color: var(--text-color);
  }
  

  .card__links {
  position: absolute;
  bottom: -100%; /* Start below the card */
  left: 0;
  width: 100%;
  display: flex;
  justify-content: center;
  gap: 0.5rem;
}

.card__glass:hover .card__links {
  animation: slideUp 0.4s ease-in-out forwards;
}

.card__button {
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  padding: 0.75rem 1.5rem;
  border-radius: 0.5rem;
  color: var(--title-color);
  font-weight: 500;
  opacity: 0;
}

.card__button:hover {
  scale: 1.09;
}

.card__glass:hover .card__button--github {
  animation: fadeIn 0.4s ease-in-out 0.3s forwards;
}

.card__glass:hover .card__button--hosted {
  animation: fadeIn 0.4s ease-in-out 0.6s forwards;
}

/* Animations */
@keyframes slideUp {
  from {
    bottom: -100%;
  }
  to {
    bottom: 1rem;
  }
}

@keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
  

  
  @media screen and (min-width: 568px) {
    .card__container {
      grid-template-columns: repeat(2, 1fr);
    }
  }
  
  @media screen and (min-width: 768px) {
    .bd-container {
      margin-left: auto;
      margin-right: auto;
    }
  
    .card {
      padding: 0;
    }
  
    .card__container {
      height: 100vh;
      grid-template-columns: repeat(3, 1fr);
      align-content: center;
    }

  }

  @media (max-width: 576px) {
  p {
    font-size: 0.8rem
  }
}

  </style>
<!-- <template>
    <div>
        <section class="card">
            <div class="card__circle card__circle1"></div>
            <div class="card__circle card__circle2"></div>

            <div class="card__container bd-container">
                <div class="card__glass">
                    <img src="assets/img/img1.jpg" alt="" class="card__img">
    
                    <div class="card__data">
                        <h3 class="card__title">Alina Morton</h3>
                        <span class="card__profession">Web Developer</span>
                    </div>

                    <a href="#" class="card__button">Know more</a>
                    
                    <div class="card__social">
                        <a href="#" class="card__link"><i class='bx bxl-instagram' ></i></a>
                        <a href="#" class="card__link"><i class='bx bxl-facebook'></i></a>
                        <a href="#" class="card__link"><i class='bx bxl-twitter' ></i></a>
                    </div>
                </div>
    
                <div class="card__glass">
                    <img src="assets/img/img2.jpg" alt="" class="card__img">
    
                    <div class="card__data">
                        <h3 class="card__title">Robbi Hawkins</h3>
                        <span class="card__profession">Product Designer</span>
                    </div>

                    <a href="#" class="card__button">Know more</a>
    
                    <div class="card__social">
                        <a href="#" class="card__link"><i class='bx bxl-instagram' ></i></a>
                        <a href="#" class="card__link"><i class='bx bxl-facebook'></i></a>
                        <a href="#" class="card__link"><i class='bx bxl-twitter' ></i></a>
                    </div>
                </div>
    
                <div class="card__glass">
                    <img src="assets/img/img3.jpg" alt="" class="card__img">
    
                    <div class="card__data">
                        <h3 class="card__title">Davidson Bass</h3>
                        <span class="card__profession">Ui/Ux Design</span>
                    </div>

                    <a href="#" class="card__button">Know more</a>
    
                    <div class="card__social">
                        <a href="#" class="card__link"><i class='bx bxl-instagram' ></i></a>
                        <a href="#" class="card__link"><i class='bx bxl-facebook'></i></a>
                        <a href="#" class="card__link"><i class='bx bxl-twitter' ></i></a>
                    </div>
                </div>
            </div>
        </section>
    </div>
</template>

<script>
export default {

}
</script>

<style>

/*========== GOOGLE FONTS ==========*/
@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@400;500;600&display=swap');

/*========== VARIABLES CSS ==========*/
:root {
  /*========== Colors ==========*/
  --first-color: #4D49BF;
  --second-color: #05DBF2;
  --body-color: #DFE9F2;
  --title-color: #1C1C22;
  --text-color: #58576B;

  /*========== Font and typography ==========*/
  --body-font: 'Montserrat', sans-serif;
  --normal-font-size: .938rem;
  --h3-font-size: 1.125rem;
  --small-font-size: .75rem;
}

@media screen and (min-width: 968px) {
  :root {
    --normal-font-size: 1rem;
    --h3-font-size: 1.25rem;
    --small-font-size: .813rem;
  }
}

/*========== BASE ==========*/
*,::before,::after{
  box-sizing: border-box;
}

body{
  margin: 0;
  padding: 0;
  font-family: var(--body-font);
  font-size: var(--normal-font-size);
}

h3{
  margin: 0;
}

a{
  text-decoration: none;
}

img{
  max-width: 100%;
  height: auto;
}

.bd-container{
  max-width: 968px;
  width: calc(100% - 3rem);
  margin-left: 1.5rem;
  margin-right: 1.5rem;
}

/*========== CARD GLASS ==========*/
.card{
  position: relative;
  overflow: hidden;
  padding: 3rem 0;
  background-color: var(--body-color);
}

.card__container{
  display: grid;
  gap: 1.5rem;
}

.card__glass{
  position: relative;
  overflow: hidden;
  text-align: center;
  padding: 2.5rem;
  background: linear-gradient(130deg,
              rgba(251,251,254,.6),
              rgba(251,251,254,.2));
  box-shadow: inset 2px 2px 1px rgba(251,251,254,.3)
              inset -2px -2px 1px rgba(251,251,254,.2);
  border-radius: 1.5rem;
  backdrop-filter: blur(10px);
}

.card__img{
  width: 80px;
  height: 80px;
  border-radius: 50%;
  border: 2px solid #F4F4FB;
  margin-bottom: 1rem;
}

.card__data{
  margin-bottom: 1.5rem;
}

.card__title{
  font-size: var(--h3-font-size);
  color: var(--title-color);
  font-weight: 600;
  margin-bottom: .25rem;
}

.card__profession{
  font-size: var(--small-font-size);
  color: var(--text-color);
  font-weight: 500;
}

.card__button{
  display: inline-block;
  background: linear-gradient(130deg,
              rgba(251,251,254,.9),
              rgba(251,251,254,.2));
  padding: .75rem 1.5rem;
  border-radius: .5rem;
  color: var(--title-color);
  font-weight: 500;
  transition: .4s;
}

.card__button:hover{
  background: linear-gradient(130deg,
              rgba(251,251,254,1),
              rgba(251,251,254,.4));
}

.card__social{
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
}

.card__link{
  display: block;
  font-size: 1.35rem;
  color: var(--title-color);
  margin: 1rem 0;
  transform: translateX(-5rem);
}

.card__link:nth-child(1){
  transition: .2s;
}
.card__link:nth-child(2){
  transition: .5s;
}
.card__link:nth-child(3){
  transition: .7s;
}

.card__glass:hover .card__link{
  transform: translateX(-1.5rem);
}

.card__circle{
  position: absolute;
  width: 250px;
  height: 250px;
  background: linear-gradient(130deg,
              rgba(77,73,191,.8),
              rgba(255,255,255,.2));
  border-radius: 50%;
}

.card__circle1{
  top: 20%;
  left: -20%;
}

.card__circle2{
  bottom: -5%;
  right: -25%;
  background: linear-gradient(130deg,
              rgba(5,219,242,.8),
              rgba(255,255,255,.2));
}

/*========== MEDIA QUERIES ==========*/
@media screen and (min-width: 568px){
  .card__container{
    grid-template-columns: repeat(2, 1fr);
  }
}

@media screen and (min-width: 768px){
  .bd-container{
    margin-left: auto;
    margin-right: auto;
  }

  .card{
    padding: 0;
  }

  .card__container{
    height: 100vh;
    grid-template-columns: repeat(3, 1fr);
    align-content: center;
  }

  .card__circle1{
    left: 5%;
    top: 12%;
  }

  .card__circle2{
    right: 8%;
    bottom: 15%;
  }
}

</style> -->