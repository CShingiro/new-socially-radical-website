<script setup lang="ts">
import { ref } from 'vue';

const firstName = ref('');
const lastName = ref('');
const email = ref('');
const subject = ref('');
const message = ref('');
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
      <q-form
        name="Contact Form"
        enctype="text/plain"
        action="https://docs.google.com/forms/d/e/1FAIpQLScWwAELW8_g2anrilDyH3UGDZrXfZPR-OyAQlUe7q_jAdTclQ/viewform?usp=pp_url"
      >
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
