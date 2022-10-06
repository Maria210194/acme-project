<template>
    <div class="container">
        <div class="resize">
            <h3 class="main_title">Calcola la tua fee </h3>
            <div class="step_box">
                <div class="card">
                    <div class="fake_btn">
                        <img class="under" src="../assets/img/133.png" alt="ellipse">
                        <img class="over" src="../assets/img/132.png" alt="ellipse">
                        <img class="number" src="../assets/img/1.png" alt="stepOne">
                    </div>
                    <div class="description">
                        Inserisci l’ammontare del tuo patrimonio in criptovalute
                    </div>
                </div>
                <div class="card">
                    <div class="fake_btn">
                        <img class="under" src="../assets/img/134.png" alt="ellipse">
                        <img class="over" src="../assets/img/135.png" alt="ellipse">
                        <img class="number" src="../assets/img/2.png" alt="stepTwo">
                    </div>
                    <div class="description">
                        Scopri la tua fee mensile
                    </div>
                </div>
                <div class="card">
                    <div class="fake_btn">
                        <img class="under" id="one" src="../assets/img/136.png" alt="ellipse">
                        <img class="over" src="../assets/img/137.png" alt="ellipse">
                        <img class="number" src="../assets/img/3.png" alt="stepThree">
                    </div>
                    <div class="description">
                        Apri il conto e godi di tutti i vantaggi
                    </div>
                </div>
            </div>
            <div class="box_calculator">
                <div class="calculator">
                    <h4 class="calc_title">Inserisci gli asset che vuoi custodire</h4>
                    <input class="user_input" type="text" name="asset" placeholder="Asset" id="">
                    <button class="red_btn">Calcola</button>
                    <p class="result">--,--€</p>
                    <a class="details" href="">Dettagli del calcolo</a>
                </div>
            </div>
        </div>
       
    </div>
</template>

<script>
export default {
    name: 'CalculatorComponent',
    props: {
        buttons: Array
    },
}
</script>

<style lang="scss" scoped>
    .container {
        width: 100%;
        overflow-x: none;
        background-color: #E4DADA;

        .resize {
            width: 90%;
            margin-inline: auto;
            display: flex;
            flex-direction: column;

            .main_title {
                text-align: center;
                padding: 2rem 0 0 0;
                margin: 2rem 0;
                font-size: 28px;
                font-weight: 600;
            }

            .step_box {
                display: flex;
                // width: 80%;
                margin-inline: auto;
                padding: 3rem 0;
    
                .card {
                    display: flex;
                    width:32%;
                    align-items: center;

                    .fake_btn {
                        position: relative;

                        .under {

                        }

                        .over {
                            position: absolute;
                            left: 10px;
                        }


                        .number {
                            position: absolute;
                            top: 50%;
                            left: 45%;
                            transform: translate(-50%, -60%);
                        }
                    }

                    .fake_btn:first-of-type {
                        padding: 0.6rem 1rem 0.6rem 1rem!important;
                    }

                    .description {
                        padding: 0 0.5rem 0 0;
                        width: 60%;
                        margin-inline: auto;
                        font-size: 0.9rem;
                        text-align: center;
                    }
                }
            }

            .box_calculator {
                width:100%;

                .calculator {
                    width: 50%;
                    margin-inline: auto;
                    margin: 3rem auto;
                    display: flex;
                    flex-direction: column;
                    align-items: center;
                    row-gap: 2rem;
                    padding: 1rem 0;
                    background-color: #584949;
                    border-radius: 20px;

                    .calc_title {
                        text-transform: uppercase;
                        color: white;
                        font-weight:100;
                        padding-top: 1rem;
                    }

                    .user_input {
                        width: 50%;
                        margin-inline: auto;
                        padding: 0.3rem 0;
                    }

                    .red_btn {
                        border: none;
                        color: white;
                        background-color: #D70F0F;
                        text-transform: uppercase;
                        font-size: 12px;
                        padding: 0.5rem 1rem;
                        border-radius: 2px;
                        width: 25%;
                    }

                    .result {
                        font-size: 60px;
                        color: white;
                    }
                    
                    .details {
                        padding-left: 0.5rem;
                        margin-bottom: 1rem;
                        color: white;
                    }
                }
            }
        }
    }

</style>