<template>
      <div class="container pt-5">
        <div class="text-center pt-5">
      <h3 class="heading">Certifications</h3>
      <p class="subtext pt-3">Here are some of my Certifications.</p>
   </div>
        <div class="row d-flex justify-content-center align-items-center pt-3">

            <CertificationCard/>
        </div>
      </div>
</template>

<script>
import CertificationCard from './CertificationCard.vue';

export default {
    components: {
    CertificationCard
  }
}
</script>

<style>

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