<script setup lang="ts">
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
  <q-page>
    <q-pdfviewer
      v-for="(doc, index) in docs"
      :src="doc"
      :key="index"
      type="pdfjs"
    >
    </q-pdfviewer>
  </q-page>
</template>
