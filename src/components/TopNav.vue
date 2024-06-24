<template>
    <div class="bg-light position-fixed top-0 w-100 d-flex justify-content-between align-items-center border-bottom px-md-4 px-2"
        style="z-index: 999;">
        <div class="p-2">
            <div class="flex-fill d-flex align-items-center">
                <router-link to="/" class="text-decoration-none d-flex align-items-center">
                    <img :src="brandLogo" alt="Brand Logo" style="height: 50px; object-fit: contain;">
                    <div class="d-flex flex-column align-items-end ms-2" style="color: var(--bg-primary)">
                        <span v-if="brandName" class="text-uppercase fs-4 fw-bold lh-1">{{ brandName }}</span>
                        <!-- <small class="smaller">{{ brandTagLine }}</small> -->
                    </div>
                </router-link>
            </div>
        </div>
        <div class="">
            <router-link v-if="showOnDemo && !showOnFree" to="/free-trial" class="text-decoration-none btn btn-danger rounded p-2 border px-2 ms-2">
                <span class="text-capitalize">Try free</span>
            </router-link>
            <router-link v-if="showOnFree && !showOnDemo" to="/demo" class="text-decoration-none btn btn-danger rounded p-2 border px-2 ms-2">
                <span class="text-capitalize">Demo</span>
            </router-link>
        </div>
    </div>
</template>

<script>
export default {
    name: 'NavBar',
    data() {
        return {
            brandName: 'saleswik',
            brandTagLine: "let's get wicked",
            brandLogo: '/img/logo.svg',
            brandColorOne: '#125252',
        }
    },
    computed: {
        showOnFree() {
            const hiddenPages = [ 'free-trial']
            return hiddenPages.includes(this.$route.name)
        },
        showOnDemo() {
            const hiddenPages = [ 'demo-page']
            return hiddenPages.includes(this.$route.name)
        },
    },
    methods: {
        closeOffcanvas() {
            const offcanvasElement = document.getElementById('offcanvasExample');
            const bsOffcanvas = window.bootstrap.Offcanvas.getInstance(offcanvasElement);
            if (bsOffcanvas) {
                bsOffcanvas.hide();
            }
        }
    },
    mounted() {
        this.$router.afterEach(() => {
            this.closeOffcanvas();
        });
    }
};
</script>
