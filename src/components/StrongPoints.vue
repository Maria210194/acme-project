<template>
    <div class="container">
        <h3 class="main_title">Cosa rende sicura e affidabile la custodia di Acme Corp:</h3>
        <div class="box_points">
            <div v-for="(element, index) in links"
            :key="index"
            class="card"
            >  
                <img class="img_points" :src="element.url" alt="">
                <h4 class="element_title">{{element.title}}</h4>
                <p class="element_parag">{{element.paragraph}}</p>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'StrongPoints',
    props: {
        links: Array
    },
}
</script>

<style lang="scss" scoped>
    .container{
        width: 100vw;
        overflow-x: none;
        margin-inline: auto;
        padding: 2rem 0;

        .main_title {
            text-align: center;
            padding: 3rem 0;
            font-size: 21px;
            font-weight: bold;
        }

        .box_points{
            display: flex;
            align-items: baseline;
            padding: 1rem 4rem;

            .card:last-child img {
                width: 55px;
            }

            .card {
                width: 20vw;
                margin-inline: auto;
                text-align: center;
                padding: 0 0.7rem;

                .img_points {
                    width: 70px;
                    padding-bottom: 10px;
                }

                .element_title {
                    padding: 0.7rem 0;
                    font-weight: bolder;
                    font-size: 14px;
                }

                .element_parag {
                    width: 90%;
                    margin-inline: auto;
                    font-size: 12px;
                }
            }
        }
    }


</style>