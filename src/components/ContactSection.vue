<template>
    <div class="container pt-5">
        <div class="text-center pt-5">
            <h2 class="contact-heading headings">Contact</h2>
            <p class="pt-3">If you have any enquiries, feel free to reach out.</p>
        </div>

        <div class="row pt-5 d-flex justify-content-center">
            
                <div class="spline-div">
                    <!-- <iframe src='https://my.spline.design/cybermannequin-013efb57449009f300fec795056b9482/' frameborder='0' width='100%' height='100%'></iframe> -->
                    <!-- <iframe src='https://my.spline.design/worldplanet-163b7172fe88ddc6f7163ff1c3662c4a/' frameborder='0' width='100%' height='100%'></iframe> -->
                    <iframe src='https://my.spline.design/rocket-478afbf555227006173ef331e54450c6/' frameborder='0' width='100%' height='100%'></iframe>
                </div>
            
            
                <div class="form-div pb-5">
                    <form @submit.prevent="submitForm" class="mt-5">
                        <div class="contact-label-div mb-3">
                            <label for="name" class="form-label contact-label">Name</label>
                            <input v-model="formData.name" type="text" class="form-control" id="name" placeholder="Enter your name" name="name" required>
                            <span v-if="formErrors.name" class="error">{{ formErrors.name }}</span>
                        </div>
                        <div class="contact-label-div mb-3">
                            <label for="email" class="form-label contact-label">Email address</label>
                            <input v-model="formData.email" type="email" class="form-control contact-form" id="email" placeholder="name@example.com" name="email" required>
                            <span v-if="formErrors.email" class="error">{{ formErrors.email }}</span>
                        </div>
                        <div class="contact-label-div mb-3">
                            <label for="message" class="form-label contact-label">Message</label>
                            <textarea v-model="formData.message" class="form-control" id="message" rows="5" placeholder="Enter your message" name="message" required></textarea>
                            <span v-if="formErrors.message" class="error">{{ formErrors.message }}</span>
                        </div>
                        <div class="row justify-content-center">

                            <button type="submit" class="btn custom-submit-button btn-outline-success"><span>Submit</span></button>
                        </div>
                    </form>
                    <!-- <div class="more">
                        <p>Reach out via...</p>
                    </div>
                    <div class="socials">
                        <a id="profile-link" href="https://github.com/caleb-okkers" target="_blank" class="btn contact-details">
                            <i class="fab fa-github fa-2xl"></i>
                            <span>
                                GitHub
                            </span>
                        </a>
                        <a id="profile-link" href="https://www.linkedin.com/in/caleb-okkers-43b100287" target="_blank" class="btn contact-details">
                            <i class="fab fa-linkedin fa-2xl"></i>
                            <span>
                                linkedin
                            </span>
                        </a>
                    </div> -->
                </div>
            
        </div>
        <!-- <div class="content"></div> -->
        <div class="row info text-center py-4 pt-5">
      <div class="col-md-4 mb-3">
        <p class="mb-0">Century City, Cape Town</p>
        <p class="mb-0">South Africa</p>
      </div>
      <div class="col-md-4 mb-3">
        <a id="profile-link" href="https://github.com/caleb-okkers" target="_blank" class="btn contact-details">
                            <i class="fab fa-github fa-2xl"></i>
                            <!-- <span>
                                GitHub
                            </span> -->
                        </a>
                        <a id="profile-link" href="https://www.linkedin.com/in/caleb-okkers-43b100287" target="_blank" class="btn contact-details">
                            <i class="fab fa-linkedin fa-2xl"></i>
                            <!-- <span>
                                linkedin
                            </span> -->
                        </a>
      </div>
      <div class="col-md-4 mb-3">
        <p class="mb-0">okkerscaleb@gmail.com</p>
        <p class="mb-0">078 344 9656</p>
      </div>
    </div>
    </div>
</template>

<script>
export default {
    name: "ContactSection",
    data() {
        return {
            formData: {
                name: '',
                email: '',
                message: ''
            },
            formErrors: {
                name: '',
                email: '',
                message: ''
            }
        };
    },
    methods: {
        submitForm() {
            // Reset errors
            this.formErrors.name = '';
            this.formErrors.email = '';
            this.formErrors.message = '';

            // Validate name
            if (!this.formData.name.trim()) {
                this.formErrors.name = 'Name is required';
            }

            // Validate email
            if (!this.formData.email.trim()) {
                this.formErrors.email = 'Email is required';
            } else if (!this.isValidEmail(this.formData.email)) {
                this.formErrors.email = 'Invalid email format';
            }

            // Validate message
            if (!this.formData.message.trim()) {
                this.formErrors.message = 'Message is required';
            }

            // Submit form if no errors
            if (!this.formErrors.name && !this.formErrors.email && !this.formErrors.message) {
                this.submitToFormspree();
            }
        },
        isValidEmail(email) {
            // Basic email validation regex
            const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
            return emailRegex.test(email);
        },
        submitToFormspree() {
            const formUrl = 'https://formspree.io/f/mzzpbkpy'; 
            fetch(formUrl, {
                method: 'POST',
                headers: {
                    'Content-Type': 'application/json'
                },
                body: JSON.stringify(this.formData)
            })
            .then(response => {
                if (!response.ok) {
                    throw new Error('Network response was not ok');
                }
                alert('Form submitted successfully!');
                this.clearForm();
            })
            .catch(error => {
                console.error('There was a problem with form submission:', error);
                alert('There was an error submitting the form. Please try again later.');
            });
        },
        clearForm() {
            this.formData.name = '';
            this.formData.email = '';
            this.formData.message = '';
        }
    }
};
</script>

<style scoped>

label {
    font-size: 1rem;
    font-family: "Montserrat", sans-serif;
    font-optical-sizing: auto;
    font-weight: 300;
    font-style: normal;
    color: var(--primary-light);
}

.form-div .btn {
  position: relative;
  overflow: hidden;
  background-color: var(--primary-dark) !important;
  color: #fff !important;
  border-color: #fff !important;
  text-align: center !important;
  padding: 5px 20px;
  cursor: pointer;
  transition: color 0.5s ease;
  border-radius: 0 !important;
  z-index: 1;
  will-change: color; 
  font-size: 1rem;
    font-family: "Montserrat", sans-serif;
    font-optical-sizing: auto;
    font-weight: 300;
    font-style: normal;
  border-radius: 4px !important;
  width: 30%;
}

.form-div .btn::before {
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

.form-div .btn:hover::before {
  transform: scaleX(1);
}

.form-div .btn span {
  position: relative;
  z-index: 2;
  backface-visibility: hidden; 
  will-change: color; 
  color: #fff;
  
}

.form-div .btn:hover span {
  position: relative;
  z-index: 2;
  backface-visibility: hidden; 
  will-change: color; 
  color: #fff !important;
  
}


i {
    color: var(--primary-light);
}

.col-md-4 {
    padding: 0;
}

  .contact-heading {
    font-size: 36px;
  display: inline-block;
  background: linear-gradient(
    135deg,
    #bc26d6,
    #fe7ab6
  ); /* Your gradient colors */
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  color: #e669fb; /* Choose a color for the static text */
  font-weight: 600; /* Optional: make the static text bold */
  font-family: "Poppins";
}


iframe {
    width: 400px;
    height: 470px;
    border-radius: 10px;
}

.form-div {
    max-width: 400px;
    height: 400px;
    padding: 0;
    /* margin: 0; */
    width: 50% !important;
    margin-left: 0;
}

.spline-div {
    width: 30%;
    margin-right: 0;
}

@media (max-width:475px) {

    iframe {
        width: 300px;
        height: 300px
    }

    .form-div {
        width: 90% !important;
        margin: 0 12px;
        padding-left: 0px ;
    }

    .spline-contact {
        width: 100% !important;
        /* padding-right: 12px; */
        
    }

    .socials {
        padding-bottom: 1rem;
    }
}


/* Responsive Media Queries */
@media (max-width: 768px) {

    p {
        font-size: 0.95rem;
    }

    label {
        font-size: 0.95rem;
    }

    .form-div .btn {
        font-size: 0.95rem;
        width: 50%;
    }

    iframe {
        width: 80%;
        height: 350px;
        margin: 0 auto;
    }

    .form-div {
        width: 60% !important;
        max-width: 100%;
    }

    .spline-div {
        width: 80%;
        margin-bottom: 1.5rem;
    }
}

@media (max-width: 475px) {

    p {
        font-size: 0.9rem;
    }

    label {
        font-size: 0.9rem;
    }

    .form-div .btn {
        font-size: 0.9rem;
        width: 70%;
        margin-bottom: 2rem !important;
    }

    iframe {
        width: 100%;
        height: 300px;
    }

    .form-div {
        width: 90% !important;
        padding: 0 12px;
    }

    .spline-div {
        width: 100%;
        margin-bottom: 1.5rem;
    }
}

@media (max-width: 576px) {
  p {
    font-size: 0.8rem
  }
}

/* Default order for larger screens (no change needed for desktop/tablet) */
.text-center .col-md-4 {
    order: initial;
}

/* Adjust order on mobile (below 768px) */
@media (max-width: 768px) {
    /* Links come first */
    .text-center .col-md-4:nth-child(1) {
        order: 1;
    }

    /* Location comes second */
    .text-center .col-md-4:nth-child(2) {
        order: 2;
    }

    /* Contact info comes last */
    .text-center .col-md-4:nth-child(3) {
        order: 3;
    }

    .info {
        margin-top: 3rem;
    }
}

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

@media (min-width: 768px) {
  .spline-div {
    margin-right: 4rem;
  }
}
</style>