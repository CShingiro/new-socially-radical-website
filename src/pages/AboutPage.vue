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
        <h1 class="romade-italic">About the Designer</h1>
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
            <strong key="emphasis">Marthad Shingiro Umucyaba</strong>, nee
            Christian Shingiro, is a graduate of the Internet Applications and
            Web Development Fundamentals Program at Conestoga College. He
            already has many projects under his belt, and is the web master and
            host of a radio show called
            <a key="self-link" href="https://sociallyradicalguitarist.com">
              The Socially Radical Guitarist</a
            >. His specialties are UI/UX design, Wordpress, Bootstrap, Vuejs,
            PHP, MySQL, and general Full Stack web development on Linux. He aims
            to be Socially Radical, while providing web services at a rate
            that's socially reasonable. You can go
            <a key="pro-link" href="https://github.com/CShingiro">here</a>
            for his public GitHub of complete and ongoing projects.
          </h6>
        </transition-group>
      </div>
    </div>
  </q-page>
  <q-page class="row items-center justify-evenly md">
    <div class="row">
      <h3 class="romade-italic">About the Designer</h3>
    </div>
    <div class="row">
      <q-img
        img-class="col self-center"
        src="/Images/MarthadUmucyaba.jpg"
        width="40%"
      ></q-img>
      <div class="col">
        <span>
          <strong>Marthad Shingiro Umucyaba</strong>, nee Christian Shingiro, is
          a graduate of the Internet Applications and Web Development
          Fundamentals Program at Conestoga College. He already has many
          projects under his belt, and is the web master and host of a radio
          show called
          <a href="https://sociallyradicalguitarist.com">
            The Socially Radical Guitarist</a
          >. His specialties are UI/UX design, Wordpress, Bootstrap, Vuejs, PHP,
          MySQL, and general Full Stack web development on Linux. He aims to be
          Socially Radical, while providing web services at a rate that's
          socially reasonable. You can go
          <a href="https://github.com/CShingiro">here</a>
          for his public GitHub of complete and ongoing projects.
        </span>
      </div>
    </div>
  </q-page>
  <q-page class="row items-center justify-evenly lt-md">
    <q-img src="/Images/MarthadUmucyaba.jpg">
      <div class="absolute-bottom text-h5 text-center romade-italic">
        About The Designer
      </div>
    </q-img>
    <div class="row">
      <span class="text-caption">
        <strong>Marthad Shingiro Umucyaba</strong>, nee Christian Shingiro, is a
        graduate of the Internet Applications and Web Development Fundamentals
        Program at Conestoga College. He already has many projects under his
        belt, and is the web master and host of a radio show called
        <a href="https://sociallyradicalguitarist.com">
          The Socially Radical Guitarist</a
        >. His specialties are UI/UX design, Wordpress, Bootstrap, Vuejs, PHP,
        MySQL, and general Full Stack web development on Linux. He aims to be
        Socially Radical, while providing web services at a rate that's socially
        reasonable. You can go <a href="https://github.com/CShingiro">here</a>
        for his public GitHub of complete and ongoing projects.
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
