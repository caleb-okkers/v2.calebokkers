<template>
  <div class="container pt-5">
   <div class="text-center">
      <h3 class="heading">Skills</h3>
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
}

.skill-div {
   width: 60%;
   gap: 10px !important;
   margin: 0 auto !important;
}

</style>