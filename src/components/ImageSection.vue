<template>
    <div class="container-fluid" style="background-color: var(--bg-primary);">
        <div class="row p-3">
            <div class="col-12 text-center">
                <img :src="banner" alt="Cover Image" style="width:50%;">
            </div>
        </div>
    </div>
</template>
<script>
export default {
    name: 'ImageSection', 
    props:{
        banner: {
            type: String, 
        },
        brandColorOne: {
            type: String, 
        },
        brandTextColor: {
            type: String, 
        },
        title: {
            type: String, 
        },
        description: {
            type: String, 
        }
    }
   
}
</script> 