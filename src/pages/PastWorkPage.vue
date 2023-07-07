<script setup lang="ts">
import ProjectsCard from 'src/components/ProjectsCard.vue';
import { theBestWorkDone } from 'src/PastWorkDetails';

const pastStuff = theBestWorkDone;
</script>

<template>
  <q-page class="row items-center justify-evenly gt-md">
    <div class="row">
      <transition
        appear
        enter-active-class="animated rollIn delay-3s"
        leave-active-class="animated rollOut delay-3s"
        :duration="5000"
      >
        <h1 class="romade-italic">Past Work</h1>
      </transition>
    </div>
    <projects-card
      v-for="(pastThing, index) in pastStuff"
      :pastWork="pastThing"
      :key="index"
    ></projects-card>
  </q-page>
  <q-page class="col items-center justify-evenly md">
    <h3 class="romade-italic">Past Work</h3>
    <projects-card
      v-for="(pastThing, index) in pastStuff"
      :pastWork="pastThing"
      :key="index"
    ></projects-card>
  </q-page>
  <q-page class="row items-center justify-evenly lt-md">
    <div class="row">
      <div class="col">
        <h4 class="romade-italic text-center">Past Work</h4>
      </div>
    </div>
    <div class="row">
      <div class="col-gutter-mixed">
        <projects-card
          v-for="(pastThing, index) in pastStuff"
          :pastWork="pastThing"
          :key="index"
        ></projects-card>
      </div>
    </div>
  </q-page>
</template>
