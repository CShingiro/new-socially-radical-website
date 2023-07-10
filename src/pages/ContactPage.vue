<script setup lang="ts">
import { ref, reactive } from 'vue';
import { ContactType } from 'src/ContactType';
import { api } from 'src/boot/axios';

let contactInfo: ContactType = reactive({
  firstName: '',
  lastName: '',
  email: '',
  subject: '',
  message: '',
});

const firstName = ref('');
const lastName = ref('');
const email = ref('');
const subject = ref('');
const message = ref('');

const onSubmit = () => {
  contactInfo = {
    firstName: firstName.value,
    lastName: lastName.value,
    email: email.value,
    subject: subject.value,
    message: message.value,
  };
  api
    .post('/api/v1/contact', contactInfo)
    .then((res) => {
      console.log(res);
    })
    .catch((err) => {
      console.log(err);
    });

  alert('Message sent. Please wait 24-48 hours for a reply.');
  firstName.value = '';
  lastName.value = '';
  email.value = '';
  subject.value = '';
  message.value = '';
};
</script>

<template>
  <q-page class="row items-center justify-evenly">
    <div class="q-pa-md">
      <div class="row">
        <div class="row">
          <div class="col-12">
            <h1 class="romade-italic text-center gt-md">
              Contact the Designer
            </h1>
            <h3 class="romade-italic text-center md">Contact the Designer</h3>
            <h4 class="romade-italic text-center lt-md">
              Contact the Designer
            </h4>
          </div>
        </div>
        <div class="row items-center">
          <div class="col">
            <h6 class="gt-md">
              Note: This form is only for those inquiring about Socially Radical
              Web Design. If you have questions about journalism, media related
              inquiries, or a question about the radio show, please refer to
              <a href="https://sociallyradicalguitarist.com" target="_blank"
                >The Socially Radical Guitarist</a
              >.
            </h6>
            <p class="md">
              Note: This form is only for those inquiring about Socially Radical
              Web Design. If you have questions about journalism, media related
              inquiries, or a question about the radio show, please refer to
              <a href="https://sociallyradicalguitarist.com" target="_blank"
                >The Socially Radical Guitarist</a
              >.
            </p>
            <span class="lt-md text-caption">
              Note: This form is only for those inquiring about Socially Radical
              Web Design. If you have questions about journalism, media related
              inquiries, or a question about the radio show, please refer to
              <a href="https://sociallyradicalguitarist.com" target="_blank"
                >The Socially Radical Guitarist</a
              >.
            </span>
          </div>
        </div>
      </div>
      <q-form @submit.prevent="onSubmit" name="Contact Form" action="POST">
        <q-input
          outlined
          v-model="firstName"
          type="text"
          label="First Name"
          required
          aria-required="true"
        ></q-input>
        <q-input
          outlined
          v-model="lastName"
          type="text"
          label="Last Name"
          required
          aria-required="true"
        ></q-input>
        <q-input
          outlined
          v-model="email"
          type="email"
          label="Email"
          required
          aria-required="true"
        ></q-input>
        <q-input
          outlined
          v-model="subject"
          type="text"
          label="Subject"
          required
          aria-required="true"
        ></q-input>
        <q-input
          outlined
          v-model="message"
          type="textarea"
          label="Message"
          required
          aria-required="true"
        ></q-input>
        <q-btn
          no-caps
          class="romade-italic text-h6"
          type="submit"
          label="Submit"
          name="Submit"
        ></q-btn>
      </q-form>
    </div>
  </q-page>
</template>
