<template>
  <div class="container-fluid">
    <!-- <NavBar/> -->
      <section class="row" id="home">
        <HomeSection/>
      </section>
      <section class="row" id="about">
          <AboutSection :about="about" :hobbies="hobbies"/>
      </section>
      <section class="row" id="resume">
        <ResumeSection/>
      </section>
      <section class="row" id="projects">
        <ProjectsSection/>
      </section>
      <section class="row" id="certifications">
        <CertificationsSection/>
      </section>
      <section class="row" id="contact">
        <ContactSection/>
      </section>
    
    <!-- <Footer/> -->
  </div>
</template>

<script>
import HomeSection from '@/components/HomeSection.vue'
import AboutSection from '@/components/AboutSection.vue'
import ResumeSection from '@/components/ResumeSection.vue'
import ProjectsSection from '@/components/ProjectsSection.vue'
import CertificationsSection from '@/components/CertificationsSection.vue'
import ContactSection from '@/components/ContactSection.vue'

export default {
  
  components: {
    HomeSection,
    AboutSection,
    ResumeSection,
    ProjectsSection,
    CertificationsSection,
    ContactSection
  }
}
</script>

<style>
</style>
