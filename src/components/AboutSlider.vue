<template>
    <div class="Tab-slider">
        <swiper  :slidesPerView="1"
        :spaceBetween="0"
        :navigation="true"
        :loop="true"
        :autoplay="{
            disableOnInteraction: false,
        }"
        :speed="1500"
        :modules="modules"
        class="image-swiper">
            <swiper-slide>
                <div class="lst-image-wrapper">
                    <img :src="$props.slideData?.img" alt="" />
                </div>
            </swiper-slide>
            <swiper-slide>
                <div class="lst-image-wrapper">
                    <img :src="$props.slideData?.img1" alt="" />
                </div>
            </swiper-slide>
            <swiper-slide>
                <div class="lst-image-wrapper">
                    <img :src="$props.slideData?.img" alt="" />
                </div>
            </swiper-slide>
            <swiper-slide>
                <div class="lst-image-wrapper">
                    <img :src="$props.slideData?.img1" alt="" />
                </div>
            </swiper-slide>
        </swiper>
    </div>
</template>
<script>
// Import Swiper Vue.js components
import { Swiper, SwiperSlide } from "swiper/vue";

// Import Swiper styles
import "swiper/css";
import "swiper/css/navigation";
import "swiper/css/pagination";

// import required modules
import { Navigation, Pagination, Scrollbar } from "swiper";

export default {
    name: "AboutSlider",
    components: {
        Swiper,
        SwiperSlide,
    },
    props: {
        slideData: Object
    },
    setup() {
        return {
            modules: [Navigation, Pagination, Scrollbar],
        };
    },
};
</script>
  
<style lang="scss">
.Tab-slider {
    width: 100%;
    position: relative;

    .image-swiper {
        width: 500px;
        position: static;

        .swiper-pagination {
            &.swiper-pagination-bullets {
                bottom: 27px;
            }
        }

        .swiper-pagination-bullet {
            width: 10px;
            height: 10px;
            border: 1px solid #fff;
            background: transparent;
            margin: 0 16px 0 0 !important;
            opacity: 1;

            &.swiper-pagination-bullet-active {
                background: #ffff;
            }

            &:last-child {
                margin-right: 0 !important;
            }
        }

        .swiper-button-prev,
        .swiper-button-next {
            width: 44px;
            height: 44px;
            border-radius: 100%;
            border: 1px solid #181818;
            bottom: 100px;
            top: auto;
            transform: none;
            position: absolute;
            margin-top: 30px;
            &::after {
                content: ' ';
            }

            @media(max-width:1500px) {
                width: 38px;
                height: 38px;
                bottom: 40px;
            }
        }

        .swiper-button-prev {
           
            left:-100%;
            margin-left: 130px;
            background: url(@/assets/icons/blk-arrow-left.svg) no-repeat;
            background-size: auto;
            background-position: center;
            top: 70%;
        }

        .swiper-button-next {
            right:-60%;
            background: url(@/assets/icons/blk-arrow-right.svg) no-repeat;
            background-size: auto;
            background-position: center;
            left: -64%;
            top: 70%;
        }

    }
}</style>