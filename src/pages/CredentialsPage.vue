<script setup lang="ts">
import CredentialsCard from 'src/components/CredentialsCard.vue';
const docs = [
  '/docs/AwardLetter.pdf',
  '/docs/CertificateCodeCademy.pdf',
  '/docs/CertificateNodeCodeCademy.pdf',
  '/docs/CertificateNodeSQLCodeCademy.pdf',
  '/docs/CertificateReactCodeCademy.pdf',
  '/docs/CertificateRubyCodeCademy.pdf',
  '/docs/ConestogaCertificate.pdf',
  '/docs/GSS证书7_55.pdf',
  '/docs/ProofofProgramCompletion.pdf',
  '/docs/VuejsForgeCertificate.pdf',
];
</script>

<template>
  <q-page class="row items-center justify-evenly gt-md">
    <div class="row items-center">
      <div class="col">
        <transition
          appear
          enter-active-class="animated zoomInUp delay-5s"
          leave-active-class="animated zoomOutUp delay-5s"
          :duration="5000"
        >
          <h1 class="romade-italic text-center">
            {{ $t('credentialsTitle') }}
          </h1>
        </transition>
      </div>
    </div>
    <credentials-card
      v-for="(doc, index) in docs"
      :key="index"
      :docSource="doc"
    ></credentials-card>
  </q-page>
  <q-page class="row items-center justify-evenly md">
    <div class="row items-center">
      <div class="col">
        <h3 class="romade-italic text-center">
          {{ $t('credentialsTitle') }}
        </h3>
      </div>
    </div>
    <credentials-card
      v-for="(doc, index) in docs"
      :key="index"
      :docSource="doc"
    ></credentials-card>
  </q-page>
  <q-page class="col items-center justify-evenly lt-md">
    <div class="col">
      <h5 class="romade-italic text-center">{{ $t('credentialsTitle') }}</h5>
    </div>
    <credentials-card
      v-for="(doc, index) in docs"
      :key="index"
      :docSource="doc"
    ></credentials-card>
  </q-page>
</template>
