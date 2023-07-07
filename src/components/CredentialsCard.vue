<script setup lang="ts">
defineProps<{
  docSource: string;
}>();
</script>

<template>
  <q-card>
    <transition
      appear
      enter-active-class="animated zoomInUp delay-5s"
      leave-active-class="animated zoomOutUp delay-5s"
      :duration="5000"
    >
      <q-pdfviewer
        content-style="background-color: grey"
        inner-content-style="background-color: grey"
        type="html5"
        :src="docSource"
        error-string="Download the PDF to View it"
      ></q-pdfviewer>
    </transition>
  </q-card>
</template>
