<template>
  <div class="container pt-5">
   <div class="text-center">
      <h3 class="heading">Skills</h3>
      <p class="subtext pt-3">What I do have are a very particular set of skills ...</p>
   </div>
   <div class="row justify-content-center align-items-center pt-5 skill-div">

      <SkillCard v-for="skill in cardSkills" :key="skill.name" :imageSrc="skill.icon"
      :caption="skill.name">

      </SkillCard>
   </div>
  </div>
</template>

<script>
import SkillCard from './SkillCard.vue'

export default {
    name: "SkillsComp",
    components: {
        SkillCard
    },
    computed: {
        cardSkills() {
          return this.$store.state.cardSkills
        }
    },
    mounted() {
        this.$store.dispatch('getCardSkills')
    }
}
</script>

<style>

.heading {
   text-align: center !important;
   font-size: 36px;
  display: inline-block;
  background: linear-gradient(
    135deg,
    #bc26d6,
    #fe7ab6
  ); /* Your gradient colors */
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  color: #e669fb; /* Choose a color for the static text */
  font-weight: 600; /* Optional: make the static text bold */
  font-family: "Poppins";
}

.skill-div {
   width: 60%;
   gap: 10px !important;
   margin: 0 auto !important;
}

p {
    font-size: 1rem;
    font-family: "Montserrat", sans-serif;
    font-optical-sizing: auto;
    font-weight: 300;
    font-style: normal;
}

@media (min-width: 1850px) {


  .skill-div {
    width: 45%;
  }
}
@media (min-width: 1670px) and (max-width: 1849px) {


  .skill-div {
    width: 55%;
  }
}

/* Tablet and smaller screens (max-width: 1024px) */
@media (max-width: 1024px) {
  .heading {
    font-size: 28px;
  }

  p {
    font-size: 0.95rem;
  }

  .skill-div {
    width: 80%;
  }
}

/* Mobile screens (max-width: 768px) */
@media (max-width: 768px) {
  .heading {
    font-size: 24px;
  }

  p {
    font-size: 0.9rem;
  }

  .skill-div {
    width: 90%;
  }
}

/* Small mobile screens (max-width: 576px) */
@media (max-width: 576px) {

  p {
    font-size: 0.8rem;
  }

  .skill-div {
    width: 100%;
    gap: 10px;
  }
}

@media (max-width: 768px) {
  .heading {
    font-size: 36px;
  }
}
@media (max-width: 576px) {
  .heading {
    font-size: 28px;
  }
}

</style>