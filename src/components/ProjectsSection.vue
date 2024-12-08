<template>
      <div class="container pt-5">
        <div class="text-center pt-5">
      <h3 class="heading">Projects</h3>
      <p class="subtext pt-3">Have a look at some of my work.</p>
   </div>
        <div class="row d-flex justify-content-center align-items-center pt-3">

            <ProjectCard/>
        </div>
      </div>
</template>

<script>
import ProjectCard from './ProjectCard.vue';

export default {
    components: {
    ProjectCard
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