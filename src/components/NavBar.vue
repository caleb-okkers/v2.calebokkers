<template>
    <div>
      <nav class="navbar navbar-expand-lg fixed-top home-nav mb-5" id="home-nav">
        <div class="container-fluid d-flex flex-column align-items-center">
          <!-- Title Row -->
          <!-- <div class="row w-100 text-center mx-auto navbar-brand">
              <h1 class=" title ">CSO</h1>
          </div> -->
          <!-- Navbar Links Row -->
          <div class="row w-100">
            <button
              class="navbar-toggler mx-auto"
              type="button"
              data-bs-toggle="collapse"
              data-bs-target="#navbarNavAltMarkup"
              aria-controls="navbarNavAltMarkup"
              aria-expanded="false"
              aria-label="Toggle navigation"
               @click="toggleNavbar"
            >
              <span class="navbar-toggler-icon"></span>
            </button>
            <div class="collapse navbar-collapse justify-content-center" id="navbarNavAltMarkup">
              <ul class="navbar-nav mb-2 mb-lg-0">
                <li class="nav-item">
                  <a class="nav-link" :class="{ active: activeSection === 'home' }" href="#home">Home</a>
                </li>
                <li class="nav-item">
                  <a class="nav-link" :class="{ active: activeSection === 'about' }" href="#about">About</a>
                </li>
                <li class="nav-item">
                  <a class="nav-link" :class="{ active: activeSection === 'resume' }" href="#resume">Education & Experience</a>
                </li>
                <li class="nav-item">
                  <a class="nav-link" :class="{ active: activeSection === 'projects' }" href="#projects">Projects</a>
                </li>
                <li class="nav-item">
                  <a class="nav-link" :class="{ active: activeSection === 'contact' }" href="#contact">Contact</a>
                </li>
              </ul>
            </div>
          </div>
        </div>
      </nav>
    </div>
  </template>
  
  <script>
  export default {
    name: "NavBar",
    data() {
    return {
      activeSection: "home",
      };
    },
    mounted() {
      window.addEventListener("scroll", this.handleScroll);
    },
    beforeUnmount() {
      window.removeEventListener("scroll", this.handleScroll);
    },
    methods: {
      handleScroll() {
        const sections = ["home", "about", "resume", "projects", "contact"];
      for (let section of sections) {
        const sectionElement = document.getElementById(section);
        if (sectionElement) {
          const rect = sectionElement.getBoundingClientRect();
          if (rect.top <= 100 && rect.bottom >= 100) {
            this.activeSection = section;
            break;
          }
        }
      }

        const navbar = document.getElementById("home-nav");
        if (window.scrollY > 10) {
          navbar.style.backgroundColor = "var(--primary-dark)";
        } else {
          navbar.style.backgroundColor = "rgba(0, 0, 0, 0)";
        }
      },

  //     toggleNavbar() {
  //   const navbarCollapse = document.getElementById('navbarNavAltMarkup');
  //   navbarCollapse.classList.toggle('show');
  // },

    },
  };
  </script>
  
  <style scoped>

.title {
  font-family: "Montserrat", sans-serif;
  font-optical-sizing: auto;
  font-weight: 700;
  font-style: italic;
  background: linear-gradient(180deg, #bc26d6, #fe7ab6); /* Your gradient colors */
  -webkit-background-clip: text; 
  -webkit-text-fill-color: transparent;
}

.navbar-collapse.collapsing,
.navbar-collapse.show {
  background-color: var(--primary-dark); /* Dark background color */
  padding: 1rem; /* Optional: Add padding for aesthetics */
  border-radius: 5px; /* Optional: Add rounded corners */
  transition: none; /* Disable transition for immediate effect */
}

  /* @media (max-width: 768px) {
    .navbar {
      background: #151515;
    }
  } */


  .navbar {
    background: rgba(0, 0, 0, 0);
    font-family: Poppins;
    font-weight: 500;
    font-style: normal;
    font-size: 1.1rem;
    transition: background-color 0.2s ease-in;
    height: 15%;
  }

  /* .navbar:hover {
    background: var(--primary-dark) !important;
  } */
  
  .navbar .navbar-brand {
    text-align: center;
  }
  
  .navbar .nav-link {
    color: #fff;
    padding-left: 1rem !important;
    padding-right: 1rem !important;
  }
  
  .navbar-toggler {
    border: none !important;
    outline: none !important;
  }

  .navbar-toggler-icon {
    color: var(--primary-light) !important;
  }
  
  .navbar-toggler:focus {
    box-shadow: none !important;
    background: #151515 !important;
  }
  
  nav a.active {

    color: var(--primary-light) ;
  }

  nav a.active::after {
  content: "";
  position: absolute;
  width: 100%;
  height: 1px;
  bottom: 0;
  left: 0;
  /* background-color: #ecb904; */
  background-color: var(--primary-light);
  transition: width 0.3s ease, left 0.3s ease;
}
  
  .nav-link {
    position: relative;
    display: inline-block;
    padding-bottom: 5px;
    text-decoration: none;
    transition: color 0.3s ease;
  }
  
  .nav-link::after {
    content: "";
    position: absolute;
    width: 0;
    height: 1px;
    bottom: 0;
    left: 50%;
    /* background-color: #ecb904; */
    /* background-color: var(--primary-light); */
    display: inline-block;
  background: linear-gradient(135deg, #bc26d6, #fe7ab6); /* Your gradient colors */



    transition: width 0.3s ease, left 0.3s ease;
  }
  
  .nav-link:hover,
  .nav-link.active {
    /* color: #ecb904 !important; */
    /* color: var(--primary-light) !important; */
    display: inline-block;
  background: linear-gradient(135deg, #bc26d6, #fe7ab6); /* Your gradient colors */
  -webkit-background-clip: text; 
  -webkit-text-fill-color: transparent;
  color: #e669fb; /* Choose a color for the static text */
  font-weight: 500;
    font-style: normal;
    font-size: 1.1rem;

  }
  
  .nav-link:hover::after,
  .nav-link.active::after {
    width: 100%;
    left: 0;
  }
  
  .home-nav .container-fluid {
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  
  .title {
    margin-bottom: 0.5rem;
    color: #fff;
  }
  </style>