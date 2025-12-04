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
                <p class="intro-text">I create pixel-perfect, full-stack projects that blend thoughtful design with functional code, delivering engaging digital experiences.</p>
                <a href="#about">
                    <button class="about-button btn mx-auto"><span class="text-light">About me</span></button>
                </a>
                <a  href="#projects">
                    <button class="btn sort m-2 " type="button" id="sort"><span class="text-light">My work</span></button>
                </a>
                <a href="https://drive.google.com/uc?export=download&id=1vvMaodCkKw-UtcawrnvfgqJFXZOPrp5s" class="btn btn-primary" target="_blank">
                    <span class="text-light">Download CV</span>
                </a>
            </div>
        </div>
        <div class="col me-auto">
            <img class="profile" src="https://github.com/caleb-okkers/portfolioaugust24/blob/master/src/assets/p7enhanced.png?raw=true" alt="profile">
        </div>
    </div>

    </div>

</template>

<script>
export default {

}
</script>

<style scoped>

.row {
  min-height: 100dvh
}

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
  font-size: 0.8rem;
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

/* General responsive adjustments */
@media (max-width: 1200px) {
  .intro-div {
    margin-left: 4rem;
  }

  .static-type {
    font-size: 58px;
  }

  h1 {
    font-size: 24px;
  }

  p {
    font-size: 1rem;
  }

  .btn {
    font-size: 0.9rem;
    padding: 8px 16px;
  }
}

@media (max-width: 992px) {
  .intro-div {
    margin-left: 2rem;
    text-align: center;
  }

  .static-type {
    font-size: 48px;
  }

  h1 {
    font-size: 22px;
  }

  p {
    font-size: 0.95rem;
  }

  .btn {
    font-size: 0.85rem;
    padding: 8px 14px;
  }

  .profile {
    width: 80%;
    margin: auto;
  }
}

@media (max-width: 768px) {
  .intro-div {
    margin-left: 1rem;
    margin-right: 1rem;
    text-align: center;
    padding-bottom: 0 !important;
    padding-top: 10rem !important;
  }

  .static-type {
    font-size: 36px;
  }

  h1 {
    font-size: 64px !important;
  }

    h3 {
    padding-bottom: 1rem;
  }

  p {
    font-size: 0.9rem;
    display: none;
  }

  .btn {
    font-size: 0.8rem;
    padding: 6px 12px;
  }

  .profile {
    width: 100%;
    padding-bottom: 10rem;
  }

  .row {
    flex-direction:column;
  }
}

@media (max-width: 576px) {

  /* Navbar adjustments */
nav {
  background-color: #001a34; /* Matching the button background color */
}

.container.pt-5 {
  padding-top: 5rem !important; /* Ensure content isn't hidden behind navbar */
}

  .intro-div {
    margin-left: 0.5rem;
    margin-right: 0.5rem;
    padding-bottom: 0 !important;
    padding-top: 1rem !important;
  }

  .static-type {
    font-size: 28px;
  }

  h3 {
    padding-bottom: 1.5rem;
  }

  h1 {
    font-size: 36px !important;
  }

  p {
    font-size: 0.85rem;
    display: none;
  }

  .btn {
    font-size: 0.75rem;
    padding: 5px 10px;
    margin-top: ;
  }

  .about-button {
    padding: 5px 10px;
  }

  .profile {
    width: 100%;
    margin-top: -7.5rem;
    padding-bottom: 0rem !important;
  }

  .intro-div {
    padding: 0;
    padding-bottom: 0 !important;
  }
}



</style>