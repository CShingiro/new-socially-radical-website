<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          icon="img:/Images/g1643.png"
          aria-label="Menu"
          @click="toggleLeftDrawer"
        />

        <q-toolbar-title class="romade-italic">
          Socially Radical Web Design
        </q-toolbar-title>

        <div>Quasar v{{ $q.version }}</div>
      </q-toolbar>
    </q-header>

    <q-drawer v-model="leftDrawerOpen" show-if-above bordered>
      <q-list>
        <q-item-label header> Essential Links </q-item-label>

        <EssentialLink
          v-for="link in essentialLinks"
          :key="link.title"
          v-bind="link"
        />
      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import EssentialLink, {
  EssentialLinkProps,
} from 'components/EssentialLink.vue';

const essentialLinks: EssentialLinkProps[] = [
  {
    title: 'Home',
    caption: 'Home Page',
    icon: 'home',
    link: '/',
  },
  {
    title: 'About',
    caption: 'About the Developer',
    icon: 'code',
    link: '/about',
  },
  {
    title: 'Credentials',
    caption: 'Credentials and Qualifications',
    icon: 'ion-desktop',
    link: '/credentials',
  },
  {
    title: 'Past Work',
    caption: 'Past quality work',
    icon: 'ion-briefcase',
    link: '/past-work',
  },
  {
    title: 'Contact',
    caption: 'Contact Socially Radical Web Design',
    icon: 'ion-mail',
    link: '/contact',
  },
];

const leftDrawerOpen = ref(false);

function toggleLeftDrawer() {
  leftDrawerOpen.value = !leftDrawerOpen.value;
}
</script>
