<template>
<div class="card ov-none">
    <div class="card-body p-0">

        <div class="row">
            <div class="col">

                <div class="cont_carrusel">
                    <div :id="'carrusel_'+ data.id" class="carousel slide" data-ride="carousel">
                        <div class="carousel-inner">
                            <div class="carousel-item" :class="{'active': index == 0}" v-for="(item, index) in data.imgs" :key="index">
                                <img class="img-fluid" alt="Imagen Portfolio" :src="'/img/portfolio/'+item" />
                            </div>
                        </div>
                    </div>
                </div>

                <div class="cont_description">
                    <div class="row h-100 justify-content-center align-items-center">
                        <div class="col-auto text-center">
                            <span class="titulo_sec_port">{{ data.titulo }}</span><br>
                        </div>
                    </div>
                </div>

                <div class="cont_description_over">
                    <div class="row h-100 justify-content-center align-items-center">
                        <div class="col-auto text-center">
                            <a :href="data.url" target="_blank">Visitar</a>
                        </div>
                    </div>
                </div>
                
            </div>
        </div>

    </div>
</div>
</template>

<script setup>
import { onMounted } from 'vue';

const props = defineProps([ "data" ])

onMounted(() => {
    const random_int = Math.floor(Math.random() * 3000) + 2000

    $(`#carrusel_${props.data.id}`).carousel({
        interval: random_int,
        pause: "false",
        direction: "right"
    });
})
</script>

<style scoped>

.cont_carrusel{
    position: relative;
}

.cont_description, .cont_description_over {
    position: absolute;
    bottom: 0;
    width: 100%;
    background: rgba(0, 0, 0, 0.9);
    color: #fff;
    padding: 0.5rem 1rem;
    transition-duration: 1s;
    margin-left: -15px;
}

.cont_description_over{
    height: 100%;
    opacity: 0;
}

.cont_description_over:hover{
    opacity: 1;
}

.cont_description_over a, .titulo_sec_port {
    color: #fff;
    font-weight: bold;
    font-size: 1.5rem;
}

.cont_description_over a{
    color: #00ec3b;
}

</style>