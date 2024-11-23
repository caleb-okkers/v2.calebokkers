<template>
  <div class="container pt-5">
    <div class="row d-flex justify-content-center align-items-center pt-5">
      <div class="col d-flex justify-content-center align-items-center">
        <div class="about-div">
          <h3 class="heading">About</h3>
          <p class="pt-3">
            I am a compassionate person who enjoys having fun and joking around
            while knowing when to lock in and take things seriously. I hold
            values such as respect, kindness, integrity and mindfulness while I
            pride myself on being honest and transparent. I also enjoy improving
            myself and encouraging others.
          </p>
        </div>
      </div>
    </div>
    <div
      class="about-row-2 row d-flex justify-content-center align-items-center pt-5"
    >
      <div class="col text-center justify-content-center pt-5 person-column">
        <h3 class="heading">Personality</h3>
        <div class="person-div d-flex justify-content-center">
          <AboutCard
            imageSrc="https://via.placeholder.com/300"
            caption="ENTJ"
            footer="Myers & Briggs"
          />
          <AboutCard
            imageSrc="https://via.placeholder.com/300"
            caption="Type 8"
            footer="The Enneagram"
          />
          <AboutCard
            imageSrc="https://via.placeholder.com/300"
            caption="Drive"
            footer="DISC"
          />
          <AboutCard
            imageSrc="https://via.placeholder.com/300"
            caption="E. Idealist"
            footer="Big Five"
          />
          <AboutCard
            imageSrc="https://via.placeholder.com/300"
            caption="Action"
            footer="VISA"
          />
        </div>
      </div>
      <div class="col text-center justify-content-center pt-5 hobby-column">
        <h3 class="heading">Hobbies</h3>
        <div class="person-div d-flex justify-content-center">
          
          <HobbyCard
            imageSrc="https://via.placeholder.com/300"
            caption="Action"
          />
          <HobbyCard
            imageSrc="https://via.placeholder.com/300"
            caption="Action"
          />
          <HobbyCard
            imageSrc="https://via.placeholder.com/300"
            caption="Action"
          />
          <HobbyCard
            imageSrc="https://via.placeholder.com/300"
            caption="Action"
          />
          <HobbyCard
            imageSrc="https://via.placeholder.com/300"
            caption="Action"
          />
          <HobbyCard
            imageSrc="https://via.placeholder.com/300"
            caption="Action"
          />
        </div>
      </div>
    </div>

    <div class="row d-flex justify-content-center align-items-center pt-5">
    <SkillsComp/>
    </div>
  </div>
</template>

<script>
import AboutCard from './AboutCard.vue';
import HobbyCard from './HobbyCard.vue';
import SkillsComp from './SkillsComp.vue';

export default {
  components: {
    AboutCard,
    HobbyCard,
    SkillsComp
  }
};
</script>

<style>
.heading {
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

.about-div {
  text-align: center;
  width: 65%;
}

.about-row-2 {
  width: 75%;
  margin: 0 auto !important;
}

.person-div {
  flex-wrap: wrap;
  gap: 20px;
}

.person-column {
  margin-right: 2rem;
}
.hobby-column {
  margin-left: 2rem;
}

</style>