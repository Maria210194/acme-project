<template>
    <div class="container">
        <div class="resize">
            <h3 class="main_title">Calcola la tua fee </h3>
            <div class="step_box">
                <div v-for="(button, index) in buttons" :key="index" class="card" >
                    <div class="fake_btn">
                        <img class="under" :src="require(`@/assets/img/${button.under}`)" alt="ellipse">
                        <img class="over" :src="require(`@/assets/img/${button.over}`)" alt="ellipse">
                        <img class="number" :src="require(`@/assets/img/${button.number}`)" alt="steps">
                    </div>
                    <div class="description">
                        {{button.description}}
                    </div>
                </div>
            </div> 
            <div class="box_calculator">
                <div class="calculator" v-if="!wrongImport && !tableActive">
                    <h4 class="calc_title">Inserisci gli asset che vuoi custodire</h4>
                    <input type="number" placeholder="Asset" id="user_input" v-model="asset">
                    <button @click="calcFee" @keyup.enter="callFee" class="red_btn">Calcola</button>
                    <div v-if="fee">
                        <div class="result_info">
                            <div class="fee_info">
                                <h3 class="title_fee">La tua fee:</h3>
                                <p class="result after_result">{{ parseFloat(fee) }}&euro;</p>
                                <span @click="toggleTable" class="dettagli">
                                Dettagli del calcolo
                                <i class="fa-solid fa-circle-chevron-down"></i>
                                </span>
                                <p class="prova_acme">Prova il servizio di custodia Acme Corp: non potrai più farne a meno.</p>
                                <div class="btns">
                                    <button class="transp_btn">Parla con noi</button>
                                    <button class="red_btn">Apri un conto</button>
                                </div>
                            </div>
                        </div>
                    </div>
                    <div v-else>
                        <p class="result">--,-- <span> €</span></p>
                        <span class="details" @click="toggleTable" >Dettagli del calcolo</span>
                    </div>
                </div>
            </div>
            <div v-if="tableActive" class="table_show">
                <img @click="toggleTable" id="info-table" src="@/assets/img/table.png" alt="info-table">
            </div>
            <div v-if="wrongImport" class="import_error">
                <div class="error_box">
                    <div class="images_error">
                        <img class="dark_box" src="@/assets/img/661.png" alt="close">
                        <img class="white_box" src="@/assets/img/672.png" alt="close">
                        <img class="circle" @click="closeModal" src="@/assets/img/x-circle.png" alt="close">
                        <h3 class="text_error">
                        Ci dispiace, al momento il nostro servizio è disponibile solo a partire da €15.000
                        </h3>
                    </div>
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
    data() {
        return {
            // Data for fee calculator
            asset: null,
            fee: null,

            // Boolean for modal
            wrongImport: false,
            tableActive: false,
        }
    },
    methods: {
        calcFee() {
            if (this.asset != "" && this.asset < 15000) {
                this.wrongImport = true;
            }
            else if (this.asset >= 15000 && this.asset < 500000) {
                let calculation = (this.asset * 0.7 / 100)
                this.fee = Math.floor(calculation / 12) + " €"
                // console.log('MINORE DI 50K, il premio annuale è: ', calculation)
            }
            else if (this.asset >= 500000 && this.asset < 1000000) {
                let calculation = ((this.asset - 500000) * 0.006) + (500000 * 0.007)
                this.fee = Math.floor(calculation / 12) + " €"
                // console.log('MINORE DI 1ML, il premio annuale è: ', calculation)
            }
            else if (this.asset >= 1000000 && this.asset < 5000000) {
                let calculation = ((this.asset - 1000000) * 0.005) + (500000 * 0.006) + (500000 * 0.007)
                this.fee = Math.floor(calculation / 12) + " €"
                // console.log('MINORE DI 5ML, il premio annuale è: ', calculation)
            }
            else if (this.asset >= 5000000 && this.asset < 10000000) {
                let calculation = ((this.asset - 5000000) * 0.004) + (4000000 * 0.005) + (500000 * 0.006) + (500000 * 0.007)
                this.fee = Math.floor(calculation / 12) + " €"
                // console.log('MINORE DI 10ML, il premio annuale è: ',calculation)
            }
            else {
                let calculation = ((this.asset - 10000000) * 0.003) + (5000000 * 0.004) + (4000000 * 0.005) + (500000 * 0.006) + (500000 * 0.007)
                this.fee = Math.floor(calculation / 12) + " €"
                // console.log('MAGGIORE DI 10ML, il premio annuale è: ', calculation)
            }
        },
        closeModal(){
        this.wrongImport = false;
        },
        toggleTable(){
            this.tableActive = !this.tableActive;
        },
    }
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

                        // .under {

                        // }

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
                    row-gap: 1rem;
                    padding: 1rem 0;
                    background-color: #584949;
                    border-radius: 20px;

                    .calc_title {
                        text-transform: uppercase;
                        font-size: 13px;
                        color: white;
                        font-weight: 200;
                        padding-top: 1rem;
                    }

                    .result_info {
                        display: flex;
                        .fee_info {
                            display: flex;
                            flex-direction: column;
                            width: 60%;
                            text-align: center;
                            padding-top: 3rem;

                            .title_fee {
                                color: white;
                                font-weight: 300;
                            }

                            .btns {
                                margin: 0.2rem 0 4rem 0;
                                .transp_btn {
                                    text-transform: uppercase;
                                    height: 30px;
                                    padding: 0 1.5rem;
                                    margin: 0 0.5rem;
                                    background: transparent;
                                    border: 1px solid white;
                                    color: white;
                                } 

                                .red_btn{
                                    height: 30px;
                                    width: fit-content;
                                    margin: 0 0.5rem;
                                    font-size: 12px;
                                }
                            }

                            .dettagli {
                                color: white;
                                margin-bottom: 2rem;
                                font-size: 12px;
                                text-decoration: underline;
                            }

                            .prova_acme {
                                color: white;
                                margin: 1rem 0 2.5rem 0;
                                font-size: 20px;
                                font-weight: 200;
                            }
                        }
                    }

                    #user_input {
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
                        margin: 2rem 0;
                    }

                    .after_result {
                        font-weight: 700;
                    }
                    
                    .details {
                        display: block;
                        padding-left: 0.5rem;
                        margin-bottom: 1.1rem;
                        color: white;
                        text-decoration: underline;
                    }

                }
            }
        }
        .table_show {
            pointer-events: auto;
            opacity: 1;
            width: 80%;
        }
        #info-table{
            max-width: 100% !important;
        }

        .import_error {
            width: 80%;
            .images_error {
                display: block;
                width: 50%;
                position: relative;
    
                .dark_box, 
                .white_box {
                    width: 100%;
                    position: absolute;
                }
                
                .white_box {
                    top: -7px;
                }
    
                .circle {
                    width: 10%;
                    position: absolute;
                    top: 0;
                    right: 5px;
                }
    
                .text_error {
                    position: relative;
                    top: 50%;
                    left: 50%;
                    transform: translate(-60%, 80%);
                    width: 80%;
                    font-weight: 400;
                    font-size:27px;
                }
            }

        }
    }

</style>