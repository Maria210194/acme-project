<template>
    <main>
        <h2 class="main_title">Tanti servizi tutti inclusi nella custodia</h2>
        <section class="servicies">
            <!-- <div v-for="(element, index) in servicies"
            :key="index"
            class="card" 
            >
                <img class="image" :src="require(`@/assets/img/${element.img}`)" :alt="element.description">
                <span class="description">{{element.description}}</span>
            </div> -->
            <Swiper
            :navigation="true"
            :modules="modules"
            class="swiper">
                <div class="swiper-wrapper">
                    <SwiperSlide v-for="(element, index) in servicies" :key="index" class="swiper-slide">
                        <img :src="require(`@/assets/img/${element.img}`)" :alt="element.description">
                        <p class="description">{{element.description}}</p>
                    </SwiperSlide>
                </div>
            </Swiper>
        </section>
    </main>
</template>

<script>
import { Swiper, SwiperSlide } from "swiper/vue";
import { Navigation } from "swiper";
import "swiper/css";
import "swiper/css/navigation";

export default {
    name: 'ServiciesComponent',
    data() {
        return {
            modules: [Navigation],
        }
    },
    components: {
        Swiper, 
        SwiperSlide,
    },
    props: {
        servicies: Array
    },
}
</script>

<style lang="scss" scoped>
    main {
        width: 100%;
        padding: 2rem 0;
        overflow-x: none;
        margin: 2rem 0 0 0;
        
        .main_title{
            padding: 40px 0;
            text-align: center;
            font-weight: 600;      
            margin-bottom: 4%;      
        }

        .servicies{
            width: 80%;
            margin: 0 auto;
            display: flex;
            align-items: baseline;
            flex-wrap: wrap;
            justify-content: center;
        
            // .card{
            //     width: 250px;
            //     margin: 0 5px;
            //     padding: 30px;
            //     display: flex;
            //     flex-direction: column;
            //     align-items: center;
            //     justify-content: center;

            //     .image{
            //         width: 110px;
            //         padding-bottom: 10px;
            //     }
            
            //     .description {
            //         font-size: 0.8rem;
            //         font-weight: bold;
            //     }
            // }
        }
    }

    .swiper {
        width: 80%;
        height: 100%;
        margin-bottom: 3rem;

        .swiper-slide {

            text-align: center;
            font-size: 18px;
            background: #fff;
    
            /* Center slide text vertically */
            display: -webkit-box;
            display: -ms-flexbox;
            display: -webkit-flex;
            display: flex;
            -webkit-box-pack: center;
            -ms-flex-pack: center;
            -webkit-justify-content: center;
            justify-content: center;
            -webkit-box-align: center;
            -ms-flex-align: center;
            -webkit-align-items: center;
            align-items: center;

            img {
                display: block;
                width: 30%;
                height: 50%;
                object-fit: cover;
                margin: 0 0 0 10%;
            }

            p {
                width: 40%;
                margin: 0 0.5rem 0 1rem;
            }
        }
    }

    @media screen and (max-width: 670px) {
        .swiper {
            .swiper-slide {
                font-size: 12px;
                flex-direction: column;
                align-items: center;
                row-gap: 1rem;

                img {
                    padding: 1.5rem 0 0 0;
                    margin: 0;
                }

                p {
                    width: 60%;
                    margin: 0;
                }
            }
        }

    }



</style>