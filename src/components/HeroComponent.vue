<template>
    <div class="container">
        <div class="box-info">
            <h2 class="black">Quanto costa custodire le tue cripto?</h2>
            <h2 class="white">Scoprilo con Acme Corp.</h2> 
            <p class="info_paragraph">
                Quando il tuo patrimonio cripto inizia a crescere, custodirlo in modo sicuro è fondamentale per evitare di incorrere in truffe e rischi.
                Prova il servizio di custodia affidabile e trasparente di Acme Corp: calcola le tue commissioni mensili e scopri tutti i vantaggi.
            </p>
            <button class="red_button">Calcola la tua fee ></button>
        </div>
        <div>
            <img class="bitcoin" src="@/assets/Bitcoin.svg" alt="">
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
        width: 100vw;
        padding: 5vh 0;
        display: flex;
        background-color: #A48C8C;

        .box-info *{
            padding: 1.5vh 0;
        }

        .box-info {
            width: 40%;
            margin-left: 15vw;
            

            .white{
                padding-top: 0;
                color: white;
            }

            .info_paragraph {
                width: 90%;
                margin: 0;
                padding-bottom: 2rem;
            }


            .red_button {
                border: none;
                color: white;
                background-color: $color_red;
                text-transform: uppercase;
                font-size: 12px;
                padding: 0.4rem;
            }
        }

        .bitcoin {
            width: 60%;

            img {
                width: 100%;
            }
        }

    }

</style>