<template>
    <div class="d-flex align-items-center mt-3">
        <div class="w-25">
            <img class="my-image" src="../assets/images/Black-bg-photo.jpg" alt="">
        </div>
        <div>
            <h2 class="text-danger">About Me:</h2>
            <p class="text-light fs-3">Ciao sono Federico Manni e sono un Junior Full Stack Web Developer. mi considero una persona socievole e comunicativa, con una naturale propensione al lavoro di squadra. Sono appassionato di tecnologia e mi entusiasma l'idea di contribuire a progetti innovativi, mentre continuo a cercare nuove opportunità per crescere sia professionalmente che personalmente.</p>
        </div>
    </div>
    <div class="text-center my-5 py-5">
        <h2 class="text-danger">Le mie competenze:</h2>
    
        <swiper
        :slidesPerView="4"
        :spaceBetween="0"
        :autoplay="{
        delay: 2500,
        disableOnInteraction: false,
        }"
        :pagination="{
        clickable: true,
        }"
        :navigation="true"
        :modules="modules"
        class="mySwiper"
    >
        <swiper-slide class="text-light fs-2"><img class="logos" src="/public/images/html-logo.png" alt=""></swiper-slide>
        <swiper-slide class="text-light fs-2"><img class="logos" src="/public/images/css-logo.png" alt=""></swiper-slide>
        <swiper-slide class="text-light fs-2"><img class="logos" src="/public/images/bootstrap-logo.png" alt=""></swiper-slide>
        <swiper-slide class="text-light fs-2"><img class="logos" src="/public/images/javascript-logo.png" alt=""></swiper-slide>
        <swiper-slide class="text-light fs-2"><img class="logos" src="/public/images/scss-logo.png" alt=""></swiper-slide>
        <swiper-slide class="text-light fs-2"><img class="logos" src="/public/images/vue-logo.png" alt=""></swiper-slide>
        <swiper-slide class="text-light fs-2"><img class="logos" src="/public/images/laravel-logo.png" alt=""></swiper-slide>
        <swiper-slide class="text-light fs-2"><img class="logos" src="/public/images/php-logo.png" alt=""></swiper-slide>    
        
        </swiper>

    </div>   


    <!-- <div class="d-flex flex-column align-items-center justify-content-center">
        <h2 class="text-danger">Le mie competenze:</h2>
        <div class="text-light d-flex align-items-center justify-content-center m-2 py-2 text-decoration-underline">
            <div>
                <h4>HTML</h4>
            </div>
            <div>
                <h4>CSS</h4>
            </div>
            <div>
                <h4>Bootstrap</h4>
            </div>
            <div>
                <h4>Javascript</h4>
            </div>
            <div>
                <h4>SCSS</h4>
            </div>
            <div>
                <h4>Vue JS</h4>
            </div>
            <div>
                <h4>Laravel</h4>
            </div>
            <div>
                <h4>PHP</h4>
            </div>
        </div>
    </div> -->
    <div class="text-light text-center my-5 py-3">
        <h2 class="text-danger">Soft Skills: </h2>
        <p class="fs-4">Doti relazionali, comunicative ed organizzative</p>
        <p class="fs-4">Attitudine al teamwork</p>
        <p class="fs-4">Abilità analitiche e di Problem Solving</p>
        <p class="fs-4">Gestione del tempo e delle priorità</p>
    </div>
    <div class="text-center m-2">
        <h2 class="fs-2 my-4 text-danger">
            Contacts:
        </h2>
        <p class="text-light fs-4 text-decoration-underline">+39 345 92 32 030</p>
        <p class="text-light fs-4 text-decoration-underline">Email: manni_federico@libero.it</p>
        <p class="text-light fs-4 text-decoration-underline">Github: github.com/federicomanni97</p>
        <p class="text-light fs-4 text-decoration-underline">Linkedin: linkedin.com/in/federicomanni2909/</p>
    </div>
</template>

<script>
  import { Swiper, SwiperSlide } from 'swiper/vue';
  import 'swiper/css';
  import 'swiper/css/pagination';
  import { Autoplay, Pagination, Navigation } from 'swiper/modules';

  export default {
    components: {
      Swiper,
      SwiperSlide,
    },
    setup() {
      return {
        modules: [Autoplay, Pagination, Navigation],
      };
    },
  };
</script>