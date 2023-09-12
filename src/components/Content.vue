<script setup>
</script>

<script>
// Import Swiper Vue.js components
import { Swiper, SwiperSlide } from 'swiper/vue';

// Import Swiper styles
import 'swiper/css';

import 'swiper/css/pagination';

import '../swiper.css';

// import required modules
import { Pagination } from 'swiper/modules';

export default {
    components: {
        Swiper,
        SwiperSlide,
    },
    setup() {
        return {
            modules: [Pagination],
        };
    },
    
};
</script>


<template>
    <div class="slid content h-[657px] w-[100%]">
        <div class="h-[100%] w-[90%] m-auto flex flex-col text-[#22343D]">
            <h2 class="text-[34px] font-[700]">{{ $t("education.content") }}</h2>
            <p class="mt-[18px] font-[500]">{{ $t("education.focusAway") }} </p>

            <div class="h-[385px] w-[100%] flex mt-[33px] justify-between">

                <swiper :slidesPerView="3"  :pagination="{
                    clickable: true,
                }" :modules="modules" class="mySwiper">

                    <swiper-slide v-for="item of 8" :key="item.id">
                        <div class="h-[250px] w-[350px] flex flex-col">
                            <img :src="`src/assets/slideslider/${item}.jpg`" alt="">
                        </div>
                    </swiper-slide>
                   
                    
                </swiper>








            </div>

            <!-- <div class="h-[20px] w-[100%] bg-[#979797] mt-[50px]"></div> -->

        </div>
    </div>
</template>

<style scoped>
@media screen and (max-width: 500px) {
    .slid{
        display: none !important;
    }
}
</style>