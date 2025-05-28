<template>
  <div>
    <div class="nav" :class="{ 'nav-open': isNavOpen }">
      <div class="photo-containe">
        <span>Filip Pędziński</span>
        <div class="photo">
          <img class="profil" src="../assets/profil.jpg" alt="" />
        </div>
      </div>
      <div class="info">
        <ul>
          <li>Miasto: Murowana Goślina</li>
          <li>Wiek: 17 lat</li>
        </ul>
      </div>
      <div class="line"></div>

      <h3 class="skills">UMIEJĘTNOŚCI</h3>

      <ul class="skills">
        <li class="skill">HTML</li>
        <div class="html"></div>

        <li class="skill">CSS</li>
        <div class="css"></div>

        <li class="skill">JavaScript</li>
        <div class="javaScript"></div>

        <li class="skill">Vue</li>
        <div class="vue"></div>

        <li class="skill">PhP</li>
        <div class="php"></div>

        <li class="skill">SQL</li>
        <div class="sql"></div>

        <li class="skill">c++</li>
        <div class="sql"></div>

        <li class="skill">c#</li>
        <div class="sql"></div>

        <li class="skill">Java</li>
        <div class="sql"></div>
      </ul>
    </div>

    <!-- Przycisk do rozwijania/zwijania -->
    <button @click="toggleNav" class="toggle-button" :class="{ 'right-position': isNavOpen, 'cross-icon': isNavOpen }"></button>

    <div class="main">
      <h1>O mnie</h1>
      <ul class="about-info">
        <li>2 lata nauki</li>
        <li>0 wykonanych projektów</li>
        <li>Opinie</li>
      </ul>

      <h2>Moje projekty</h2>
      <slider></slider>
    </div>
  </div>
</template>


<style src="../assets/global.css"> 

</style>

<script>
import slider from "./slider.vue";

export default {
  components: { slider },
  name: "AboutPage",
  data() {
    return {
      isNavOpen: false,
    };
  },
  methods: {
    toggleNav() {
      this.isNavOpen = !this.isNavOpen;
    },
  },
};
</script>
