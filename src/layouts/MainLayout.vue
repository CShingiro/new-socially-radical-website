<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar class="bg-grey">
        <q-btn
          class="lt-md"
          flat
          dense
          round
          icon="img:/Images/g1643.png"
          aria-label="Menu"
          @click="toggleLeftDrawer"
        />
        <q-item to="/" active-class="white">
          <q-toolbar-title class="romade-italic" to="/">
            Socially Radical Web Design
          </q-toolbar-title>
        </q-item>
        <q-space></q-space>
        <q-space></q-space>
        <q-space></q-space>
        <div class="gt-md row justify-evenly">
          <q-btn
            icon="code"
            no-caps
            flat
            label="About"
            to="/about"
            class="romade-italic"
          ></q-btn>
          <q-btn
            icon="ion-desktop"
            no-caps
            flat
            label="Credentials"
            to="/credentials"
            class="romade-italic col-gutter-mixed"
          ></q-btn>
          <q-btn
            icon="design_services"
            no-caps
            flat
            label="Past Work"
            to="/past-work"
            class="romade-italic col-gutter-mixed"
          ></q-btn>
          <q-btn
            icon="ion-mail"
            no-caps
            flat
            label="Contact"
            to="/contact"
            class="romade-italic col-gutter-mixed"
          ></q-btn>
        </div>
      </q-toolbar>
    </q-header>

    <q-drawer class="lt-md" v-model="leftDrawerOpen" bordered>
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

    <q-footer>
      <q-toolbar class="bg-grey">
        <q-btn
          href="https://www.facebook.com/SociallyRadicalWebDesign"
          target="_blank"
          aria-label="Facebook"
          flat
        >
          <q-icon name="facebook" color="white"></q-icon>
        </q-btn>
        <q-btn
          href="https://www.instagram.com/sociallyradicalwebdesign"
          target="_blank"
          aria-label="Instagram"
          flat
        >
          <q-icon name="ion-logo-instagram" color="white"></q-icon>
        </q-btn>
        <q-btn
          href="https://twitter.com/web_socially"
          target="_blank"
          aria-label="Twitter"
          flat
        >
          <q-icon name="ion-logo-twitter" color="white"></q-icon>
        </q-btn>
        <q-btn
          href="https://www.youtube.com/channel/UCA7dy966M7PRd_Gu1mtyugA"
          target="_blank"
          aria-label="Rumble"
          flat
        >
          <q-icon name="ion-logo-youtube" color="white"></q-icon>
        </q-btn>
        <q-space />
        <q-btn
          flat
          no-caps
          class="romade-italic"
          aria-label="Fair Use Copyright 2021 Socially Radical Guitarist"
        >
          <q-icon name="copyright" color="white"></q-icon>
          2022 - Socially Radical Web Design
        </q-btn>
      </q-toolbar>
    </q-footer>
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
    icon: 'design_services',
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
