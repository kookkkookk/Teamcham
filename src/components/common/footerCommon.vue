<template>
    <footer>
        <div class="footerContent">
            <div class="footerContentLeft">
                <h1 class="footerLogo"></h1>
                <ul>
                    <li>鼎晟不動產開發有限公司</li>
                    <li>Teamcham Estate Corporation</li>
                    <li>100 台北市中正區忠孝西路一段50號13樓之8</li>
                    <li>客服電話: (02)2370-3200</li>
                    <li>客服傳真: (02)2331-7668</li>
                    <li>客服信箱: service@teamcham.com</li>
                </ul>
            </div>
            <div class="footerContentCenterLine"></div>
            <div class="footerContentRight">
                <ul>
                    <li>
                        <a href="javascript:;">關於鼎晟</a>
                        <div class="arrow"></div>
                        <ul>
                            <li><a href="javascript:;">品牌宣言</a></li>
                            <li><a href="javascript:;">大事紀要</a></li>
                            <li><a href="javascript:;">關係企業</a></li>
                            <li><a href="javascript:;">服務項目</a></li>
                        </ul>
                    </li>
                    <li><a href="javascript:;">停車位買賣與仲介</a></li>
                    <li><a href="javascript:;">停車場租賃與管理</a></li>
                    <li><a href="javascript:;">倉儲空間租賃</a></li>
                    <li><a href="javascript:;">不動產投資專區</a></li>
                </ul>
            </div>
        </div>
        <div class="copyright">
            <div class="copyrightContent">
                <ul>
                    <li><a href="javascript:;"></a></li>
                    <li><a href="javascript:;"></a></li>
                </ul>
                <h3>COPYRIGHT © 2015　鼎晟不動產開發 ALL RIGHTS RESERVED.</h3>
            </div>
        </div>
    </footer>
</template>
<script>
export default {
    
}
</script>
<style lang="scss">
    @import '../../assets/scss/_mixin.scss';
    footer{
        width: 100%;
        background-color: #ededed;
        @include SCREEN_1300{
            margin-top: 30px;
        }
        .footerContent{
            height: 320px;
            width: 1280px;
            margin: 0 auto;
            @include SCREEN_1300{
                width: 100%;
            }
            .footerContentLeft{
                width: 40%;
                float: left;
                @include SCREEN_1300{
                    width: 90%;
                    margin-left: 5%;
                }
                .footerLogo{
                    width: 160px;
                    height: 40px;
                    background-image: url("../../assets/images/footer_Logo.png");
                    display: inline-block;
                    margin-top: 50px;
                }
                >ul{
                    margin-top: 10px;
                    >li{
                        font-size: 15px;
                        color: #6c6b6b;
                        line-height: 30px;
                        &:first-child{
                            font-size: 20px;
                        }
                    }
                }
            }
            .footerContentCenterLine{
                width: 1px;
                height: calc(100% - 80px);
                margin-top: 50px;
                float: left;
                background-color: #b4c5ce;
                @include SCREEN_1300{
                    display: none;
                }
            }
            .footerContentRight{
                width: calc(60% - 1px);
                float: left;
                @include SCREEN_1300{
                    display: none;
                }
                >ul{
                    overflow: hidden;
                    margin-top: 88px;
                    margin-left: 90px;
                    >li{
                        float: left;
                        margin-right: 37px;
                        &:last-child{
                            margin-right: 0px;
                        }
                        >a{
                            font-size: 16px;
                            color: #757575;
                            display: block;
                            text-decoration: none;
                        }
                        .arrow{
                            width: 100%;
                            height: 20px;
                            background-color: pink;
                            display: block;
                            position: relative;
                            
                        }
                        >ul{
                            >li{
                                margin-top: 15px;
                                >a{
                                    font-size: 16px;
                                    color: #757575;
                                    display: block;
                                    text-decoration: none;
                                }
                            }
                        }
                    }
                }
            }
        }
        
        .copyright{
            width: 100%;
            height: 40px;
            background-color: #7b8d9f;
            @include SCREEN_1300{
                height: auto;
            }
            .copyrightContent{
                width: 1280px;
                margin: 0 auto;
                text-align: center;
                @include SCREEN_1300{
                    width: 100%;
                }
                >ul{
                    overflow: hidden;
                    display: inline-block;
                    float: left;
                    >li{
                        float: left;
                        &:first-child{
                            margin-right: 5px;
                        }
                        >a{
                            width: 30px;
                            height: 40px;
                            display: block;
                            background-repeat: no-repeat;
                            background-position: 0% 0%;
                        }
                        
                        &:first-child > a{
                            background-image: url("../../assets/images/footer_Line.png");
                        }
                        &:last-child > a{
                            background-image: url("../../assets/images/footer_Fb.png");
                        }
                        &:hover > a{
                            background-position: 0% 100%;
                        }
                    }
                }
                >h3{
                    font-size: 16px;
                    color: #fff;
                    line-height: 40px;
                    display: inline-block;
                    @include SCREEN_1300{
                        font-size: 12px;
                    }
                }
            }
        }
    }
</style>


