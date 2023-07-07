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
    <q-form
      name="Contact Form"
      enctype="text/plain"
      action="https://docs.google.com/forms/d/e/1FAIpQLScWwAELW8_g2anrilDyH3UGDZrXfZPR-OyAQlUe7q_jAdTclQ/viewform?usp=pp_url"
    >
      <q-input v-model="firstName" type="text"></q-input>
      <q-input v-model="lastName" type="text"></q-input>
      <q-input v-model="email" type="email"></q-input>
      <q-input v-model="subject" type="text"></q-input>
      <q-input v-model="message" type="text"></q-input>
      <q-btn
        no-caps
        class="romade-italic"
        type="submit"
        label="Submit"
        name="Submit"
      ></q-btn>
    </q-form>
  </q-page>
</template>
