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
  <q-page class="row items-center justify-evenly">
    <credentials-card
      v-for="(doc, index) in docs"
      :key="index"
      :docSource="doc"
    ></credentials-card>
  </q-page>
</template>
