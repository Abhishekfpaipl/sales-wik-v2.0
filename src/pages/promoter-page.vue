<template>
    <div class="container d-flex align-items-center w-100" style="padding-top: 70px;">
        <div class="d-flex justify-content-center flex-wrap row">
            <div v-for="(vote, index) in shops" :key="index" class="col-4 col-md-2 position-relative">
                <div class="d-flex justify-content-center text-dark mb-4">
                    <div class="bg-light border rounded-2 d-flex flex-column justify-content-center align-items-center pt-3 px-3 text-dark"
                        style="width: 120px;">
                        <img :src="vote.img" alt="" style="width: 60%;" />
                        <p class="fw-bold my-1 text-center">{{ vote.name }}</p>
                        <div class="d-flex">
                            <small>{{ vote.support }}+</small>
                            &nbsp;
                            <small>Promoters</small>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>

export default {
    data() {
        return {
            shops: [
                { id: 1, img: '/img/users/1.png', name: 'Travis', support: 200 },
                { id: 2, img: '/img/users/2.png', name: 'Kanye', support: 100 },
                { id: 3, img: '/img/users/3.png', name: 'Snoop', support: 200 },
                { id: 4, img: '/img/users/4.png', name: 'Weekend', support: 100 },
                { id: 5, img: '/img/users/5.png', name: 'Akon', support: 100 },
                { id: 6, img: '/img/users/1.png', name: 'Snoop', support: 200 },
                { id: 1, img: '/img/users/3.png', name: 'Travis', support: 200 },
                { id: 2, img: '/img/users/2.png', name: 'Kanye', support: 100 },
                { id: 3, img: '/img/users/4.png', name: 'Snoop', support: 200 },
                { id: 4, img: '/img/users/5.png', name: 'Weekend', support: 100 },
                { id: 5, img: '/img/users/1.png', name: 'Akon', support: 100 },
                { id: 6, img: '/img/users/2.png', name: 'Snoop', support: 200 },
            ],
        };
    }
};
</script>

<style lang="">
</style>
