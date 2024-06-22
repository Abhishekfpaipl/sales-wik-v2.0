<template>
    <div class="container-fluid p-5  bg-dark" style="background-image: url('/img/level.png')">
        <div class="">
            <div class="d-flex flex-column justify-content-center align-items-center">
                <img src="/img/famefoottag.svg" style="width: 300px; max-width: 80%; filter: invert(1)" alt="">
                <p class="mb-0  text-white text-capitalize">" we are absolutely thrilled and honored to be
                    best Lead management software in India  <span v-if="service">in {{ service }}</span> <span v-if="category">, in {{ category }}</span> <span v-if="place">in {{ place
                        }}.</span> "
                </p>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    name: "FameFoot",
    props: ['service', 'category', 'place'],
}
</script>
<style></style>