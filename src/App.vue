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

    <v-card class="image" style="margin-top: 240px;" @click="show0=!show0">
    <img src="./assets/mtfuji.jpg" alt="富士山">
    <p>{{ fuji[lang] }}</p>
    <v-expand-transition>
      <div v-show="show0">
        <v-divider></v-divider>
        <v-card-text>
          {{ fuji_exp[lang] }}
        </v-card-text>
      </div>
    </v-expand-transition>
    </v-card>

    <v-card class="image" @click="show1=!show1">
    <img src="./assets/toyota_car.jpg" alt="TOYOTA">
    <p>{{ toyota[lang] }}</p>
    <v-expand-transition>
      <div v-show="show1">
        <v-divider></v-divider>
        <v-card-text>
          {{ toyota_exp[lang] }}
        </v-card-text>
      </div>
    </v-expand-transition>
    </v-card>

    <v-card class="image"  @click="show2=!show2">
    <img src="./assets/anime_jp.jpg" alt="アニメ">
    <p>{{ anime[lang] }}</p>
    <v-expand-transition>
      <div v-show="show2">
        <v-divider></v-divider>
        <v-card-text>
          {{ anime_exp[lang] }}
        </v-card-text>
      </div>
    </v-expand-transition>
    </v-card>

    <v-card class="image"  @click="show3=!show3">
    <img src="./assets/ninja.jpg" alt="忍者">
    <p>{{ ninja[lang] }}</p>
    <v-expand-transition>
      <div v-show="show3">
        <v-divider></v-divider>
        <v-card-text>
          {{ ninja_exp[lang] }}
        </v-card-text>
      </div>
    </v-expand-transition>
    </v-card>

    <v-card class="image" @click="show4=!show4">
    <img src="./assets/toyotakosen.png" alt="豊田高専">
    <p>{{ kosen[lang] }}</p>
    <v-expand-transition>
      <div v-show="show4">
        <v-divider></v-divider>
        <v-card-text>
          {{ kosen_exp[lang] }}
        </v-card-text>
      </div>
    </v-expand-transition>
    </v-card>

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
v-card {
  vertical-align:middle;
}
/* .img-sized {
  width: 50%;
  height: auto;
  margin: 0 auto;
} */
img {
  width: 100%;
  height: auto;
}
/* img {
  animation: rotate-anime 3s linear infinite;
} */
/* @keyframes rotate-anime {
  0%  {transform: rotate(0);}
  100%  {transform: rotate(360deg);}
  50% {transform: rotateY(90deg);}
  100% {transform: rotateY(180deg);}
} */
.image {
  position: relative;
  }
.image img {
  opacity: 0.6;
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
    show0: 0,
    show1: 0,
    show2: 0,
    show3: 0,
    show4: 0,
    fuji: ["美しい国、日本", "Japan is beautiful country.", "日本是一个美丽的国家。"],
    fuji_exp: ["日本へようこそ。日本には美しい自然や景観、匠の技、伝統芸能などがあります。", "Welcome to Japan... Japan is home to beautiful nature and scenery, master craftsmen's techniques, and traditional arts.", "欢迎来到日本... 日本拥有美丽的自然风光、大师级的工艺技术和传统艺术。"],
    toyota: ["世界に誇る日本の車", "Japanese cars that we can be proud of in the world.", "我们可以在世界上引以为傲的日本车"],
    toyota_exp: ["日本のTOYOTAは世界的に有名な大企業で最新の車を作り続けています。", "Japan's TOYOTA is a world-famous giant company that continues to make the latest cars.", "日本的TOYOTA是世界著名的巨头公司，不断制造最新的汽车。"],
    anime: ["世界を魅了する日本のアニメ", "Japanese Anime that attracts the world.", "吸引世界的日本动漫"],
    anime_exp: ["日本のアニメは海外でも人気で、大規模な市場を形成しています。またコスプレや漫画などのサブカルチャーも注目を集めています。", "Japanese animation is also popular overseas and has created a large market. Subcultures such as cosplay and manga are also attracting a lot of attention.",
    "日本动画在海外也很受欢迎，创造了很大的市场。 cosplay、漫画等亚文化也备受关注。"],
    ninja: ["日本の伝統文化", "Japanese Traditional Culture", "日本传统文化"],
    ninja_exp: ["日本の伝統文化は、神道を基軸として外来の文化を取り込みながら、時代とともに変遷してきました。", "Japan's traditional culture has changed over time, incorporating foreign cultures with Shinto as its foundation.", "日本的传统文化以神道为基础，同时又融入了外来文化，随着时间的推移而不断发展。"],
    kosen: ["技術立国を支える高専", "KOSEN - Supporting a technological nation", "KOSEN - 支持技术国家"],
    kosen_exp: ["高専は日本の高等教育機関で、戦後に設立されてから今まで日本の工業化を支えてきました。", "KOSEN is an institution of higher education in Japan and has supported Japan's industrialization since its establishment after World War II.", "国立技术大学是日本的一所高等院校，自战后成立以来，一直支持着日本的工业化进程。"],
  }),
};
</script>
