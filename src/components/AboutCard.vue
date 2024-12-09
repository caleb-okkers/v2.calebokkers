<template>
    <div class="card"  data-aos="fade-up">
      <img :src="imageSrc" alt="Card Image" class="card-image" />
      <p class="card-caption">{{ caption }}</p>
      <div class="card-footer">{{ footer }}</div>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      imageSrc: {
        type: String,
        required: true
      },
      caption: {
        type: String,
        required: true
      },
      footer: {
        type: String,
        required: true
      }
    }
  };
  </script>
  
  <style scoped>
  .card {
    background-color: #111;
    color: white;
    border-radius: 5px;
    overflow: hidden;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 1);
    max-width: 100px;
    height: 100px;
    margin: auto;
    text-align: center;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    padding: 1px;
    padding-top: 5px;
    margin: 0.01rem;
  }
  
  .card-image {
    width: 40%;
    display: block;
    margin: 0 auto;
  }
  
  .card-caption {
    padding: 1px;
    font-size: 0.8rem;
    margin-bottom: -10px;
  }
  
  .card-footer {
    color: #555;
    padding: 1px;
    font-size: 0.7rem;
  }

  /* Default styling for larger screens */
.card {
  background-color: #111;
  color: white;
  border-radius: 5px;
  overflow: hidden;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 1);
  max-width: 100px;
  height: 100px;
  margin: auto;
  text-align: center;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  padding: 1px;
  padding-top: 5px;
  margin: 0.01rem;
}

  /* Media query for screens below 576px */
@media (max-width: 576px) {
  .card {
    width: 90px; /* Slightly smaller cards on mobile */
    height: 90px;
  }

  .card-caption {
    font-size: 0.55rem;
  }

  .card-footer {
    font-size: 0.45rem;
  }
}
  </style>
  


<!-- <template>
    <div class="card">
      <img :src="imageSrc" alt="Card Image" class="card-image" />
      <div class="card-caption">{{ caption }}</div>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      imageSrc: {
        type: String,
        required: true
      },
      caption: {
        type: String,
        required: true
      }
    }
  };
  </script>
  
  <style scoped>
  .card {
    background-color: black;
    color: white;
    border-radius: 5px;
    overflow: hidden;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
    max-width: 150px;
    height: 150px;
    margin: auto;
    text-align: center;
  }
  
  .card-image {
    width: 100%;
    display: block;
    height: 75%;
  }
  
  .card-caption {
    padding: 10px;
    font-size: 1rem;
  }
  </style>
   -->