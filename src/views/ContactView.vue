<script setup lang="ts">
import VHeroBlock from '@/components/VHeroBlock.vue'
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome'
import { faPhone, faArrowRight, faExclamationTriangle } from '@fortawesome/free-solid-svg-icons'
import emailjs from '@emailjs/browser';
import { ref } from 'vue';
import Swal from 'sweetalert2'
const form = ref<HTMLFormElement | null>(null);
const errorMsgs: any = ref([]);

const formData = ref({
    name: '',
    email: '',
    phone: '',
    subject: '',
    message: ''
});



function sendEmail() {
    if (form.value !== null) {
        emailjs
            .sendForm('service_8xwe4qx', 'template_ihvvut6', form.value, {
                publicKey: '4Z7cO4rsSonIuZlJt',
            })
            .then(
                () => {
                    showAlertMessage();
                },
                (error) => {
                    console.log('FAILED...', error.text);
                },
            );
    }
}

function validateForm() {
    errorMsgs.value = [];

    const elements = form.value?.elements;

    if (!elements) return;

    const nameElement = elements[0] as HTMLInputElement;
    const emailElement = elements[1] as HTMLInputElement;
    const phoneElement = elements[2] as HTMLInputElement;
    const subjectElement = elements[3] as HTMLInputElement;
    const messageElement = elements[4] as HTMLTextAreaElement;

    nameElement.setCustomValidity(nameElement.checkValidity() ? '' : 'Please enter your name');
    emailElement.setCustomValidity(emailElement.checkValidity() ? '' : 'Please enter your email');
    phoneElement.setCustomValidity(phoneElement.checkValidity() ? '' : 'Please enter your phone number');
    subjectElement.setCustomValidity(subjectElement.checkValidity() ? '' : 'Please enter your subject');
    messageElement.setCustomValidity(messageElement.checkValidity() ? '' : 'Please enter your message');

    for (let i = 0; i < elements.length; i++) {
        const element = elements[i] as HTMLInputElement | HTMLTextAreaElement;
        const errorIcon = element.nextElementSibling as HTMLElement;

        if (!element.checkValidity()) {
            errorIcon.classList.add('show-error-icon'); // Add class to show icon
        } else {
            errorIcon.classList.remove('show-error-icon'); // Remove class to hide icon
        }

        if (!element.checkValidity()) {
            errorMsgs.value.push(element.validationMessage);
        }
    }


    if (form.value?.checkValidity()) {
        sendEmail();
    } else {
        form.value?.reportValidity();
    }

    nameElement.setCustomValidity('');
    emailElement.setCustomValidity('');
    phoneElement.setCustomValidity('');
    subjectElement.setCustomValidity('');
    messageElement.setCustomValidity('');
}

function showAlertMessage() {
    Swal.fire({title: 'Email sent successfully!', text: 'You will be contacted soon.', icon: "success"}).then(() => {
        window.location.href='.';
    });
}

</script>

<template style="background-color: red;">
    <VHeroBlock imageUrl="./src/assets/hero_contact.png" title="Contact Us" />
    <div class="overlap-box">
        <div class="form-title">
            <p>Request </p>
            <div class="form-title-quote">
                <p>a quote</p>
            </div>
        </div>
        <div class="form-title-underline"></div>
        <form method="POST" class="form" ref="form" @submit.prevent="validateForm()">
            <div class="input-row">
                <div>
                    <label for="name">Name</label>
                    <input type="text" id="name" name="name" v-model="formData.name" required>
                    <FontAwesomeIcon class="error-icon" :icon="faExclamationTriangle" />
                </div>
                <div>
                    <label for="email">Email</label>
                    <input type="email" id="email" name="email" required>
                    <FontAwesomeIcon class="error-icon" :icon="faExclamationTriangle" />
                </div>
            </div>
            <div class="input-row">
                <div>
                    <label for="phone">Phone</label>
                    <input type="tel" id="phone" name="phone" required>
                    <FontAwesomeIcon class="error-icon" :icon="faExclamationTriangle" />
                </div>
                <div>
                    <label for="subject">Subject</label>
                    <input type="text" id="subject" name="subject" required>
                    <FontAwesomeIcon class="error-icon" :icon="faExclamationTriangle" />
                </div>
            </div>
            <div class="input-row">
                <div>
                    <label for="message">Message</label>
                    <textarea id="message" name="message" rows="5" required></textarea>
                    <FontAwesomeIcon class="message-error-icon" :icon="faExclamationTriangle" />
                </div>
            </div>

            <div class="form-footer">
                <div class="submit-container">
                    <input type="submit" value="Send">
                    <span class="icon-container">
                        <FontAwesomeIcon :icon="faArrowRight" class="pr-icon-arrow" />
                    </span>
                </div>
                <div class="pr-text-footer">
                    <FontAwesomeIcon :icon="faPhone" class="pr-icon-footer" /><a href="tel:+13039154272">+1 303
                        915-4272</a>
                </div>
            </div>
            <div class="error-msg">
                <p v-for="msg in errorMsgs" :key="msg" class="error-text">
                    {{ msg }}
                </p>
            </div>
        </form>
    </div>
</template>

<style scoped>
.overlap-box {
    position: relative;
    top: -40px;
    width: 70%;
    height: max-content;
    border-radius: 15px;
    margin: auto;
    background-color: white;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
    z-index: 2;
}

.form {
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 10em;
    padding-top: 3em;
    padding-bottom: 2em;
    color: gray;
}

.input-row {
    display: flex;
    flex-direction: row;
    gap: 5em;
    width: 100%;
}

.input-row div {
    width: 100%;
}

label {
    font-family: MundialLight;
    display: block;
    margin-bottom: 0.5em;
    text-align: start;
}

input,
textarea {
    margin-bottom: 1em;
    padding: 0.5em;
    border-radius: 5px;
    border: 1px solid #ccc;
    width: 100%;
    resize: none;
}

input[type="submit"] {
    padding: 0.5em 1em;
    padding-left: 2em;
    background-color: #1D2344;
    font-family: AkiraExpandedDemo;
    color: white;
    border: none;
    width: 10em;
    text-align: left;
    border-radius: 0px;
    cursor: pointer;
}

.form-footer {
    display: flex;
    width: 100%;
    justify-content: space-between;
}

.pr-icon-footer {
    color: var(--color-light-blue-lighter);
    margin-right: 1em;
}

.pr-icon-arrow {
    transform: translate(-45px, 3px);
    color: white;
    font-size: 1.5em;
}

.pr-text-footer {
    color: rgb(82, 81, 81);
}

.form-title {
    font-family: AkiraExpandedDemo;
    color: var(--color-indigo-100);
    display: flex;
    flex-direction: row;
    gap: 1em;
    margin-left: 10em;
    padding-top: 4em;
    width: max-content;
}

.form-title p {
    margin: 0;
    font-size: 25px;
}

.form-title-underline {
    border-bottom: 3px solid var(--color-light-blue);
    margin-left: 10em;
    margin-top: 1em;
    width: 4%;
}

.form-title-quote {
    font-family: AkiraExpandedDemo;
    color: var(--color-light-blue);
}

.error-msg {
    color: #cc0000;
    margin-right: auto;
}

.error-text {
    margin: 0;
}

.error-icon {
    display: none;
    color: #cc0000;
    font-size: 1.2em;
    margin-left: -30px;
    margin-bottom: -1px;
}
.message-error-icon {
    display: none;
    color: #cc0000;
    font-size: 1.2em;
    margin-left: -30px;
    margin-bottom: 72px;
}

.show-error-icon {
    display: inline;
}

@media (max-width: 1260px) {
    .input-row {
        flex-direction: column;
        gap: 0px;
    }

    .overlap-box {
        height: 60em;
    }

    .form {
        padding: 0px 2em;
    }

    .form-title {
        margin-left: 2em;
    }

    .form-title-underline {
        margin-left: 2em;
        margin-bottom: 1em;
    }
}

@media (max-width: 600px) {
    .form-footer {
        flex-direction: column;
    }

    .form-title {
        flex-direction: column;
    }
}
</style>