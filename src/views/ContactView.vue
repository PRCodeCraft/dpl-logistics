<script setup lang="ts">
import VHeroBlock from '@/components/VHeroBlock.vue'
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome'
import { faPhone } from '@fortawesome/free-solid-svg-icons'
</script>

<template>
    <VHeroBlock 
        imageUrl="./src/assets/hero_contact.png"
        title="Contact Us"
    />
    <div class="overlap-box">
        <form action="#" method="post" class="form">
            <div class="input-row">
                <div>
                    <label for="name">Name:</label>
                    <input type="text" id="name" name="name" required>
                </div>
                <div>
                    <label for="email">Email:</label>
                    <input type="email" id="email" name="email" required>
                </div>
            </div>
            <div class="input-row">
                <div>
                    <label for="phone">Phone:</label>
                    <input type="tel" id="phone" name="phone" required>
                </div>
                <div>
                    <label for="subject">Subject:</label>
                    <input type="text" id="subject" name="subject" required>
                </div>
            </div>
            <div class="input-row">
                <div>
                    <label for="message">Message:</label>
                    <textarea id="message" name="message" rows="5" required></textarea><br>
                </div>
            </div>
            <div class="form-footer">
                <input type="submit" value="Send">
                <div class="pr-text-footer"><FontAwesomeIcon :icon="faPhone" class="pr-icon-footer"/>+1 303 915-4272</div>
            </div>
        </form>
    </div>
</template>

<style scoped>
.overlap-box {
    position: relative;
    top: -40px;
    width: 70%;
    height: 40em;
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
    display: block;
    margin-bottom: 0.5em;
    text-align: start;
}

input, textarea {
    margin-bottom: 1em;
    padding: 0.5em;
    border-radius: 5px;
    border: 1px solid #ccc;
    width: 100%;
}

input[type="submit"] {
    padding: 0.5em 1em;
    background-color: #007bff;
    color: white;
    border: none;
    width: 10em;
    border-radius: 5px;
    cursor: pointer;
}

.form-footer {
    display: flex;
    width: 100%;
    justify-content: space-between;
}

.pr-icon-footer{
  color: var(--color-light-blue-lighter);
  margin-right: 1em;
}

.pr-text-footer {
    color: rgb(82, 81, 81);
}
</style>