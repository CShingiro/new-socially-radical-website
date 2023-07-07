<script setup lang="ts">
defineProps<{
  docSource: string;
}>();
</script>

<template>
  <q-card>
    <transition
      appear
      enter-active-class="animated zoomInUp"
      leave-active-class="animated zoomOutUp"
      :duration="5000"
    >
      <q-pdfviewer
        content-style="background-color: grey"
        inner-content-style="background-color: grey"
        type="html5"
        :src="docSource"
      ></q-pdfviewer>
    </transition>
  </q-card>
</template>
