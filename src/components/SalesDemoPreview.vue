<template>
    <div class="container">
        <h1 class="text-center mb-4 text-capitalize">sales funnel</h1>
        <div class="row m-0 gy-2 mb-4">
            <div class="col-12 col-md-6 align-self-center">
                <img src="/img/mobilecontent.svg" style="max-width: 80%; width: 250px;" alt="">
            </div>
            <div class="col-12 col-md-6 g-2 mt-5 mt-md-0">
                <div v-for="(demo, index) in demos" :key="index" class="col">
                    <div class="border-bottom p-1 py-2 m-2">
                        <router-link :to="demo.link"
                            class="d-flex align-items-center justify-content-between text-decoration-none text-dark">
                            <h5 class="text-center mb-0">{{ demo.head }}</h5>

                            <button class="btn btn-danger"> <i class="bi bi-play"></i> Video</button>
                            <button class="btn btn-danger"> <i class="bi bi-eye"></i> Preview</button>
                        </router-link>
                    </div>
                </div>
            </div>
        </div>
        <div>
            <ul class="nav nav-pills justify-content-start align-items-center" id="pills-tab" role="tablist">
                <div class="d-flex overflow-x-scroll gap-3 my-3 p-2 px-3 rounded" id="scroll">
                    <li class="nav-item border rounded-pill" role="presentation" v-for="(template, index) in templates"
                        :key="index">
                        <button class="nav-link" :class="{ 'active': index === activeTabIndex }" :id="'tab-' + index"
                            data-bs-toggle="pill" :data-bs-target="'#content-' + index" type="button" role="tab"
                            :aria-controls="'content-' + index" :aria-selected="index === activeTabIndex"
                            @click="activeTabIndex = index">{{ template.name}}</button>
                    </li>
                </div>
            </ul>
            <div class="tab-content" id="pills-tabContent">
                <div class="d-flex align-items-center shadow p-2 mb-3">
                    <input type="search" placeholder="Search for questions?" v-model="searchTerm"
                        class="form-control border-0" ref="searchInput" @keyup.enter="search">
                    <div>
                        <i class="bi bi-search" @click="search"></i>
                    </div>
                </div>
                <div class="tab-pane fade" :class="{ 'show active': index === activeTabIndex }"
                    v-for="(template, index) in templates" :key="index" :id="'content-' + index" role="tabpanel"
                    :aria-labelledby="'tab-' + index" tabindex="0">
                    <div class="row row-cols-1 row-cols-md-2 row-cols-lg-3 row-cols-xl-4 g-2">
                        <div class="col" v-for="(demo, demoIndex) in template.tempDemos" :key="demoIndex">
                            <div class="card">
                                <div class="card-body">
                                    <h3>{{ demo.title }}</h3>
                                    <i class="bi fs-1" :class="demo.icon"></i>
                                </div>
                            </div>
                        </div>
                    </div>
                    <!-- <div class="row">
                        <div class="col-12" v-for="(faq, index) in filteredFaqs(price.plans)" :key="index">
                            <div class="accordion accordion-flush" id="accordionFlushExample">
                                <div class="accordion-item my-2 border-0">
                                    <h2 class="accordion-header border">
                                        <button class="accordion-button collapsed bg-light border-start border-4"
                                            type="button" data-bs-toggle="collapse"
                                            :data-bs-target="'#flush-collapseOne' + index" aria-expanded="false"
                                            :aria-controls="'flush-collapseOne' + index"
                                            style="border-color: var(--bg-primary) !important;">
                                            <span class="me-2">Q{{ index + 1 }}.</span> {{ faq.question }}
                                        </button>
                                    </h2>
                                    <div :id="'flush-collapseOne' + index" class="accordion-collapse collapse border-0"
                                        data-bs-parent="#accordionFlushExample">
                                        <div class="accordion-body text-start">{{ faq.answer }}</div>
                                    </div>
                                </div>
                            </div>
                        </div>
                        <div v-if="filteredFaqs(price.plans).length === 0" class="col-12">
                            <p class="text-center">No results found.</p>
                        </div>
                    </div> -->
                </div>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    name: 'SalesDemoPreview',
    data() {
        return {
            demos: [
                {
                    id: 1,
                    head: 'Demo 1',
                    link: '/sales-demo-one'
                },
                {
                    id: 2,
                    head: 'Demo 2',
                    link: '/sales-demo-two'
                },
                {
                    id: 3,
                    head: 'Demo 3',
                    link: '/'
                },
            ],
            templates: [
                {
                    id: 1,
                    name: "Template 1",
                    tempDemos: [
                        {
                            title:"test 1",
                            link:"/sales-demo-one",
                            icon:"bi-check2",
                        },
                        {
                            title:"test 2",
                            link:"/sales-demo-one",
                            icon:"bi-check2",
                        },
                        {
                            title:"test 3",
                            link:"/sales-demo-one",
                            icon:"bi-check2",
                        },
                        {
                            title:"test 4",
                            link:"/sales-demo-one",
                            icon:"bi-check2",
                        },
                    ]
                },
                {
                    id: 2,
                    name: "Template 2",
                    tempDemos: [
                        {
                            title:"test 1",
                            link:"/sales-demo-one",
                            icon:"bi-check2",
                        },
                        {
                            title:"test 2",
                            link:"/sales-demo-one",
                            icon:"bi-check2",
                        },
                        {
                            title:"test 3",
                            link:"/sales-demo-one",
                            icon:"bi-check2",
                        },
                        {
                            title:"test 4",
                            link:"/sales-demo-one",
                            icon:"bi-check2",
                        },
                    ]
                },
                {
                    id: 3,
                    name: "Template 3",
                    tempDemos: [
                        {
                            title:"test 1",
                            link:"/sales-demo-one",
                            icon:"bi-check2",
                        },
                        {
                            title:"test 2",
                            link:"/sales-demo-one",
                            icon:"bi-check2",
                        },
                        {
                            title:"test 3",
                            link:"/sales-demo-one",
                            icon:"bi-check2",
                        },
                        {
                            title:"test 4",
                            link:"/sales-demo-one",
                            icon:"bi-check2",
                        },
                    ]
                },
                {
                    id: 4,
                    name: "Template 4",
                    tempDemos: [
                        {
                            title:"test 1",
                            link:"/sales-demo-one",
                            icon:"bi-check2",
                        },
                        {
                            title:"test 2",
                            link:"/sales-demo-one",
                            icon:"bi-check2",
                        },
                        {
                            title:"test 3",
                            link:"/sales-demo-one",
                            icon:"bi-check2",
                        },
                        {
                            title:"test 4",
                            link:"/sales-demo-one",
                            icon:"bi-check2",
                        },
                    ]
                },
                {
                    id: 5,
                    name: "Template 5",
                    tempDemos: [
                        {
                            title:"test 1",
                            link:"/sales-demo-one",
                            icon:"bi-check2",
                        },
                        {
                            title:"test 2",
                            link:"/sales-demo-one",
                            icon:"bi-check2",
                        },
                        {
                            title:"test 3",
                            link:"/sales-demo-one",
                            icon:"bi-check2",
                        },
                        {
                            title:"test 4",
                            link:"/sales-demo-one",
                            icon:"bi-check2",
                        },
                    ]
                },

            ],
            searchTerm: '',
            activeTabIndex: 0
        }
    },
    methods: {
        // filteredFaqs(plans) {
        //     if (!this.searchTerm) {
        //         return plans;
        //     }
        //     const term = this.searchTerm.toLowerCase();
        //     return plans.filter(faq =>
        //         faq.question.toLowerCase().includes(term) || faq.answer.toLowerCase().includes(term)
        //     );
        // },
    },
    mounted() {
        this.$refs.searchInput.focus();
    }
}
</script>