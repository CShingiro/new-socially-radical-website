<script setup lang="ts">
import { PastWork } from 'src/PastWorkType';
defineProps<{
  pastWork: PastWork;
}>();
</script>

<template>
  <transition-group
    appear
    enter-active-class="animated rollIn delay-2s"
    leave-active-class="animated rollOut delay-2s"
    :duration="5000"
  >
    <q-card key="card" class="card-style col-gutter-mixed" flat>
      <q-img key="project-image" :src="pastWork.source">
        <div key="divider" class="absolute-bottom text-h6 text-center">
          <a
            key="link"
            :href="pastWork.link"
            target="_blank"
            class="romade-italic change-active"
            >Link Here</a
          >
        </div>
      </q-img>
      <q-card-section key="text" class="text-center">
        {{ pastWork.description }}
      </q-card-section>
    </q-card>
  </transition-group>
</template>

<style scoped>
.card-style {
  width: 100%;
  max-width: 450px;
}

.change-active {
  color: white;
}
</style>
