<script>
import 'vue3-carousel/dist/carousel.css'
import { Carousel, Slide, Pagination, Navigation } from 'vue3-carousel'
import FirstSlide from './components/FirstSlide.vue'


export default {
  name: 'App',
  components: {
    Carousel,
    Slide,
    Pagination,
    Navigation,
    FirstSlide,
    
  },
  data() {
    return {
      slidesPaths: ['./assets/first-slide.jpg', '../src/assets/second-slide.jpg', '../assets/third-slide.jpg', '../../src/assets/fifth-slide.jpg', '../../src/assets/sixth-slide.jpg', '../../src/assets/seventh-slide.jpg', '../../src/assets/eithts-slide.jpg'],
    }
  },
}
</script>

<template>
    <div class="container">
      <div class="logo-wrapper">
        <img src="./assets/logo.svg" alt="">
      </div>
    </div>
    <div class="bg">
      <h1 class="bg__title">Welcome to Latinos In Action!</h1>
    </div>
    <div class="line"></div>
    <div class="about__us container">
        <h2 class="about__us-title">About us:</h2>
        <p class="about__us-text">Latinos in Action is a national organization that empowers Latino youth to lead and strengthen their communities through college and career readiness. We focus on academic excellence, service, and cultural celebration. 🎓🌟</p>
    </div>
    <div class="container">
      <Carousel class="carousel" :autoplay="2000" :wrapAround="true" :transition="500" items-to-show="2.5" :items-to-show="1.5">
        <Slide v-for="(slidePath) in slidesPaths" :key="slide">
          <FirstSlide :url="slidePath" />
        </Slide>
        <template #addons>
          <Navigation />
          <Pagination />
        </template>
      </Carousel>
    </div>
    <div class="line"></div>
    <div class="why__us container">
      <h2 class="why__us-title">Why joining Latinos in Action is a great idea:</h2>
      <ul>
        <li>Embrace Cultural Heritage: celebrate and deepen your understanding of Latino culture.</li>
        <li>Develop leadership skills: take on roles that build confidence and leadership abilities.</li>
        <li>Academic Support:benefit from tutoring and resources to excel in your studies.</li>
        <li>Community service: give back through meaningful service projects and make a positive impact.</li>
        <li>Make lifelong friends: join a welcoming community where strong friendships are formed.</li>
      </ul>
    </div>
    <div class="footer-bg">
      <a style="cursor: auto; margin-bottom: 90px; margin-top: 30px;">Join today!</a>
      <a style="margin-bottom: 20px;">LIA Instagram</a>
      <a>LIA TikTok</a>
    </div>
</template>

<style scoped>
.container {
  max-width: 1200px;
  margin: 0 auto;
}

.line {
  border: 5px solid rgba(198, 107, 255, 1);
  margin-bottom: 30px;
}

.logo-wrapper {
  display: flex;
  justify-content: center;
}

.about__us {
  padding: 0 70px;
  padding-bottom: 30px;
}

.about__us-title {
  color: rgba(198, 107, 255, 1);
  font-family: 'Archivo Black';
  font-size: 25px;
  line-height: 27px;
  letter-spacing: 0em;
  text-align: center;
  padding-bottom: 15px;
}

.about__us-text {
  font-family: 'Caladea';
  font-size: 24px;
  line-height: 28px;
  letter-spacing: 0em;
  text-align: center;
}

.bg {
  background-image: url('./assets/main-bg.jpg');
  height: 234px;
  width: 100%;
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center;
  margin-bottom: 60px;
  margin-top: 30px;
  position: relative;
}

.bg__title {
  font-family: Archivo Black;
  font-size: 24px;
  line-height: 26px;
  letter-spacing: 0em;
  text-align: center;
  color: rgba(255, 255, 255, 1);
  background: linear-gradient(90deg, #C66BFF 0%, #600CCB 100%);
  box-shadow: 0px 4px 4px 0px rgba(0, 0, 0, 0.25);
  width: 255px;
  padding: 14px;
  position: absolute;
  left: 50%;
  transform: translateX(-50%);
  top: -32px;
}

.carousel {
  margin-bottom: 30px;
}

.why__us {
  padding: 0 40px 100px;
}

.why__us ul {
  padding-left: 20px;
}

.why__us ul li {
  font-family: 'Caladea';
  font-size: 24px;
  font-weight: 400;
  line-height: 28px;
  letter-spacing: 0em;
  text-align: left;
  margin-bottom: 20px;
}

.why__us-title {
  font-family: 'Archivo Black';
  font-size: 22px;
  font-weight: 400;
  line-height: 24px;
  letter-spacing: 0em;
  text-align: center;
  padding-bottom: 30px;
  color: rgba(198, 107, 255, 1);
}

.footer-bg {
  background-image: url('./assets/footer-bg.jpg');
  max-width: 100%;
  height: 405px;
  background-position: 39% 84%;
  background-repeat: no-repeat;
  background-size: cover;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.footer-bg a {
  text-decoration: none;
  width: 265px;
  font-family: 'Archivo Black';
  font-size: 27px;
  line-height: 29px;
  letter-spacing: 0em;
  text-align: center;
  background: linear-gradient(90deg, #C66BFF 0%, #600CCB 100%);
  padding: 20px 0;
  color: rgba(255, 255, 255, 1);
  cursor: pointer;
}

.img-slide {
  height: 275px;
  width: 158px;
}
</style>
