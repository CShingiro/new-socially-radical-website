<script setup lang="ts">
import { PastWork } from 'src/PastWorkType';
defineProps<{
  pastWork: PastWork;
}>();
</script>

<template>
  <q-card class="card-style col-gutter-mixed">
    <q-img :src="pastWork.source">
      <div class="absolute-bottom text-h6 text-center">
        <a :href="pastWork.link" class="romade-italic">Link Here</a>
      </div>
    </q-img>
    <q-card-section class="text-center">
      {{ pastWork.description }}
    </q-card-section>
  </q-card>
</template>

<style>
.card-style {
  width: 100%;
  max-width: 450px;
}
</style>
