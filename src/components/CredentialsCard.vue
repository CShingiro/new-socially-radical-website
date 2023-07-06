<script setup lang="ts">
defineProps<{
  docSource: string;
}>();
</script>

<template>
  <q-card>
    <q-pdfviewer
      content-style="background-color: #ff0000"
      inner-content-style="background-color: #ff0000"
      type="html5"
      :src="docSource"
    ></q-pdfviewer>
  </q-card>
</template>
