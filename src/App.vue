<template>
  <v-app>
    <v-card class="overflow-hidden">
    <v-app-bar
      color="#6A76AB"
      dark
      shrink-on-scroll
      prominent
      src="./assets/winter.jpg"
      fade-img-on-scroll
      scroll-target="#scrolling-techniques-4"
      fixed
    >
      <template v-slot:img="{ props }">
        <v-img
          v-bind="props"
          gradient="to top right, rgba(100,115,201,.7), rgba(25,32,72,.7)"
        ></v-img>
      </template>

      <!-- <v-app-bar-nav-icon></v-app-bar-nav-icon> -->

      <v-toolbar-title>Greeting Card</v-toolbar-title>

      <v-spacer></v-spacer>

      <!-- <v-btn icon>
        <v-icon>mdi-magnify</v-icon>
      </v-btn> -->

      <v-btn icon @click="type = !type">
        <v-icon :color="type==0 ? '#ffffff' : 'pink'">mdi-heart</v-icon>
      </v-btn>

      <template v-slot:extension>
        <v-tabs align-with-title>
          <v-tab @click="lang = 0">日本語</v-tab>
          <v-tab @click="lang = 1">English</v-tab>
          <v-tab @click="lang = 2">中文</v-tab>
        </v-tabs>
      </template>
    </v-app-bar>
    <!-- <v-sheet
      id="scrolling-techniques-4"
      class="overflow-y-auto"
      max-height="1000"
    > -->
      <!-- <v-container style="height: 1000px;"></v-container> -->
      <!-- <v-container style="height: 240px;" vertical-align:middle;></v-container> -->

    <div class="image" style="margin-top: 240px;">
    <img src="./assets/mtfuji.jpg" alt="富士山">
    <p>{{ fuji[lang] }}</p>
    </div>
    <div class="image">
    <img src="./assets/toyota_car.jpg" alt="TOYOTA">
    <p>{{ toyota[lang] }}</p>
    </div>
    <div class="image">
    <img src="./assets/anime_jp.jpg" alt="アニメ">
    <p>{{ anime[lang] }}</p>
    </div>
    <div class="image">
    <img src="./assets/ninja.jpg" alt="忍者">
    <p>{{ ninja[lang] }}</p>
    </div>
    <div class="image">
    <img src="./assets/toyotakosen.png" alt="豊田高専">
    <p>{{ kosen[lang] }}</p>
    </div>

    <!-- </v-sheet> -->
    </v-card>
  </v-app>
</template>

<style>
@import url('https://fonts.googleapis.com/css2?family=Courgette&family=Sawarabi+Mincho&family=Zhi+Mang+Xing&display=swap');
#app {
  /* font-family: 'Courgette', cursive; */
  font-family: 'Sawarabi Mincho', sans-serif;
  /* font-family: 'Zhi Mang Xing', cursive; */
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
}
div {
  vertical-align:middle;
}
.img-sized {
  width: 50%;
  height: auto;
  margin: 0 auto;
}
img {
  width: 100%;
  height: auto;
}
.image {
  position: relative;
  }
.image img {
  opacity: 0.7;
}
.image p {
  position: absolute;
  top: 50%;
  left: 50%;
  -ms-transform: translate(-50%,-50%);
  -webkit-transform: translate(-50%,-50%);
  transform: translate(-50%,-50%);
  margin:0;
  padding:0;
  font-size:25px;
  }
</style>

<script>
// import HelloWorld from './components/HelloWorld';
// import { Carousel, Slide } from 'vue-carousel';

export default {
  name: 'App',

  components: {
    // HelloWorld,
    // Carousel,
    // Slide
  },

  data: () => ({
    lang: 0,
    type: 0,
    fuji: ["美しい国、日本", "Japan is beautiful country.", "日本是一个美丽的国家。"],
    toyota: ["世界に誇る日本の車", "Japanese cars that we can be proud of in the world.", "我们可以在世界上引以为傲的日本车"],
    anime: ["世界を魅了する日本のアニメ", "Japanese Anime that attracts the world.", "吸引世界的日本动漫"],
    ninja: ["日本の伝統文化", "Japanese Traditional Culture", "日本传统文化"],
    kosen: ["技術立国を支える高専", "KOSEN - Supporting a technological nation", "KOSEN - 支持技术国家"],
  }),
};
</script>
