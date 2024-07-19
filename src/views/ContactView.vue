<template>
    <div class="container contact-page">
        <div class="row mt-4">
            <h4 class="mt-4 mb-3">THANK YOU FOR VISITING MY WEBSITE,</h4>
            <h4 class="mb-4">LET'S GET TO KNOW EACH OTHER MORE.</h4>
        </div>
        <div class="row d-flex justify-content-between mt-4">
            <div class="col-lg-7 col-md-12 col-xs-12 mb-5 mb-lg-0">
                <form ref="contactForm" class="border-right pr-5 mb-5" @submit.prevent="handleSubmit()"
                    action="https://api.web3forms.com/submit" method="POST">
                    <input type="hidden" name="access_key" value="b9843fb4-93d3-4c91-af3b-1a618984ef45">
                    <div class="row d-flex">
                        <div class="col-md-6 col-xs-12 mb-4 form-group">
                            <input type="text" class="form-control" name="fname" id="fname" v-model="firstname"
                                placeholder="First name">
                            <div v-if="errors.firstname" class="text-danger">
                                {{ errors.firstname }}
                            </div>
                        </div>
                        <div class="col-md-6 col-xs-12 mb-4 form-group">
                            <input type="text" class="form-control" name="lname" id="lname" placeholder="Last name"
                                v-model="lastname">
                            <div v-if="errors.lastname" class="text-danger">
                                {{ errors.lastname }}
                            </div>
                        </div>
                    </div>
                    <div class="row">
                        <div class="col-md-12 col-sm-12 col-xs-12 mb-4 form-group">
                            <input type="text" class="form-control" name="email" id="email" placeholder="Email"
                                v-model="email">
                            <div v-if="errors.email" class="text-danger">
                                {{ errors.email }}
                            </div>
                        </div>
                    </div>
                    <div class="row">
                        <div class="col-md-12 col-xs-12 mb-4 form-group">
                            <textarea class="form-control" name="message" id="message" cols="30" rows="7"
                                v-model="textmessage" placeholder="Drop your message here"></textarea>
                        </div>
                    </div>
                    <div class="row">
                        <div class="col-md-6">
                            <button class="btn fill" id="submit" type="submit">
                                Submit
                            </button>
                        </div>
                    </div>
                </form>
            </div>
            <div class="col-md-4 col-sm-12 col-xs-12 ml-auto">
                <h3 class="mb-4">OR REACH ME BY</h3>
                <ul class="contact-list">
                    <li class="d-flex align-items-center mb-4 list-item">
                        <i class="fa-solid fa-location-dot fa-xl icons location"></i>
                        <div class="contact-place">Springvale, VIC 3171, Australia</div>
                    </li>
                    <li class="d-flex align-items-center mb-4 list-item">
                        <i class="fa-solid fa-envelope fa-xl icons email"></i>
                        <a href="mailto:mengtongsrean17@gmail.com">mengtongsrean17@gmail.com</a>
                    </li>
                    <li class="d-flex align-items-center mb-4 list-item">
                        <i class="fa-solid fa-phone fa-xl icons phone"></i>
                        <div><a href="tel:+61475679863">+61 475 679 863</a></div>
                    </li>
                </ul>

                <hr>
                <ul class="social-media-list">
                    <a href="https://github.com/mengtongsrean" target="_blank">
                        <i class="fa fa-github fa-lg" aria-hidden="true"></i>
                    </a>
                    <a href="https://www.linkedin.com/in/mengtongsrean" target="_blank">
                        <i class="fa-brands fa-linkedin fa-lg" aria-hidden="true"></i>
                    </a>
                    <a href="mailto:mengtongsrean17@gmail.com">
                        <i class="fa-solid fa-envelope fa-lg" aria-hidden="true"></i>
                    </a>
                    <a href="https://www.instagram.com/mengtong.srean/" target="_blank">
                        <i class="fa-brands fa-instagram fa-lg"></i>
                    </a>
                </ul>
                <hr>
            </div>
        </div>
    </div>
</template>
<script scoped>
export default {
    data() {
        return {
            errors: {},
            firstname: '',
            lastname: '',
            email: '',
            textmessage: ''
        }
    },
    methods: {
        // Method to validate email format
        validateEmail(email) {
            const emailPattern = /^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$/;
            return emailPattern.test(email);
        },
        // Method to validate form inputs
        validateForm() {
            this.errors = {};
            const namePattern = /^[A-Za-z]+$/;

            // Validate username
            if (!this.firstname || !this.firstname.match(namePattern)) {
                this.errors.firstname = "Firstname must be letters only.";
            }

            if (!this.lastname || !this.lastname.match(namePattern)) {
                this.errors.lastname = "Lastname must be letters only.";
            }

            if (!this.email || !this.validateEmail(this.email)) {
                this.errors.email = "Email must be in email format only.";
            }
            return Object.keys(this.errors).length === 0; // Return true if no errors
        },
        // Method to handle form submission
        handleSubmit() {
            if (this.validateForm()) {
                // Submit form if validation passes
                this.$refs.contactForm.submit();
                this.firstname = '';
                this.lastname = '';
                this.email = '';
                this.textmessage = '';
            }
        }
    }
}

</script>
<style scoped>
.form.border-right {
    padding-right: 6rem !important;
}

h4 {
    letter-spacing: 0.12rem;
}

.contact-list {
    list-style-type: none;
    margin-left: -30px;
    padding-right: 20px;

}

.list-item {
    color: rgb(114, 112, 112);
    font-size: 15px;
    line-height: 2;
}

.list-item a {
    color: rgb(114, 112, 112);
    text-decoration: none;
    transition-duration: 0.2s;
}

.list-item:hover,
.list-item a:hover {
    color: #22cef4;
    transition-duration: 0.2s;
}

.icons {
    margin-right: 15px;
}

.location {
    margin-right: 23px;
}

.email {
    margin-right: 19px;
}

.phone {
    margin-right: 19px;
}

hr {
    border-color: rgb(114, 112, 112);
}
</style>
