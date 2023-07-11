<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar class="bg-grey">
        <q-btn
          class="lt-lg"
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="toggleLeftDrawer"
        />
        <q-item to="/" active-class="white">
          <q-toolbar-title class="romade-italic" to="/">
            {{ $t('websiteTitle') }}
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
            :label="$t('aboutButton')"
            to="/about"
            class="romade-italic"
          ></q-btn>
          <q-btn
            icon="ion-desktop"
            no-caps
            flat
            :label="$t('credentialsButton')"
            to="/credentials"
            class="romade-italic col-gutter-mixed"
          ></q-btn>
          <q-btn
            icon="design_services"
            no-caps
            flat
            :label="$t('pastWork')"
            to="/past-work"
            class="romade-italic col-gutter-mixed"
          ></q-btn>
          <q-btn
            icon="ion-mail"
            no-caps
            flat
            :label="$t('contactButton')"
            to="/contact"
            class="romade-italic col-gutter-mixed"
          ></q-btn>
        </div>
        <q-select
          no-caps
          class="romade-italic"
          v-model="locale"
          :options="localeOptions"
          emit-value
          map-options
          options-dense
        >
          <template v-slot:option="scoped">
            <q-item :="scoped.itemProps">
              <q-item-section avatar>
                <q-icon :name="scoped.opt.icon"></q-icon>
              </q-item-section>
              <q-item-section class="romade-italic">
                {{ scoped.opt.label }}
              </q-item-section>
            </q-item>
          </template>
        </q-select>
      </q-toolbar>
    </q-header>

    <q-drawer class="lt-lg" v-model="leftDrawerOpen" bordered>
      <q-list>
        <q-item-label class="romade-italic" header>
          {{ $t('websiteTitle') }}
        </q-item-label>

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
          class="romade-italic gt-md"
          aria-label="Fair Use Copyright 2021 Socially Radical Guitarist"
        >
          <q-icon name="copyright" color="white"></q-icon>
          {{ $t('copyrightDesktop') }}
        </q-btn>
        <q-btn
          flat
          no-caps
          class="romade-italic lt-lg"
          aria-label="Copyright 2022 Socially Radical Web Design"
        >
          <q-icon name="copyright" color="white"></q-icon>
          {{ $t('copyrightMobile') }}
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
import { useI18n } from 'vue-i18n';

const { locale } = useI18n({ useScope: 'global' });
const { t } = useI18n();

const essentialLinks: EssentialLinkProps[] = [
  {
    title: t('home'),
    caption: t('homeCaption'),
    icon: 'home',
    link: '/',
  },
  {
    title: t('aboutButton'),
    caption: t('aboutTitle'),
    icon: 'code',
    link: '/about',
  },
  {
    title: t('credentialsButton'),
    caption: t('credentialsTitle'),
    icon: 'ion-desktop',
    link: '/credentials',
  },
  {
    title: t('pastWork'),
    caption: t('pastWorkCaption'),
    icon: 'design_services',
    link: '/past-work',
  },
  {
    title: t('contactButton'),
    caption: t('contactTitle'),
    icon: 'ion-mail',
    link: '/contact',
  },
];

const leftDrawerOpen = ref(false);

function toggleLeftDrawer() {
  leftDrawerOpen.value = !leftDrawerOpen.value;
}

const localeOptions = [
  { icon: 'img:/Images/gb.svg', value: 'en-US', label: 'English' },
  { icon: 'img:/Images/fr.svg', value: 'fr-FR', label: 'Français' },
  { icon: 'img:/Images/cn.svg', value: 'zh-CN', label: '简体中文' },
  { icon: 'img:/Images/hk.svg', value: 'zh-HK', label: '繁體中文' },
];
</script>
