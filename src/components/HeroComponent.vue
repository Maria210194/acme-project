<template>
    <div class="container">
        <div class="box-info">
            <h2 class="black">Quanto costa custodire le tue cripto?</h2>
            <h2 class="white">Scoprilo con Acme Corp.</h2> 
            <div class="info_container">
                <p class="info_paragraph">
                    Quando il tuo patrimonio cripto inizia a crescere, custodirlo in modo sicuro è fondamentale per evitare di incorrere in truffe e rischi.
                </p>
                <p class="info_paragraph">
                    Prova il servizio di custodia affidabile e trasparente di Acme Corp: <span class="bold">calcola le tue commissioni mensili e scopri tutti i vantaggi.</span>
                </p>
            </div>
            <a class="red_button" href="#calculator">Calcola la tua fee ></a>
        </div>
        <div class="bitcoin">
            <img src="@/assets/img/Bitcoin.svg" alt="">
        </div>
        
    </div>
</template>

<script>
export default {
    name: 'HeroComponent'
}
</script>

<style lang="scss" scoped>
    @import '../styles/vars.scss';
    
    .container {
        width: 100%;
        overflow-x: none;
        padding: 5vh 0;
        display: flex;
        background-color: #A48C8C;

        .box-info *{
            padding: 1.5vh 0;
        }

        .box-info {
            width: 65%;
            margin: 1.1rem 0 0 8vw;

            .black {
                font-weight: bolder;
                font-size: 30px;
                padding-bottom: 0;
            }
            
            .white{
                font-weight: bolder;
                font-size: 30px;

                padding-top: 0;
                color: white;
            }

            .info_paragraph {
                width: 90%;
                margin: 0;
                padding: 0.4rem 0;

                .bold {
                    font-weight: bolder;
                }
            }

            .red_button {
                display: inline-block;
                width: fit-content;
                margin-bottom: 0.5rem;
                border: none;
                color: white;
                text-decoration: none;
                background-color: $color_red;
                text-transform: uppercase;
                font-size: 12px;
                padding: 0.4rem;
            }

            .info_container {
                margin-bottom: 1rem;
            }
        }

        .bitcoin {
            width: 34%;
            padding: 1.5rem 0 1.1rem 0;

            img {
                width: 75%;
                padding: 1rem;
            }
        }

    }

    @media screen and (max-width: 850px) {
        .container {
            flex-direction: column;
            .bitcoin {
                width: 60%;
                position: relative;

                img {
                    width: 100%;
                    padding: 1rem;
                    position: absolute;
                    bottom: -100%;
                    filter: opacity(0.2);
                }
            }
        }
    }

    @media screen and (max-width: 450px) {
        .container {
            .box-info {
                .white,
                .black {
                    font-size: 20px;
                }
                .info_paragraph {
                    font-size: 11px;
                }
            }
        }
    }

</style>