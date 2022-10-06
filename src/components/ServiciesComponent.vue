<template>
    <main>
        <h2 class="main_title">Tanti servizi tutti inclusi nella custodia</h2>
        <section class="servicies">
            <div v-for="(element, index) in servicies"
            :key="index"
            class="card" 
            >
                <img class="image" :src="element.img" :alt="element.description">
                <span class="description">{{element.description}}</span>
            </div>
        </section>
    </main>
</template>

<script>
export default {
    name: 'ServiciesComponent',
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
        
        .main_title{
            padding: 40px 0;
            text-align: center;
        }

        .servicies{
            width: 80%;
            margin: 0 auto;
            display: flex;
            align-items: center;
            flex-wrap: wrap;
            justify-content: center;
        
            .card{
                width: 250px;
                margin: 0 5px;
                padding: 30px;
                display: flex;
                flex-direction: column;
                align-items: center;
                justify-content: center;

                .image{
                    width: 110px;
                    padding-bottom: 10px;
                }
            
                .description {
                    font-size: 0.8rem;
                    font-weight: bold;
                }
            }
        }
    }



</style>