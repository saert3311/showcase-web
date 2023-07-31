<template>
    <Carousel v-bind="settings" :breakpoints="breakpoints" :wrap-around="true">
        <Slide v-for="(item, index) in portfolios" :key="index">
            <div class="carousel__item">
                <PortfolioCard :data="item" />
            </div>
        </Slide>

        <template #addons>
            <Navigation />
            <Pagination />
        </template>
    </Carousel>
</template>
  
<script>
import { defineComponent } from 'vue'
import { Carousel, Navigation, Slide, Pagination } from 'vue3-carousel'
import PortfolioCard from './PortfolioCard.vue'
import 'vue3-carousel/dist/carousel.css'

export default defineComponent({
    name: 'ProjectSlider',
    components: {
        Carousel,
        Slide,
        Navigation,
        PortfolioCard,
        Pagination
    },
    data() {
        return {
            portfolios: [
                {
                    title: 'Miami Scaffold Rental',
                    imgSrc: '/img/portfolio/miamiscaffoldrental.webp',
                    link: 'https://miamiscaffoldrental.com',
                    description: 'Web de arriendo de andamios, formulario de contacto, galeria de trabajos, opiniones de google'
                },
                {
                    title: 'Desarmaduria San Pedro',
                    imgSrc: '/img/portfolio/desarmaduriasanpedro.webp',
                    link: 'https://desarmaduriasanpedro.cl',
                    description: 'Web de compra de repuestos de vehiculos explorador de productos, formulario y boton de contacto, acceso directo whatsapp'
                },
                {
                    title: 'Expoandes',
                    imgSrc: '/img/portfolio/expoandes.webp',
                    link: 'https://expoandes.cl',
                    description: 'Landing page de ventas de insumos forestales, galeria dinamica, multilenguage, acceso directo whatsapp'
                },
                {
                    title: 'Procenter',
                    imgSrc: '/img/portfolio/procenterr.webp',
                    link: 'https://procenter.cl/',
                    description: 'Servicios de pintura y desabollado a vehiculos, formlario de contacto, localizacion en mapas.'
                },
                {
                    title: 'Tahpas 529',
                    imgSrc: '/img/portfolio/tahpas529.webp',
                    link: 'https://procenter.cl/',
                    description: 'Restaurante de tahpas, fotos de instagram, enlace a reservas, menu online'
                }
            ],
            settings: {
                itemsToShow: 1,
                snapAlign: 'center',
            },
            breakpoints: {
                // 700px and up
                700: {
                    itemsToShow: 2.5,
                    snapAlign: 'center',
                },
            },
        }
    }
})
</script>
<style>
.carousel__item {
    min-height: 200px;
    width: 100%;
    border-radius: 8px;
    display: flex;
    justify-content: center;
    align-items: center;
}

.carousel__slide {
    padding: 10px;
}

.carousel__prev,
.carousel__next {
    box-sizing: content-box;
    border: 5px solid white;
}
</style>