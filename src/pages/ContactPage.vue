<script setup lang="ts">
import { ref, reactive } from 'vue';
import { ContactType } from 'src/ContactType';
import { api } from 'src/boot/axios';
import { useI18n } from 'vue-i18n';

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

const { t } = useI18n();

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

  alert(t('formSent'));
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
              {{ $t('contactTitle') }}
            </h1>
            <h3 class="romade-italic text-center md">Contact the Designer</h3>
            <h4 class="romade-italic text-center lt-md">
              {{ $t('contactTitle') }}
            </h4>
          </div>
        </div>
        <div class="row items-center">
          <div class="col">
            <h6 class="gt-md">
              {{ $t('contactNotice') }}
              <a href="https://sociallyradicalguitarist.com" target="_blank">{{
                $t('srgLink')
              }}</a
              >.
            </h6>
            <p class="md">
              {{ $t('contactNotice') }}
              <a href="https://sociallyradicalguitarist.com" target="_blank">{{
                $t('srgLink')
              }}</a
              >.
            </p>
            <span class="lt-md text-caption">
              {{ $t('contactNotice') }}
              <a href="https://sociallyradicalguitarist.com" target="_blank">{{
                $t('srgLink')
              }}</a
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
          :label="$t('formFirstName')"
          required
          aria-required="true"
        ></q-input>
        <q-input
          outlined
          v-model="lastName"
          type="text"
          :label="$t('formLastName')"
          required
          aria-required="true"
        ></q-input>
        <q-input
          outlined
          v-model="email"
          type="email"
          :label="$t('formEmail')"
          required
          aria-required="true"
        ></q-input>
        <q-input
          outlined
          v-model="subject"
          type="text"
          :label="$t('formSubject')"
          required
          aria-required="true"
        ></q-input>
        <q-input
          outlined
          v-model="message"
          type="textarea"
          :label="$t('formMessage')"
          required
          aria-required="true"
        ></q-input>
        <q-btn
          no-caps
          class="romade-italic text-h6"
          type="submit"
          :label="$t('formSubmit')"
          name="Submit"
        ></q-btn>
      </q-form>
    </div>
  </q-page>
</template>
