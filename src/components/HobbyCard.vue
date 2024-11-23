<template>
    <div class="card">
      <img :src="imageSrc" alt="Card Image" class="card-image" />
      <p class="card-caption">{{ caption }}</p>
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
    background-color: #111;
    color: white;
    border-radius: 5px;
    overflow: hidden;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 1);
    max-width: 150px;
    height: 150px;
    margin: auto;
    text-align: center;
    display: flex;
    justify-content: space-between;
    padding: 10px;
  }
  
  .card-image {
    width: 50%;
    display: block;
    margin: 0 auto;
  }
  
  .card-caption {
    padding: 5px;
    font-size: 0.8rem;
  }

  </style>