<script setup lang="ts"></script>

<template>
  <q-page class="gt-md row items-center justify-evenly">
    <transition
      appear
      enter-active-class="animated fadeInLeft delay-3s"
      leave-active-class="animated fadeOutLeft delay-3s"
      :duration="5000"
    >
      <q-img class="logo col" src="/Images/g1643.png"></q-img>
    </transition>
    <div class="col">
      <transition
        appear
        enter-active-class="animated fadeInDown delay-3s"
        leave-active-class="animated fadeOutDown delay-3s"
        :duration="5000"
      >
        <h4 class="romade-italic">{{ $t('websiteWelcome') }}</h4>
      </transition>
      <div class="row items-center justify-evenly">
        <div class="col">
          <transition
            appear
            enter-active-class="animated fadeInUp delay-3s"
            leave-active-class="animated fadeOutUp delay-3s"
            :duration="5000"
          >
            <q-btn
              no-caps
              class="romade-italic"
              outline
              :label="$t('aboutTitle')"
              to="/about"
            ></q-btn>
          </transition>
        </div>
        <div class="col">
          <transition
            appear
            enter-active-class="animated fadeInRight delay-3s"
            leave-active-class="animated fadeOutRight delay-3s"
            :duration="5000"
          >
            <q-btn
              no-caps
              class="romade-italic"
              outline
              :label="$t('contactButton')"
              to="/contact"
            ></q-btn>
          </transition>
        </div>
      </div>
    </div>
  </q-page>
  <q-page class="lt-lg row items-center justify-evenly">
    <q-img class="logo row center" src="/Images/g1643.svg"></q-img>
    <h5 class="romade-italic text-center">
      {{ $t('websiteWelcome') }}
    </h5>
    <div class="row items-center justify-evenly">
      <div class="col-gutter-mixed">
        <q-btn
          no-caps
          class="romade-italic"
          flat
          :label="$t('aboutTitle')"
          to="/about"
        ></q-btn>
      </div>
      <div class="col-gutter-mixed">
        <q-btn
          no-caps
          class="romade-italic"
          flat
          :label="$t('contactButton')"
          to="/contact"
        ></q-btn>
      </div>
    </div>
  </q-page>
</template>

<style scoped>
.logo {
  width: '100%';
  max-width: '250px';
}
</style>
