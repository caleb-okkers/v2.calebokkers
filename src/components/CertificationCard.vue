<template>
  <div>
    <div class="card__container bd-container">
      <div
        v-for="(cert, index) in displayedCerts"
        :key="index"
        class="card__glass"
        data-aos="fade-up"
      >
        <img :src="cert.image" :alt="cert.name" class="card__img" />
        
        <div class="card__data">
          <h3 class="card__title">{{ cert.name }}</h3>
        </div>

        <!-- Only one button -->
        <div class="card__links">
          <button class="btn" @click="selectedCert = cert">
            <span class="text-light">View</span>
          </button>
        </div>
      </div>
    </div>

    <!-- <button v-if="!showAll" class="show-all-btn" @click="showAll = true">
      Show All
    </button> -->

        <!-- Show More / Show Less -->
    <div class="text-center mt-4">
      <button
        v-if="!showAll"
        @click="showAll = true"
        class="btn"
      >
        <span class="text-light">Show more</span>
      </button>
      <button
        v-else
        @click="showAll = false"
        class="btn"
      >
        <span class="text-light">Show less</span>
      </button>
    </div>



    <!-- Modal -->
    <div v-if="selectedCert" class="modal" @click.self="closeModal">
      <div class="modal-content">
        <img :src="selectedCert.image" :alt="selectedCert.name" />
        <h3 class="card__title">{{ selectedCert.name }}</h3>
        <button class="btn" @click="closeModal"><span class="text-light">Close</span></button>
      </div>
    </div>
</div>
</template>

<script>
export default {
  name: "CertificationCards",
  data() {
    return {
      showAll: false,
      selectedCert: null,
    };
  },
  computed: {
    certifications() {
      return this.$store.state.certifications || [];
    },
    displayedCerts() {
      return this.showAll
        ? this.certifications
        : this.certifications.slice(0, 3);
    },
  },
  methods: {
    closeModal() {
      this.selectedCert = null;
    },
  },
  mounted() {
    this.$store.dispatch("getCertifications");
  },
};
</script>

<style scoped>
/* Buttons */

.btn {
  position: relative;
  overflow: hidden;
  background-color: var(--primary-dark) !important;
  color: #fff !important;
  border-color: #fff !important;
  text-align: center !important;
  padding: 4px 15px;
  cursor: pointer;
  transition: color 0.5s ease;
  border-radius: 0 !important;
  z-index: 1;
  will-change: color; 
  font-size: 0.8rem;
    font-family: "Montserrat", sans-serif;
    font-optical-sizing: auto;
    font-weight: 300;
    font-style: normal;
  border-radius: 4px !important;
}

.btn::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: linear-gradient(135deg, #bc26d6, #bc26d6, #fe7ab6); 
  z-index: 0;
  transition: transform 0.5s ease;
  transform: scaleX(0);
  transform-origin: left;
  backface-visibility: hidden; 
  will-change: transform; 
}

.btn:hover::before {
  transform: scaleX(1);
}

/* .btn:hover,
.about-button:hover::before {
  color: #001a34 !important; 
} */

.btn span,
.about-button span {
  position: relative;
  z-index: 2;
  backface-visibility: hidden; 
  will-change: color; 
  color: #fff;
  
}

.btn:hover span,
.about-button:hover span {
  position: relative;
  z-index: 2;
  backface-visibility: hidden; 
  will-change: color; 
  color: #fff !important;
  
}

/* original project card styling */
span {
  font-family: "Montserrat", sans-serif;
  font-weight: 300;
  font-size: 0.75rem;
}

@import url("https://fonts.googleapis.com/css2?family=Montserrat:wght@400;500;600&display=swap");

*, ::before, ::after {
  box-sizing: border-box;
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
  padding: 2rem;
  border-radius: 5px;
  backdrop-filter: blur(10px);
  background: #111;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 1);
  color: #f4f4fb;
}

/* .card__img {
  width: 210px;
  height: 120px;
  border-radius: 5px;
  border: 2px solid #f4f4fb;
  margin-bottom: 1rem;
} */

.card__img {
  width: 100%;
  height: 150px; /* or whatever fixed height works for your layout */
  object-fit: contain;
  object-position: center;
  border-radius: 5px;
  margin-bottom: 1rem;
}

.card__data {
  margin-bottom: 1.5rem;
}

.card__title {
  font-size: 1.25rem;
  font-weight: 600;
  margin-bottom: 0.25rem;
  background: linear-gradient(135deg, #bc26d6, #fe7ab6);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

.card__links {
  position: absolute;
  bottom: -100%;
  left: 0;
  width: 100%;
  display: flex;
  justify-content: center;
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
  background: #bc26d6;
  color: white;
  font-weight: 500;
  opacity: 0;
  border: none;
  cursor: pointer;
}

.card__button:hover {
  scale: 1.09;
}

.card__glass:hover .card__button--view {
  animation: fadeIn 0.4s ease-in-out 0.3s forwards;
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

/* Responsive */
/* @media screen and (min-width: 568px) {
  .card__container {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media screen and (min-width: 768px) {
  .card__container {
    grid-template-columns: repeat(3, 1fr);
  } 
}*/

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
      /* height: 100vh; */
      grid-template-columns: repeat(3, 1fr);
      align-content: center;
    }

  }

  @media (max-width: 576px) {
  p {
    font-size: 0.8rem
  }
}



.show-all-btn {
  display: block;
  margin: 1.5rem auto;
  padding: 0.7rem 2rem;
  background: #bc26d6;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  font-weight: 600;
  font-size: 1rem;
}

/* Modal styling */
.modal {
  position: fixed;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  background-color: rgba(10, 10, 10, 0.8);
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 1000;
}

/* Centered modal box */
.modal-content {
  background: #111;
  padding: 1.5rem;
  border-radius: 8px;
  text-align: center;
  max-width: 600px;   /* keep it nice and centered */
  width: 90%;         /* responsive */
  max-height: 80vh;   /* prevent it from overflowing */
  overflow-y: auto;
  /* color: #f4f4fb; */
  box-shadow: 0 8px 20px rgba(0,0,0,0.4);
}

/* Image inside modal */
.modal-content img {
  max-width: 100%;   /* not full width */
  max-height: 50vh; /* prevent huge images */
  height: auto;
  border-radius: 5px;
  margin-bottom: 1rem;
  object-fit: contain;
}

/* Button */
.modal-content button {
  width: 80px;
  margin: 0 auto;
  margin-top: 1rem;
  padding: 0.25rem 1.5rem;
  /* background: #bc26d6;
  border: none;
  border-radius: 5px;
  color: white;
  cursor: pointer;
  font-weight: 600; */
  transition: background 0.2s ease;
}

.modal-content button:hover {
  background: #9e1eb6;
}
</style>
