<script setup lang="ts">
import VHeroBlock from '@/components/VHeroBlock.vue'
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome'
import { faPhone, faArrowRight, faExclamationTriangle } from '@fortawesome/free-solid-svg-icons'
import emailjs from '@emailjs/browser';
import { ref } from 'vue';
import Swal from 'sweetalert2'
const form = ref<HTMLFormElement | null>(null);
const errorMsgs: any = ref([]);

const name = ref({
    msg: ''
});
const email = ref({
    msg: ''
});
const phone = ref({
    msg: ''
});
const subject = ref({
    msg: ''
});
const message = ref({
    msg: ''
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
    console.log("hola");
    const elements = form.value?.elements;

    if (!elements) return;

    const nameElement = elements[0] as HTMLInputElement;
    const emailElement = elements[1] as HTMLInputElement;
    const phoneElement = elements[2] as HTMLInputElement;
    const subjectElement = elements[3] as HTMLInputElement;
    const messageElement = elements[4] as HTMLTextAreaElement;
    nameElement.setCustomValidity('');
    emailElement.setCustomValidity('');
    phoneElement.setCustomValidity('');
    subjectElement.setCustomValidity('');
    messageElement.setCustomValidity('');

    nameElement.setCustomValidity(nameElement.checkValidity() ? '' : 'Please enter your name');
    emailElement.setCustomValidity(emailElement.checkValidity() ? '' : !emailElement.value ? 'Please enter your email' : 'Please enter a valid email');
    phoneElement.setCustomValidity(phoneElement.checkValidity() ? '' : !phoneElement.value ? 'Please enter your phone number' : 'Please enter a valid phone number');
    subjectElement.setCustomValidity(subjectElement.checkValidity() ? '' : 'Please enter your subject');
    messageElement.setCustomValidity(messageElement.checkValidity() ? '' : 'Please enter your message');

    name.value.msg = nameElement.validationMessage;
    email.value.msg = emailElement.validationMessage;
    phone.value.msg = phoneElement.validationMessage;
    subject.value.msg = subjectElement.validationMessage;
    message.value.msg = messageElement.validationMessage;

    for (let i = 0; i < elements.length; i++) {
        const element = elements[i] as HTMLInputElement | HTMLTextAreaElement;
        const errorIcon = element.nextElementSibling as HTMLElement;

        if (!element.checkValidity()) {
            errorMsgs.value.push(element.validationMessage);
            element.setCustomValidity(' ')
            errorIcon.classList.add('show-error-icon');
            element.classList.add('input-error');
        } else {
            errorIcon.classList.remove('show-error-icon');
            element.classList.remove('input-error');
        }
    }

    if (form.value?.checkValidity()) {
        sendEmail();
    } else {
        form.value?.reportValidity();
    }
}

function showAlertMessage() {
    Swal.fire({ title: 'Email sent successfully!', text: 'You will be contacted soon.', icon: "success" }).then(() => {
        window.location.href = '.';
    });
}

</script>

<template style="background-color: red;">
    <VHeroBlock imageUrl="./src/assets/hero_contact.png" title="Contact Us" />
    <div class="overlap-box">
        <div class="px-24 py-12">
            <span class="pr-contact-title-1 text-2xl font-bold text-gray-800">Request </span><span
                class="pr-contact-title-2 text-2xl font-bold text-blue-500">a quote</span>
        </div>
        <div class="form-title-underline"></div>
        <form method="POST" class="form" ref="form">
            <div class="input-row">
                <div>
                    <label for="name">
                        <p>*</p>Name
                    </label>
                    <input type="text" id="name" name="name" required>
                    <FontAwesomeIcon class="error-icon" :icon="faExclamationTriangle" />
                    <div class="error-msg">
                        <p v-if="name.msg" class="error-text">
                            {{ name.msg }}
                        </p>
                    </div>
                </div>
                <div>
                    <label for="email">
                        <p>*</p>Email
                    </label>
                    <input type="email" id="email" name="email" required>
                    <FontAwesomeIcon class="error-icon" :icon="faExclamationTriangle" />
                    <div class="error-msg">
                        <p v-if="email.msg" class="error-text">
                            {{ email.msg }}
                        </p>
                    </div>
                </div>
            </div>
            <div class="input-row">
                <div>
                    <label for="phone">
                        <p>*</p>Phone
                    </label>
                    <input type="tel" id="phone" name="phone" required>
                    <FontAwesomeIcon class="error-icon" :icon="faExclamationTriangle" />
                    <div class="error-msg">
                        <p v-if="phone.msg" class="error-text">
                            {{ phone.msg }}
                        </p>
                    </div>
                </div>
                <div>
                    <label for="subject">
                        <p>*</p>Subject
                    </label>
                    <input type="text" id="subject" name="subject" required>
                    <FontAwesomeIcon class="error-icon" :icon="faExclamationTriangle" />
                    <div class="error-msg">
                        <p v-if="subject.msg" class="error-text">
                            {{ subject.msg }}
                        </p>
                    </div>
                </div>
            </div>
            <div class="input-row">
                <div>
                    <label for="message">
                        <p>*</p>Message
                    </label>
                    <textarea id="message" name="message" rows="5" required></textarea>
                    <FontAwesomeIcon class="message-error-icon" :icon="faExclamationTriangle" />
                    <div class="error-msg">
                        <p v-if="message.msg" class="error-text">
                            {{ message.msg }}
                        </p>
                    </div>
                </div>
            </div>

            <div class="form-footer">
                <div class="submit-container" @click="validateForm()">
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
        </form>
    </div>
</template>

<style scoped>
.pr-main-content {
    background-color: var(--color-light-gray-100);
}

.overlap-box {
    position: relative;
    top: -40px;
    width: 70em;
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
    padding: 6em;
    padding-top: 0;
    padding-bottom: 3em;
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

label p {
    color: red;
    padding-right: 5px;
    display: inline;
    font-family: Arial, Helvetica, sans-serif;
}

input,
textarea {
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

.pr-contact-title-1 {
  font-family: 'AkiraExpandedDemo';
  font-size: 25px;
  color: var(--color-indigo-100);
}
.pr-contact-title-1:after {
  content: '';
  position: absolute;
  width: 7%;
  left: 6rem;
  padding-top: 40px;
  border-bottom: 2px solid var(--color-light-blue-lighter);
}
.pr-contact-title-2 {
  font-family: 'AkiraExpandedDemo';
  font-size: 25px;
  color: var(--color-light-blue);
}
.error-msg {
    color: #cc0000;
    margin-right: auto;
    margin-bottom: 1em;
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

.input-error {
    border-color: #cc0000;
}

.input-error:focus {
    outline-color: #cc0000;
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