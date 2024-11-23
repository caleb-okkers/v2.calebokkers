<template>
    <div class="container pt-5">
        <!-- <div class="row d-flex justify-content-center align-items-center">
            <div class="col-md-6 col-sm-12 d-flex justify-content-center align-items-center">
              <div class="content">
                <h1 class="name static-type">Caleb Okkers</h1>
                <h3 class="title">
                  <span>Fullstack Developer</span>
                </h3>
                <a href="https://pdf.ac/3tW6pH" class="btn btn-primary mt-4" target="_blank">
                  Resume
                </a>
              </div>
              
            </div>
          <div class="col d-flex justify-content-center profile-col">
            <div class="home-image">
              <img src="https://github.com/caleb-okkers/vueportfolio/blob/main/src/assets/Caleb%20Okkers%20Profile.png?raw=true" alt="Caleb Okkers" loading="lazy">
            </div>
    
          </div>
          
        </div> -->

        <div class="row d-flex justify-content-center align-items-center">
        <div class="col d-flex justify-content-center">
            <div class="intro-div pb-5">
                <p class="intro-text">Hi, I'm</p>
                <h1 class="name static-type">CALEB OKKERS.</h1>
                <h3 class="title pt-2">Fullstack Developer</h3>
                <p class="intro-text">I design and build pixel perfect projects that inspire innovation and provide satisfying digital experiences.</p>
                <a href="#about">
                    <button class="about-button btn mx-auto"><span class="text-light">About me</span></button>
                </a>
                <a  href="#projects">
                    <button class="btn sort m-2 " type="button" id="sort"><span class="text-light">My work</span></button>
                </a>
                <a href="https://pdf.ac/3tW6pH" class="btn btn-primary" target="_blank">
                    <span class="text-light">Download CV</span>
                </a>
            </div>
        </div>
        <div class="col me-auto">
            <img class="profile" src="https://github.com/caleb-okkers/portfolioaugust24/blob/master/src/assets/p7enhanced.png?raw=true" alt="">
        </div>
    </div>

    </div>

</template>

<script>
export default {

}
</script>

<style scoped>

.profile {
    /* aspect-ratio: 1; */
    width: 100%;
}

p {
    font-size: 1.18rem;
    font-family: "Montserrat", sans-serif;
    font-optical-sizing: auto;
    font-weight: 300;
    font-style: normal;
}

h1 {
  font-size: 28px; /* Adjust size as needed */
  text-align: center; /* Optional: center the text */
  color: #fff;
  font-style: italic;
}

.static-type {
  font-size: 68px;
  display: inline-block;
  background: linear-gradient(135deg, #bc26d6, #fe7ab6); /* Your gradient colors */
  -webkit-background-clip: text; 
  -webkit-text-fill-color: transparent;
  color: #e669fb; /* Choose a color for the static text */
  font-weight: bold; /* Optional: make the static text bold */
  margin-top: -0.5rem;
}

.title {
    font-family: Montserrat;
    color: #fff !important;
}

.intro-div {
    color: #fff;
    margin-right: 0;
    margin-left: 8rem;
}

.about-button {
  position: relative;
  overflow: hidden;
  background-color: #001a34 !important;
  color: #fff !important;
  border-color: #001a34 !important;
  text-align: center !important;
  padding: 10px 20px;
  cursor: pointer;
  transition: color 0.5s ease;
  border-radius: 0 !important;
  z-index: 1;
  will-change: color;
  font-size: 1.18rem;
    font-family: "Montserrat", sans-serif;
    font-optical-sizing: auto;
    font-weight: 300;
    font-style: normal;
}

.btn {
  position: relative;
  overflow: hidden;
  background-color: var(--primary-dark) !important;
  color: #fff !important;
  border-color: #fff !important;
  text-align: center !important;
  padding: 10px 20px;
  cursor: pointer;
  transition: color 0.5s ease;
  border-radius: 0 !important;
  z-index: 1;
  will-change: color; 
  font-size: 1.18rem;
    font-family: "Montserrat", sans-serif;
    font-optical-sizing: auto;
    font-weight: 300;
    font-style: normal;
  border-radius: 4px !important;
}

.btn::before,
.about-button::before {
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

.btn:hover::before,
.about-button:hover::before {
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


</style>