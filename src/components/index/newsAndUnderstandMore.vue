<template>
    <div class="hotCaseArea NewsArea">
        <h1>News <span>最新消息</span></h1>
        <ol>
            <!-- <li>
                <div data-switch="false" class="more" @click="moreDescription"></div>
                <div class="date">2017.09.11</div>
                <h1 class="title">車位貴鬆鬆 北市哪裡漲最多？</h1>
                <p class="description">在高房價的台北市買車位，應該準備多少錢呢？大家房屋統計去年、今年各行政區車位實價行情，台北市平面車位去年均價191.7萬元，今年漲至197.2萬元，漲幅2.9%；機械式車位去年111.5萬元、今年108.1萬元，反跌3.1%.....</p>
                <div class="thismore"><span></span><span></span></div>
            </li> -->

            <li v-for="(item, index) in newsAry"
                :key="index">
                <div class="more" @click="moreDescription(index)"
                     :class="{open:item.isShow}"></div>
                <div class="date">{{item.date}}</div>
                <h1 class="title">{{item.title}}</h1>
                <transition enter-active-class="animated fadeIn"
                            leave-active-class="animated fadeOut">
                    <p class="description" v-show="item.isShow">{{item.description}}</p>
                </transition>
                <div class="thismore" v-show="item.isShow"><span></span><span></span></div>
            </li>


        </ol>
        <div class="moreHotCase"><a href="javascript:;">更多消息 <span></span></a></div>

        <div class="understandMoreArea">
            <ol>
                <li>
                    <h1>個人倉儲空間<br/>為您解決儲物煩惱</h1>
                    <p>
                        <a href="javascript:;">馬上預定...</a>
                    </p>
                </li>
                <li>
                    <h1>輕鬆投資不動產<br/>理財規劃的首選</h1>
                    <p>
                        <a href="javascript:;">了解更多...</a>
                    </p>
                    
                </li>
            </ol>
        </div>
    </div>
</template>
<script>
// import Vue from "vue";
import axios from 'axios'
// import VueAxios from 'vue-axios'
import newsData from "../../assets/data/index/news.json";
// import Es6Promise from "es6-promise"; //處理IE11 axios無法引入ES6問題
// Es6Promise.polyfill();
// Vue.use(VueAxios, Axios)
export default {
    name: "news-and-understand-more",
    data() {
        return {
            newsAry: []
        }
    },
    computed: {
        // disPlaySwitch() {
        //     return this.newsAry.map(function(child){
        //         return {
        //             isShow: false
        //         }
        //     })
        // }
    },
    methods: {
        moreDescription: function(index){
        //moreDescription: (index)=> {
            //console.log(e.target.dataset.switch)
            //if(!e.target.dataset.switch){}
            this.newsAry[index].isShow = !this.newsAry[index].isShow
        }
    },
    //created new Vue前發生 dom為炫覽至畫面
    created() {
        let item = [];
        console.log(newsData)
        newsData.forEach((obj,idx)=>{
            obj.isShow = idx ===0 ? true : false;
            item.push(obj)
        })
        this.newsAry = item;
    },
    //mounted new Vue前發後 dom已炫覽至畫面
    mounted(){
        //如果是在本地端的內的資料，vue cli已經做到資料引入與分析這塊，可以直接引入該data，並且直接就是可解析的檔案
        // newsData.map((obj)=>{
        //     //this.newsAry.push(obj);
            
        // })
        
        




        //需要連到本地端外的才需要axios
        /*axios.get(newsapi)
        .then((response)=> {
            console.log("response:", response.data)
        })
        .catch((error)=> {
            console.log(error)
        });*/
    }
}
</script>
<style lang="css" src="../../assets/css/animate.min.css"></style>
<style lang="scss">
    @import '../../assets/scss/_mixin.scss';
    .NewsArea{
        >h1{
            text-align: center;
        }
        >ol{
            margin-left: 35px;
            border-top: 1px solid #d2d2d2;
            position: relative;
            >li{
                // display: flex;
                // align-items: center;
                border-bottom: 1px dashed #d2d2d2;
                padding: 20px 0;
                overflow: hidden;
                position: relative;
                .more{
                    width: 20px;
                    height: 20px;
                    background-color: #000;
                    border-radius: 10px;
                    float: left;
                    position: relative;
                    cursor: pointer;
                    &::before{
                        content: "";
                        width: 12px;
                        height: 1px;
                        background-color: #d2d2d2;
                        display: block;
                        position: absolute;
                        top: 9.5px;
                        left: 4px;
                    }
                    &::after{
                        content: "";
                        width: 12px;
                        height: 1px;
                        background-color: #d2d2d2;
                        display: block;
                        position: absolute;
                        top: 9.5px;
                        left: 4px;
                        transform: rotate(90deg);
                    }
                    &.open{
                        &::after{
                            transform: rotate(0deg);
                        }
                    }
                }
                .date{
                    font-size: 18px;
                    color: #0052a4;
                    padding: 0 25px 0 15px;
                    float: left;
                }
                .title{
                    font-size: 24px;
                    color: #676767;
                    float: left;
                }
                .description{
                    clear: both;
                    padding-top: 20px;
                    padding-left: 25px;
                    font-size: 18px;
                    color: #949494;
                    line-height: 24px;
                    position: relative;
                    z-index: 1;
                }
                .thismore{
                    width: 40px;
                    height: 40px;
                    background-color: #acc8d4;
                    position: absolute;
                    bottom: 0;
                    right: 0;
                    cursor: pointer;
                    &::before{
                        content: "";
                        display: block;
                        width: 82px;
                        height: 82px;
                        background-color: #f7f7f7;
                        pointer-events: none;
                        transform: rotate(45deg);
                        margin-top: -50px;
                        margin-left: -50px;
                    }
                    >span{
                        width: 12.5px;
                        height: 2px;
                        background-color: #fff;
                        display: block;
                        // border-radius: 1px;
                        position: absolute;
                        right: 6px;
                        bottom: 10px;
                        &:last-child{
                            transform: rotate(90deg);
                        }
                    }
                }
            }
        }

    }

    .understandMoreArea{
        width: 100%;
        >ol{
            margin-left: 35px;
            @include SCREEN_1300{
                margin-left: 0px;
            }
            overflow: hidden;
            >li{
                width: 49.5%;
                height: 400px;
                background-size: cover;
                background-repeat: no-repeat;
                background-position: 50% 50%;
                float: left;
                &:first-child{
                    margin-right: 1%;
                    background-image: url("../../assets/images/right_ad1.jpg");
                }
                &:last-child{
                    background-image: url("../../assets/images/right_ad2.jpg");
                }
                >h1{
                    font-size: 25px;
                    font-weight: bold;
                    color: #fff;
                    text-align: center;
                    line-height: 32px;
                    margin-top: 110px;
                }
                >p{
                    margin-top: 25px;
                    text-align: center;
                    >a{
                        padding: 7px 16px;
                        font-size: 20px;
                        font-weight: bold;
                        text-decoration: none;
                        border: 1px solid #fff;
                        color: #fff;
                        display: inline-block;
                        &:hover{
                            background-color: #fff;
                            color: #000;
                        }  
                    }
                }
            }
        }
    }


    .fade-enter-active, .fade-leave-active {
        transition: opacity .3s;
    }
    .fade-enter, .fade-leave-to {
        opacity: 0;
    }
</style>