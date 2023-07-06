<script setup lang="ts">
import { PastWork } from 'src/PastWorkType';
defineProps<{
  pastWork: PastWork;
}>();
</script>

<template>
  <q-card>
    <q-img :src="pastWork.source">
      <div class="absolute-bottom text-h6 text-center">
        <a :href="pastWork.link">Link Here</a>
      </div>
    </q-img>
    <q-card-section>
      {{ pastWork.description }}
    </q-card-section>
  </q-card>
</template>
