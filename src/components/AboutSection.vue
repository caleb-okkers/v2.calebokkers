<template>
  <div class="container pt-5">
    <div class="row d-flex justify-content-center align-items-center pt-5">
      <div class="col d-flex justify-content-center align-items-center">
        <div class="about-div">
          <h3 class="heading">About</h3>
          <p class="pt-4">
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
        <div class="person-div pt-4 d-flex justify-content-center">
          <AboutCard
            imageSrc="https://github.com/caleb-okkers/first_api/blob/main/images/icons8-knight-helmet-208.png?raw=true"
            caption="ENTJ"
            footer="Myers & Briggs"
          />
          <AboutCard
            imageSrc="https://github.com/caleb-okkers/first_api/blob/main/images/icons8-number-8-100.png?raw=true"
            caption="Type 8"
            footer="The Enneagram"
          />
          <AboutCard
            imageSrc="https://github.com/caleb-okkers/first_api/blob/main/images/icons8-d-100%20(1).png?raw=true"
            caption="Drive"
            footer="DISC"
          />
          <AboutCard
            imageSrc="https://github.com/caleb-okkers/first_api/blob/main/images/icons8-accurate-100.png?raw=true"
            caption="E. Idealist"
            footer="Big Five"
          />
          <AboutCard
            imageSrc="https://github.com/caleb-okkers/first_api/blob/main/images/icons8-a-100.png?raw=true"
            caption="Action"
            footer="VISA"
          />
          <AboutCard
            imageSrc="https://github.com/caleb-okkers/first_api/blob/main/images/icons8-ok-hand-100.png?raw=true"
            caption="Optimist"
            footer="High 5"
          />
        </div>
      </div>
      <div class="col text-center justify-content-center pt-5 hobby-column">
        <h3 class="heading">Interests</h3>
        <div class="person-div pt-4 d-flex justify-content-center">
          
          <HobbyCard
            imageSrc="https://github.com/caleb-okkers/first_api/blob/main/images/icons8-football-100%20(1).png?raw=true"
            caption="Football"
          />
          <HobbyCard
            imageSrc="https://github.com/caleb-okkers/first_api/blob/main/images/icons8-boxing-glove-100.png?raw=true"
            caption="MMA"
          />
          <HobbyCard
            imageSrc="https://github.com/caleb-okkers/first_api/blob/main/images/icons8-formula-1-100.png?raw=true"
            caption="Formula 1"
          />
          <HobbyCard
            imageSrc="https://github.com/caleb-okkers/first_api/blob/main/images/art-gallery-svgrepo-com.png?raw=true"
            caption="Art"
          />
          <HobbyCard
            imageSrc="https://github.com/caleb-okkers/first_api/blob/main/images/movies-and-tv-svgrepo-com.png?raw=true"
            caption="Movies"
          />
          <HobbyCard
            imageSrc="https://github.com/caleb-okkers/first_api/blob/main/images/family-svgrepo-com%20(1).png?raw=true"
            caption="Family"
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

<style scoped>

p {
    font-size: 1rem;
    font-family: "Montserrat", sans-serif;
    font-optical-sizing: auto;
    font-weight: 300;
    font-style: normal;
}

.heading {
  font-size: 36px;
  display: inline-block;
  background: linear-gradient(
    135deg,
    #bc26d6,
    #fe7ab6
  ); 
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  color: #e669fb; 
  font-weight: 600; 
  font-family: "Poppins";
}

.about-div {
  text-align: center;
  width: 65%;
}
.about-div p {
  text-align: center;
}

.about-row-2 {
  width: 68%;
  margin: 0 auto !important;
}

.person-div {
  flex-wrap: wrap;
  gap: 20px;
}

.person-column {
  margin-right: 3.5rem;
}
.hobby-column {
  margin-left: 3.5rem;
}


.person-div {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
  justify-content: center;
}


@media (max-width: 576px) {

  .container {
    padding-top: 2rem !important;
  }

  .row {
    padding-top: 0 !important;
  }

  .about-row-2 {
    width: 100%;
  }

  .about-div {
  text-align: center;
  width: 78%;
}
  .about-div p {
  text-align: left;
}
  

  .person-column,
  .hobby-column {
    width: 100% !important;
    margin: 0;
  }

  .person-div,
  .hobby-div {
    width: 100%;
    margin: 0;
  }

  .person-div,
  .hobby-column .person-div {
    display: grid;
    grid-template-columns: repeat(3, 1fr); /* 3 cards per row */
    gap: 15px;
    justify-items: center;
  }

  
  .about-row-2 {
    display: flex;
    flex-direction: column;
  }

  .person-column {
    order: 1;
  }

  .hobby-column {
    order: 2;
    padding-bottom: 3rem;
  }


  p {
    font-size: 0.8rem
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