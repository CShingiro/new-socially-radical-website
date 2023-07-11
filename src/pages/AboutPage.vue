<script setup lang="ts"></script>

<template>
  <q-page class="row items-center justify-evenly gt-md">
    <div class="row">
      <transition
        appear
        enter-active-class="animated fadeInDown delay-3s"
        leave-active-class="animated fadeOutDown delay-3s"
        :duration="5000"
      >
        <h1 class="romade-italic">{{ $t('aboutTitle') }}</h1>
      </transition>
    </div>
    <div class="row">
      <div class="col gt-md">
        <transition
          appear
          enter-active-class="animated fadeInBottomLeft delay-3s"
          leave-active-class="animated fadeOutBottomLeft delay-3s"
          :duration="5000"
        >
          <q-img
            width="80%"
            class="about-picture"
            src="/Images/MarthadUmucyaba.jpg"
          ></q-img>
        </transition>
      </div>
      <div class="col">
        <transition-group
          appear
          enter-active-class="animated fadeInBottomRight delay-3s"
          leave-active-class="animated fadeOutBottomRight delay-3s"
          :duration="5000"
        >
          <h6 key="font-size">
            <strong key="emphasis">{{ $t('aboutDetailsPartOne') }}</strong
            >{{ $t('aboutDetailsPartTwo') }}
            <a key="self-link" href="https://sociallyradicalguitarist.com">
              {{ $t('srgLink') }}</a
            >{{ $t('aboutDetailsPartThree') }}
            <a key="pro-link" href="https://github.com/CShingiro">{{
              $t('githubLink')
            }}</a>
            {{ $t('aboutDetailsPartFour') }}
          </h6>
        </transition-group>
      </div>
    </div>
  </q-page>
  <q-page class="row items-center justify-evenly md">
    <div class="row">
      <h3 class="romade-italic">{{ $t('aboutTitle') }}</h3>
    </div>
    <div class="row">
      <q-img
        img-class="col self-center"
        src="/Images/MarthadUmucyaba.jpg"
        width="40%"
      ></q-img>
      <div class="col">
        <span>
          <strong>{{ $t('aboutDetailsPartOne') }}</strong
          >{{ $t('aboutDetailsPartTwo') }}
          <a href="https://sociallyradicalguitarist.com"> {{ $t('srgLink') }}</a
          >{{ $t('aboutDetailsPartThree') }}
          <a href="https://github.com/CShingiro">{{ $t('githubLink') }}</a>
          {{ $t('aboutDetailsPartFour') }}
        </span>
      </div>
    </div>
  </q-page>
  <q-page class="row items-center justify-evenly lt-md">
    <q-img src="/Images/MarthadUmucyaba.jpg">
      <div class="absolute-bottom text-h5 text-center romade-italic">
        {{ $t('aboutTitle') }}
      </div>
    </q-img>
    <div class="row">
      <span class="text-caption">
        <strong>{{ $t('aboutDetailsPartOne') }}</strong
        >{{ $t('aboutDetailsPartTwo') }}
        <a href="https://sociallyradicalguitarist.com"> {{ $t('srgLink') }}</a
        >{{ $t('aboutDetailsPartThree')
        }}<a href="https://github.com/CShingiro">{{ $t('githubLink') }}</a>
        {{ $t('aboutDetailsPartFour') }}
      </span>
    </div>
  </q-page>
</template>

<style scoped>
.about-picture {
  width: '100%';
  max-width: '250px';
}
</style>
