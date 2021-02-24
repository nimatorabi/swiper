<template>
<b-container>
    <b-row>
        <b-col cols="12">
            <swiper :slides=list class="mt-5 pt-2" />
        </b-col>
    </b-row>
</b-container>
</template>

<script>
import Swiper from "~/components/swiper/index.vue"
export default {
    components: {
        Swiper
    },
    data() {
        return {
            list: []
        }
    },
    created() {
        this.getList()
    },
    methods: {
        async getList() {
            try {
                const {
                    data
                } = await this.$axios.get("https://randomuser.me/api/");
                this.list = data.results
            }catch{err=>{
                console.log("err",err);
            }}
        }
    }
}
</script>

<style>

</style>
