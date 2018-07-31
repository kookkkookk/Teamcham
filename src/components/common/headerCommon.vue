<template>
    <header>
        <div class="headerContent">
            <h1>TEAMCHAM 鼎昇</h1>

            <div class="menuMobileBtn"
                 v-if="!isMobileDisable"
                 @click="playMobileMenu()">
                <span :class="{menuMobileOpen: isMobileMenuSwitch}"></span>
                <span :class="{menuMobileOpen: isMobileMenuSwitch}"></span>
                <span :class="{menuMobileOpen: isMobileMenuSwitch}"></span>
            </div>
            <div class="menuContent"
                 :class="{menuContentisDesktop: !isMobileDisable,
                          menuMobileOpen: isMobileMenuSwitch}">
                <!-- <ul v-if="isMobileDisable"> -->
                <ul>
                    <li>
                        <a href="javascript:;">關於鼎晟</a>
                        <div class="subMenu">
                            <ul>
                                <li><a href="javascript:;">品牌宣言</a></li>
                                <li><a href="javascript:;">大事記要</a></li>
                                <li><a href="javascript:;">關係企業</a></li>
                                <li><a href="javascript:;">服務項目</a></li>
                            </ul>
                        </div>
                    </li>
                    <li><a href="javascript:;">停車位買賣與仲介</a></li>
                    <li><a href="javascript:;">停車場租賃與管理</a></li>
                    <li><a href="javascript:;">倉儲空間租賃</a></li>
                    <li><a href="javascript:;">不動產投資專區</a></li>
                    <li><a href="javascript:;">最新消息</a></li>
                </ul>
            </div>

            <div class="handy">
                <ul>
                    <li><a href="javascript:;"></a></li>
                    <li><a href="javascript:;"></a></li>
                </ul>
            </div>
        </div>
    </header>
</template>

<script>
export default {
    name: 'headerCommon',
    data() {
        return {
            isMobileDisable: null,
            isMobileMenuSwitch: false
        }
    },
    methods: {
        playMobileMenu: function(){
            this.isMobileMenuSwitch = !this.isMobileMenuSwitch;
        }
    },
    mounted(){
        console.log(document.body.clientWidth)
        if(document.body.clientWidth > 1300){
            this.isMobileDisable = true;
        }else{
            this.isMobileDisable = false;
        }

        /*window.onresize = function(event){
            // console.log("resize")
            if(document.body.clientWidth > 1300){
                this.isMobileDisable = true;
                console.log("is Desktop")
            }else{
                this.isMobileDisable = false;
                console.log("is Mobile")
            }
        }*/
    }
}
</script>

<style lang="scss">
    @import '../../assets/scss/_mixin.scss';
    header{
        width: 100%;
        height: 80px;
        background-color: #FFF;
        display: flex;
        position: relative;
        z-index: 50;
        @include SCREEN_1300{
            height: 60px;
        }
    }
    .headerContent{
        //flex: 0 1 1280px;
        width: 1280px;
        margin: 0 auto;
        // background-color: pink;
        display: flex;
        align-items: flex-start;
        justify-content: space-between;

        @include SCREEN_1300{
            width: 100%;
        }
        >h1{
            @include text-hide;
            background-image: url('../../assets/images/top_Logo.png');
            flex: 0 0 231px;
            height: 55px;
            margin-top: 12px;
            // float: left;
            margin-right: 30px;
            
            display: inline-flex;
            @include SCREEN_1300{
                background-image: url('../../assets/images/footer_Logo.png');
                flex: 0 0 160px;
                height: 40px;
                margin-top: 10px;
                margin-right: 0px;
                margin-left: 10px;
            }
        }
        .menuMobileBtn{
            width: 50px;
            height: 50px;
            border: 1px solid #0052a4;
            position: absolute;
            top: 5px;
            right: 10px;
            z-index: 1;
            
            >span{
                width: 80%;
                height: 4px;
                border-radius: 2px;
                background-color: #0052a4;
                display: block;
                position: absolute;
                left: 10%;
                transition: all 0.3s;
                transition-timing-function: ease-in-out;
                transform-origin: 50% 50%;
                &:nth-child(1){
                    top: 13.5px;
                }
                &:nth-child(2){
                    top: 23px;
                }
                &:nth-child(3){
                    top: 32.5px;
                }
            }
            >span.menuMobileOpen{
                &:nth-child(1){
                    top: 23px;
                    transform: rotate(45deg);
                }
                &:nth-child(2){
                    opacity: 0;
                }
                &:nth-child(3){
                    top: 23px;
                    transform: rotate(-45deg);
                }
            }
        }

        .menuContent{
            // float: left;
            flex-grow: 1;
            @include SCREEN_1300{
                flex-grow: 0;
                height: auto;
            }
            
            >ul{
                display: flex;
                justify-content: space-around;
                @include SCREEN_1300{
                    // justify-content: flex-start;
                    flex-direction:column;
                    margin-top: 60px;
                }
                >li{
                    // margin: 0 15px;
                    height: auto;
                    cursor: pointer;
                    position: relative;
                    @include SCREEN_1300{
                        background-color: #fff;
                        &:last-child{
                            padding-bottom: 10px;
                            border-radius: 0 0 0 25px;
                            >a{
                                border: none;
                            }
                        }
                        &:first-child>a{
                            border: none;
                        }
                        >a{
                            border-bottom: 1px solid #cdcdcd;
                        }
                    }
                    >a{
                        line-height: 80px;
                        color: #7c9daf;
                        font-size: 20px;
                        font-weight: bold;
                        text-decoration: none;

                        height: 80px;
                        display: block;
                        position: relative;
                        z-index: 1;
                        background-color: #fff;
                        @include SCREEN_1300{
                            line-height: 50px;
                            height: 50px;
                            font-size: 16px;
                            margin: 0 30px;
                        }
                    }
                    &:hover>a{
                        color: #0052a4;
                    }
                    &:first-child > a::after{
                        content: "\FF1E";
                        display: inline-block;
                        color: #7c9daf;
                        font-weight: bold;
                        transform: rotate(90deg);
                        
                    }
                    &:hover:first-child > a::after{
                        color: #0052a4;
                    }

                    &:hover .subMenu{
                        bottom: -168px;
                    }

                    .subMenu{
                        width: 100%;
                        background-color: #ededed;
                        position: absolute;
                        bottom: 0;
                        transition: all 0.5s;
                        @include SCREEN_1300{
                            position: static;
                        }
                        >ul{
                            >li{
                                text-align: center;
                                &:hover{
                                    background-color: #0052a4;
                                }
                                &:hover>a{
                                    color: #fff;
                                }
                                >a{
                                    font-size: 20px;
                                    font-weight: bold;
                                    color: #7c9daf;
                                    text-decoration: none;
                                    display: block;
                                    padding: 11px 0;
                                    @include SCREEN_1300{
                                        font-size: 16px;
                                    }
                                }
                                
                            }
                            
                        }
                    }
                }
            }
        }
        .menuContent.menuContentisDesktop{
            position: absolute;
            top: 0;
            right: -188px;
            transition: all 0.5s;
            transition-timing-function: ease-in-out;
        }
        .menuContent.menuContentisDesktop.menuMobileOpen{
            right: 0px;
        }

        .handy{
            // float: right;
            @include SCREEN_1300{
                position: absolute;
                top: 0px;
                right: 60px;
            }
            >ul{
                >li{
                    float: left;
                    margin: 0 6px;
                    margin-top: 12.5px;
                    @include SCREEN_1300{
                        margin: 0 10px;
                        margin-top: 2.5px;
                    }
                    >a{
                        display: block;
                        width: 25px;
                        height: 55px;
                    }
                    &:first-child >a{
                        background-image: url("../../assets/images/top_member.png");
                        background-position: 0 0;
                        &:hover{
                            background-position: 0 100%;
                        }
                    }
                    &:last-child >a{
                        background-image: url("../../assets/images/top_mail.png");
                        &:hover{
                            background-position: 0 100%;
                        }
                    }
                }
            }
        }
    }
</style>