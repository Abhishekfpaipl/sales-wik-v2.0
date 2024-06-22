<template>
    <div class="">
        <div class="container px-3 px-md-0">
            <h1 class="text-center text-capitalize py-3">Capture leads from all lead sources</h1>
            <p class="">Boost your sales with seamless integration with google, facebook, indiamart, justdial, instagram , linkedin, youtube, whatsapp and pinterest.</p>
            <div class="row d-flex justify-content-center pb-5 pt-2">
                <div class="col-4 row row-cols-1 g-3 mt-0">
                    <div v-for="(service, index) in servicesLeft" :key="index" class="col">
                        <img :src="service.img" style="width: 50px" alt=""> 
                        <!-- <div class="d-flex align-items-center">
                            <p class="fs-5 fw-b title mb-0 ms-4">{{ service.title }}</p>
                        </div> -->
                    </div>
                </div>


                <div class="col-4 d-flex justify-content-center align-items-center">
                    <img src="/img/our-service.svg" class="d-none d-md-block" style="width:250px; object-fit: contain;">
                    <img src="/img/our-service.svg" class="d-md-none" style="width:80px; object-fit: contain;">
                </div>


                <div class="col-4 row row-cols-1 g-3 mt-0">
                    <div v-for="(service, index) in servicesRight" :key="index" class="col">
                        <img :src="service.img" style="width: 50px" alt=""> 
                        <!-- <div class="d-flex align-items-center"> -->
                            <!-- <p class="fs-5 fw-b title mb-0 ms-4">{{ service.title }}</p> -->
                        <!-- </div> -->
                    </div>
                </div>

            </div>
        </div>
    </div>
</template>
<script>
export default {
    name: "OurService",
    data() {
        return {
            servicesLeft: [
                {
                    id: 1,
                    title: "India Mart",
                    img: "/img/share/indiamart.png",
                },
                {
                    id: 2,
                    title: "Facebook",
                    img: "/img/share/facebook.png",
                },
                {
                    id: 3,
                    title: "Instagram",
                    img: "/img/share/insta.png",
                },
                {
                    id: 4,
                    title: "Just Dial",
                    img: "/img/share/justdial.png",
                },
            ],
            servicesRight: [
                {
                    id: 1,
                    title: "Pinterest",
                    img: "/img/share/pinterest.png",
                },
                {
                    id: 2,
                    title: "LinkedIn",
                    img: "/img/share/linkedin.png",
                },
                {
                    id: 3,
                    title: "WhatsApp",
                    img: "/img/share/whatsapp.png",
                },
                {
                    id: 4,
                    title: "Youtube",
                    img: "/img/share/Youtube.jpg",
                },
            ]


        }
    }
}
</script>
<style lang="">

</style>