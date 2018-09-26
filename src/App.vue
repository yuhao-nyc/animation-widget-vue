<template>
    <div class="mx-auto dm-widget-container">

        <div 
            v-if="pageStacked" 
            class="row pt-4 elastic-container-stacked" 
            :class="pageElastic ? 'elastic-left' : ' '"
        >
            <div class="col-6 widget-mg-top widget-heading">
                <h5>Sub-heading</h5>
                <h2>Lorem ipsum dolor consectetur tempor incididunt?</h2>
                <p class="mt-4">Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut</p>
            </div>

            <div class="col-4 ml-4 widget-mg-top">
                <div 
                    class="slides-open-btn" 
                    @click="showPageDetails"
                >
                    <img src="./assets/imgs/open-btn.svg">
                </div>

                <div class="slides-container">
                    <div v-on:mouseover="showPageDetails">
                        <img src="./assets/imgs/matthew-brodeur-62444.jpg">
                    </div>

                    <div>
                        <img src="./assets/imgs/samsommer-72299.jpg">
                    </div>

                    <div>
                        <img src="./assets/imgs/ravi-pinisetti-64168.jpg">
                    </div>

                    <div>
                        <img src="./assets/imgs/luca-bravo-112050.jpg">
                    </div>
                </div>
            </div>
        </div>
    
        <div 
            v-if="pageDetails" 
            :class="pageDetails ? 'elastic-right' : ' '" 
            class="elastic-container-detail"
        >
            <div class="slides-close-btn" @click="showStackedPage">
                <img src="./assets/imgs/close-btn.svg" >
            </div>

            <h5>Sub-heading</h5>
            <h3>Lorem ipsum dolor consectetur tempor incididunt?</h3>

            <div class="row mt-4">
                <div class="col-3">
                    <div class="slides-container-full">
                        <img src="./assets/imgs/matthew-brodeur-62444.jpg">
                    </div>
                </div>
                <div class="col-3">
                    <div class="slides-container-full">
                        <img src="./assets/imgs/samsommer-72299.jpg">
                    </div>
                </div>
                <div class="col-3">
                    <div class="slides-container-full">
                        <img src="./assets/imgs/ravi-pinisetti-64168.jpg">
                    </div>
                </div>
                <div class="col-3">
                    <div class="slides-container-full">
                        <img src="./assets/imgs/luca-bravo-112050.jpg">
                    </div>
                </div>
            </div>
        </div>

    </div>

</template>

<script>
export default {
    data() {
        return {
            pageStacked: true,
            pageDetails: false,
            pageElastic: false
        }

    },
    methods: {
        showPageDetails() {
            this.pageStacked = false
            this.pageDetails = true
        },
        showStackedPage() {
            this.pageStacked = true
            this.pageDetails = false
            this.pageElastic = true
        }
    }
}
</script>

<style>
    body {
        background-color: #152545
    }
    
    .dm-widget-container {
        width: 712px; 
        height: 423px; 
        position:relative; 
        margin-top: 8%; 
        background-color: #F9FAFC; 
        border: 1px solid #979797; 
        border-radius: 10px
    }
    
    .widget-heading h5,
    .elastic-container-detail h5 {
        font-size: 20px;
        background: linear-gradient(to right, #2C2C64, #4A90F5);
        -webkit-background-clip: text;
        -webkit-text-fill-color: transparent;
    }

    .widget-heading h2 {
        font-size: 34px;
        color: #041847;
    }

    .widget-heading p {
        font-size: 16px;
        color: #9DA5B2
    }

    .widget-mg-top {
        margin-top: 55px;
    }

    .slides-open-btn {
        position: absolute;
        left: 0px;
        z-index: 10;
        top: 50%;
        cursor: pointer;
    }

    .slides-close-btn {
        position: absolute; 
        left: -8px; 
        top: 50%; 
        cursor: pointer
    }

    .slides-container > div > img {
        width: 100%;
        height: 100%
    }

    .slides-container > div:nth-child(1) {
        width: 182px; 
        height: 323px; 
        top: -30px; 
        z-index: 4; 
        background: #FFFFFF; 
        position: absolute; 
        border-radius: 12px; 
        box-shadow: 0 21px 33px 0 rgba(44,45,101,0.13);
        cursor: pointer;
    }

    .slides-container > div:nth-child(2) {
        width: 148px; 
        height: 259px; 
        opacity: 0.6; 
        z-index: 3; 
        left: 80px; 
        top: 5px; 
        background: #FFFFFF; 
        position: absolute; 
        box-shadow: 0 21px 33px 0 rgba(44,45,101,0.13); 
        border-radius: 9.6px;        
    }

    .slides-container > div:nth-child(3) {
        width: 117px; 
        height: 195px; 
        opacity: 0.4; 
        z-index: 2; 
        left: 140px; 
        top: 40px; 
        background: #FFFFFF; 
        position: absolute; 
        box-shadow: 0 21px 33px 0 rgba(44,45,101,0.13); 
        border-radius: 10px;
    }

    .slides-container > div:nth-child(4) {
        width: 79px; 
        height: 132px; 
        opacity: 0.4; 
        z-index: 1; 
        left: 205px; 
        top: 70px; 
        background: #FFFFFF; 
        position: absolute; 
        box-shadow: 0 21px 33px 0 rgba(44,45,101,0.13); 
        border-radius: 10px;
    }

    .elastic-container-detail > h3 {
        font-size: 18px; 
        color: #041847
    }

    .slides-container-full {
        background: #FFFFFF; 
        width: 135px; 
        height: 240px; 
        box-shadow: 0 22px 23px 0 rgba(44,45,101,0.15); 
        border-radius: 9px;
    }

    .slides-container-full > img {
        width: 100%;
        height: 100%;
    }

    .elastic-container-stacked {
        animation-fill-mode: forwards !important;
        position: absolute;
        padding: 44px 48px;
    }
    .elastic-container-detail {
        animation-fill-mode: forwards !important;
        position: absolute;
        padding: 44px 48px;
    }
    .elastic-container-heading {
        position: absolute;
    }
    .elastic-right {
        animation: elastic-right 0.8s;
    }
    .elastic-left {
        animation: elastic-left 0.8s;
    }
    .elastic-bottom {
        animation: elastic-bottom 0.8s;
    }
    @keyframes elastic-right {
        0% {
            left: calc(100% - 20px);
        }
        20% {
            left: 0%;
        }
        40% {
            left: 5%;
        }
        60% {
            left: 0%;
        }
        100% {
            left: 0%;
        }
    }
    @keyframes elastic-left {
        0% {
            right: calc(100% - 20px);
        }
        20% {
            right: 0%;
        }
        40% {
            right: 5%;
        }
        60% {
            right: 0%;
        }
        100% {
            right: 0%;
        }
    }
</style>
