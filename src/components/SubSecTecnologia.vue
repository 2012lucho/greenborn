<template>
    <div class="row justify-content-center alig-items-center">
        <div class="col-12 col-sm-10 col-md-6 col-lg-4 col-xl-3 mt-4 mb-5 text-center">
        
            <a href="{{data.url}}" target="_blank">
                <img alt="Logo Tecnología" :src="data.img_src" class="img-tecno"/>
            </a>
        
        </div>

        <div class="col-12 col-lg-8 col-xl-9" >
            <div class="row mt-4 mb-4">
                <div class="col">
                    <span v-html="data.description"></span>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>

const props = defineProps([ "data" ])

</script>

<style scoped>
.img-tecno{
  width: 100%;
  height: auto;
}

@media (max-width: 500px) {
    .img-tecno{
        width: 100%;
        max-width: 10rem;
        height: auto;
    }
}
</style>