<template>
   <div class="card"  data-aos="fade-up">
     <img :src="imageSrc" alt="Card Image" class="card-image pt-3" />
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
   flex-direction: column;
   justify-content: space-between;
   padding: 10px;
   margin: 0.2rem;
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


 /* Small mobile screens (max-width: 576px) */
@media (max-width: 576px) {
  .card {
    max-width: 90px; /* Adjust card size for smaller screens */
    height: 90px;
    padding: 8px;
  }

  .card-caption {
    font-size: 0.49rem;
    padding-top: 0.5rem;
  }

  .card-image {
    width: 45%;
  }
}
 </style>