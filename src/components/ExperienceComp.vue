<template>
    <div class="container" id="experience-section">
      <div class="experience-section text-center" v-if="work && work.length">
    <h2 class="section-heading heading">Work Experience</h2>
    <p class="subtext pt-3">It's not about the destination ... it's about the experience.</p>
    
    <div class="job-list">
      <ul class="job-tabs">
        <li
          v-for="(job, index) in work"
          :key="job.company"
          :class="{ active: selectedJobIndex === index }"
          @click="selectJob(index)"
        >
          <img :src="job.image" alt="company logo" class="company-logo"> {{ job.company }}
        </li>
      </ul>

      <div class="job-details justify-content-center align-content-center">
        <h3>
          {{ work[selectedJobIndex].position }} <span>@ {{ work[selectedJobIndex].company }}</span>
        </h3>
        <p class="job-duration">{{ work[selectedJobIndex].year }}</p>
        <p>{{ work[selectedJobIndex].description }}</p>
      </div>
    </div>
  </div>
  </div>


  </template>
  <script>
  export default {
    data() {
      return {
        selectedJobIndex: 0
      };
    },
    computed: {
      work() {
        return this.$store.state.work;
      }
    },
    mounted() {
      this.$store.dispatch("getWork");
    },
    methods: {
      selectJob(index) {
        this.selectedJobIndex = index;
      }
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

  .experience-section {
    margin: 0 auto;
    max-width: 1000px;
    padding: 50px 0;
  }
  
  .section-heading {
    text-align: center;
  }


  .heading {
    text-align: center !important;
  font-size: 36px;
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
  
  .subtext {
    text-align: center;
    margin-bottom: 40px;
  }
  
  .job-list {
    display: flex;
    justify-content: space-between;
  }
  
  .job-tabs {
    list-style: none;
    padding: 0;
    width: 30%;
    display: flex;
    flex-direction: column;
  }
  
  .job-tabs li {
    padding: 15px;
    cursor: pointer;
    color: #666;
    border-left: 2px solid transparent;
    display: flex;
    align-items: center;
    transition: all 0.3s ease;
    font-size: 1rem;
    font-family: "Montserrat", sans-serif;
    font-optical-sizing: auto;
    font-weight: 300;
    font-style: normal;
  }
  
  .job-tabs li.active {
    background: linear-gradient(
    135deg,
    #bc26d6,
    #fe7ab6
  ); /* Your gradient colors */
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  color: #e669fb; /* Choose a color for the static text */
    border-left: 2px solid #bc26d6;
  }
  

  .company-logo {
    width: 30px;
    height: 30px;
    margin-right: 10px;
  }
  

  .job-details {
    width: 65%;
  }
  
  .job-details h3 {
    font-size: 1.75rem;
    background: linear-gradient(
    135deg,
    #bc26d6,
    #fe7ab6
  ); /* Your gradient colors */
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  color: #e669fb; /* Choose a color for the static text */
    font-family: "Poppins";
    
  }
  
  .job-details .job-duration {
    font-size: 1rem;
    margin-bottom: 20px;
  }
  
  .job-details p {
    font-weight: 200 !important;
  }

  @media (max-width:475px) {
    .job-tabs {
    width: 50%;
    display: flex;
    flex-direction: column;
  }

  .job-tabs li {
  align-items: left;
  text-align: left;
  font-size: 12px;
}

.job-details  {
    color: #333;
    text-align: left;
    padding-left: 2rem ;
    font-size: 0.8rem;
  }

  .job-details h3  {
    font-size: 1.2rem;
  }

}

@media (max-width: 576px) {
  p {
    font-size: 0.8rem
  }
}

.company-logo {
  width: 30px;
  height: 30px;
  margin-right: 10px;
  filter: grayscale(100%);
  transition: filter 0.3s ease;
}

.job-tabs li.active .company-logo {
  filter: none;
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
