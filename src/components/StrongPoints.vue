<template>
  <div class="container">
    <h3 class="main_title">Cosa rende sicura e affidabile la custodia di Acme Corp:</h3>
    <div class="box_points">
        <div v-for="(element, index) in links"
        :key="index"
        class="card"
        >  
            <img class="img_points" :src="require(`@/assets/img/${element.url}`)" :alt="element.title">
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
        width: 100%;
        overflow-x: none;
        margin-inline: auto;
        padding: 2rem 0;

        .main_title {
            text-align: center;
            padding: 3rem 0;
            font-size: 23px;
            font-weight: 700;
        }

        .box_points{
            display: flex;
            align-items: baseline;
            flex-wrap: wrap;
            justify-content: center;
            padding: 1rem 4rem;

            .card:last-child img {
                width: 55px;
            }

            .card {
                width: 200px;
                margin-inline: auto;
                text-align: center;
                padding: 0.7rem;

                .img_points {
                    width: 70px;
                    padding-bottom: 10px;
                }

                .element_title {
                    padding: 0.7rem 0;
                    font-weight: bolder;
                    font-size: 14px;
                    font-weight: 600;
                }

                .element_parag {
                    width: 90%;
                    margin-inline: auto;
                    font-size: 12px;
                }
            }
        }
        table {
            width: 60%;
            margin-inline: auto;

            .big_details {
                font-size: 18px;
            }

            .small_details {
              font-size: 10px;
            }

            th,
            td {
                border: 1px solid black;
                padding: 1rem;
                width: 5%;
                line-height: 1;
                font-size: 10px;
            }
        }
    }

    @media screen and (max-width: 450px) {
        .container {
            .main_title {
                font-size: 20px;
            }
        }

    }


</style>