<template>
<client-only>
    <swiper ref="swiper" :options="swiperOption">
        <slide v-for="(slide,index) in slides" :key="index" :slide="slide" />
        <div class="swiper-pagination" slot="pagination" />
    </swiper>
</client-only>
</template>

<script>
import Slide from "~/components/swiper/slide.vue"
export default {
    props: {
        slides: {
            type: Array,
            required: true
        }
    },
    components: {
        Slide
    },
    data() {
        return {
            swiperOption: {
                grabCursor: true,
                pagination: {
                    el: ".swiper-pagination"
                },
                navigation: {
                    nextEl: ".swiper-button-next",
                    prevEl: ".swiper-button-prev"
                },
                autoHeight: true
            }

        }
    }

}
</script>


