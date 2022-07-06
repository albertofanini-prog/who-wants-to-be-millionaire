<template>
    <div class="quizbox">
        <div class="info">
            <div class="current">
                4/10
            </div>
            <div class="prize">
                $150
            </div>
            <div class="odds">
                4,281
            </div>
        </div>
        <div class="timer">
            5
        </div>
        <div class="askbox">
            <div class="tipology">
                Technology
            </div>
            <div class="ask">
                What was the first product launched by Apple?
            </div>
        </div>
        <div class="answersbox">
            <ul>
                <li>
                    iPhone
                </li>
                <li>
                    iPad
                </li>
                <li>
                    Apple 1
                </li>
                <li>
                    iPod
                </li>
            </ul>
        </div>
        <div class="credits">
            Made by Fanini A. with VueJS
        </div>
    </div>
</template>

<script>
    export default{
        name: 'QuizBox',
    }
</script>

<style lang="scss">
    .quizbox{
        width: 80%;
        height: 70%;
        // border: 3px solid red;
        border-radius: 25px;
        background-color: #FFFFFF;
        box-shadow: 5px 5px 30px 5px blue, -5px -5px 30px 5px red;
        display: flex;
        flex-direction: column;
        padding: 5% 1%;
        align-items: center;
        gap: 30px;
        .info{
            // border: 3px solid green;
            width: 90%;
            // height: 8%;
            display: flex;
            align-items: center;
            justify-content: space-between;
            font-size: 14px;
            font-weight: 600;
        }
        .timer{
            border: 2px solid blue;
            border-radius: 999px;
            width: 40px;
            height: 40px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: 600;
            font-size: 22px;
        }
        .askbox{
            // border: 3px solid green;
            width: 90%;
            // height: 8%;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: space-between;
            gap: 10px;
            padding-bottom: 30px;
            .tipology{
                font-size: 12px;
                opacity: 0.7;
            }
            .ask{
                line-height: 26px;
                font-weight: 600;
                font-size: 18px;
            }
        }
        .answersbox{
            // border: 3px solid green;
            width: 90%;
            // height: 8%;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: space-between;
            gap: 10px;
            ul{
                list-style: none;
                display: flex;
                flex-direction: column;
                align-items: center;
                justify-content: space-between;
                width: 100%;
                gap: 20px;
                li{
                    // border: 1px solid black;
                    width: 100%;
                    height: calc(100% / 4);
                    border-radius: 15px;
                    box-shadow: 0 0 10px;
                }
            }
        }
        .credits{
            margin-top: 20px;
            // border: 3px solid green;
            width: 90%;
            font-size: 10px;
            line-height: 18px;
            letter-spacing: 0;
            text-align: right;
        }
    }
</style>