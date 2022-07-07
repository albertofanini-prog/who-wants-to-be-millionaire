<template>
    <div class="container">
        <div class="info">
            <div class="current">
                Quiz: {{domandaIndex + 1}}/10
            </div>
            <div class="prize">
                $ 0
            </div>
            <div class="odds">
                Punti: {{score}} /10
            </div>
        </div>
        <div class="time">
            30
        </div>
        <form>
            <div class="quizBox" v-if="domandaIndex < domande.length">
                <label class="ask">{{ domanda.domanda }}</label>
                <div class="answerBox" v-for="domanda of domanda.scelta" :key="domanda">
                    <input type="radio" name="choice" v-model="risposta" :value="domanda"/>
                    {{ domanda }}
                </div>
                <button :style="background" type="button" @click="submit">controlla</button>
            </div>
            <div v-else>
                <button :style="background" type="button" @click="restart">rinizia</button>
            </div>
        </form>
    </div>
</template>

<script>
    const domande = [
    {
        domanda: "Chi ha scritto l'album \"Sticky fingers\"?",
        scelta: [
            "The Beatles",
            "The Doors",
            "Rolling Stones",
            "The Beach Boys"
        ],
        rispostaGiusta: "Rolling Stones",
    },
    {
        domanda: "Chi ha vinto più mondiali di calcio?",
        scelta: [
            "Italia",
            "Brasile",
            "Australia",
            "Germania"
        ],
        rispostaGiusta: "Brasile",
    },
    {
        domanda: "Quale film venne realizzato da Walt Disney 1937?",
        scelta: [
            "Biancaneve",
            "Il libro della giungla",
            "Cenerentola",
            "La bella e la bestia"
        ],
        rispostaGiusta: "Biancaneve",
    },
    {
        domanda: "Vi si trova la Mole Antonelliana",
        scelta: [
            "Roma",
            "Udine",
            "Torino",
            "Reggio Calabria"
        ],
        rispostaGiusta: "Torino",
    },
    {
        domanda: "Il ladro protagonista del fumetto italiano",
        scelta: [
            "Lupin",
            "La Banda Bassotti",
            "Diabolik",
            "Catwoman"
        ],
        rispostaGiusta: "Diabolik",
    },
    {
        domanda: "Ce n'è una in Italia e una in Egitto",
        scelta: [
            "Forlì",
            "Barletta",
            "Pordenone",
            "Alessandria"
        ],
        rispostaGiusta: "Alessandria",
    },
    {
        domanda: "La città del Saracino",
        scelta: [
            "Pistoia",
            "Arezzo",
            "Siena",
            "Lucca"
        ],
        rispostaGiusta: "Arezzo",
    },
    {
        domanda: "I venti che soffiano costantemente verso l'equatore",
        scelta: [
            "Ponente",
            "Maestrale",
            "Aliseo",
            "Libeccio"
        ],
        rispostaGiusta: "Aliseo",
    },
    {
        domanda: "Indovinello: Più è caldo, più è fresco. Cosa è?",
        scelta: [
            "Motore di un veicolo",
            "The",
            "Uovo",
            "Frigorifero"
        ],
        rispostaGiusta: "Uovo",
    },
    {
        domanda: "Secondo la mitologia romana, Saturno di cosa era il Dio?",
        scelta: [
            "Vento",
            "Agricoltura",
            "Falegnameria",
            "Fuoco"
        ],
        rispostaGiusta: "Agricoltura",
    },
    ];
    export default {
        name: "App",
        data() {
            return {
                domande,
                score: 0,
                domandaIndex: 0,
                domanda: domande[0],
                risposta: "",
                background:{
                    backgroundImage: "url(https://image.api.playstation.com/vulcan/img/rnd/202111/3009/Icu3kOAJ00NPRiMtiBKVsV0z.png)",
                }
            };
        },
        methods: {
            submit() {
            const { risposta, domanda, domande, domandaIndex } = this;
            if (risposta === domanda.rispostaGiusta) {
                this.score++;
            }
            if (domandaIndex < domande.length) {
                this.domandaIndex++;
                this.domanda = { ...domande[this.domandaIndex] };
            }
            },
            restart() {
                this.domanda = domande[0];
                this.risposta = "";
                this.domandaIndex = 0;
                this.score = 0;
            },
        },
    };
</script>

<style lang="scss">
    .container{
        width: 80%;
        height: 60%;
        // border: 3px solid red;
        border-radius: 25px;
        background-color: #FFFFFF;
        box-shadow: 5px 5px 30px 5px blue, -5px -5px 30px 5px red;
        display: flex;
        flex-direction: column;
        padding: 5%;
        align-items: center;
        justify-content: space-between;
        gap: 30px;
        .info{
            // border: 3px solid red;
            width: 100%;
            display: flex;
            align-items: center;
            justify-content: space-between;
            font-size: 14px;
            font-weight: 600;
            .current{
                width: 35%;
                text-align: left;
            }
            .prize{
                width: 30%;
            }
            .odds{
                width: 35%;
                text-align: right;
            }
        }
        .time{
            border: 2px solid blue;
            border-radius: 99px;
            padding: 5px;
        }
        form{
            width: 100%;
            height: 100%;
            position: relative;
            .quizBox{
                display: flex;
                flex-direction: column;
                align-items: center;
                gap: 25px;
                .answerBox{
                    text-align: center;
                    width: 100%;
                    display: flex;
                    align-items: baseline;
                    justify-content: flex-start;
                    gap: 10px;
                    text-align: left;
                }
            }
            .ask{
                line-height: 26px;
                font-weight: 600;
                font-size: 20px;
            }
            button{
                width: 65%;
                padding: 5px 10px;
                border-radius: 8px;
                border: none;
                background-color: none;
                text-transform: uppercase;
                color: white;
            }
        }
    }
</style>