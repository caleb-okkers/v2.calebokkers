<template>
  <div class="container pt-5">
   <div class="text-center">
      <h3 class="heading">Skills</h3>
      <p class="subtext pt-3">What I do have are a particular set of skills ...</p>
   </div>
   <div class="row justify-content-center align-items-center pt-4 skill-div">

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
  font-weight: bold; /* Optional: make the static text bold */
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

</style>