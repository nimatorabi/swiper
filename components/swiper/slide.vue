<template>
<div>
    <div class="mx-auto outer-swiper">
        <swiper-slide class="bg-white shadow-lg mx-auto swiper-cutsom rounded">
            <div class="d-flex flex-column mx-auto text-center">
                <img v-if="slide.picture" :src="slide.picture.large" class="mx-auto mt-5 rounded-circle" alt="">
                <h5 class="pt-4 pb-2">{{fullname}}</h5>
                <p class="px-5 py-4 text-muted">
                    Lorem ipsum dolor sit amet consectetur adipisicing elit. Deserunt quibusdam quidem culpa, repellat eum nobis reiciendis sed distinctio, placeat facilis sit nesciunt officia molestias error a impedit dolorum minima et quisquam sunt earum obcaecati maiores sequi! Earum aut molestiae molestias nemo? Recusandae, fugit? Aut, ducimus.
                </p>
            </div>
        </swiper-slide>
    </div>
</div>
</template>

<script>
export default {
    props: {
        slide: {
            type: Object,
            required: true
        }
    },
    computed: {
        fullname() {
            if (this.slide.location && this.slide.name) {
                return `${this.slide.name.first} ${this.slide.name.last},${this.slide.location.city}`
            }
        }
    }

}
</script>

<style lang="scss" scoped>
.outer-swiper {
    max-height: 310px;
    max-width: 1050px !important;
    background: #754EF9;
}

.swiper-cutsom {
    max-width: 980px !important;
    position: relative;
    top: -2rem;
}

img {
    box-shadow: 0 0 0 7px #754EF9,
        0 0 0 15px #764ef9a6;
}
</style>
