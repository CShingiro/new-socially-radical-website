<script setup lang="ts">
import ProjectsCard from 'src/components/ProjectsCard.vue';
import { theBestWorkDone } from 'src/PastWorkDetails';

const pastStuff = theBestWorkDone;
</script>

<template>
  <q-page class="row items-center justify-evenly">
    <projects-card
      v-for="(pastThing, index) in pastStuff"
      :pastWork="pastThing"
      :key="index"
    ></projects-card>
  </q-page>
</template>
