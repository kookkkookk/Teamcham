<template>
    <div class="service">
        <h1>Our Service</h1>
        <div class="serviceArea">
            <ul>
                <li><a href="javascript:;"></a><span>停車位買賣與仲介</span></li>
                <li><a href="javascript:;"></a><span>停車場租賃與管理</span></li>
                <li><a href="javascript:;"></a><span>倉儲空間租賃</span></li>
                <li><a href="javascript:;"></a><span>不動產投資專區</span></li>
            </ul>
        </div>
    </div>
</template>
<script>
export default {
    
}
</script>
<style lang="scss">
    @import '../../assets/scss/_mixin.scss';
    .service{
        width: 100%;
        background-color: #ffffff;
        >h1{
            font-family: initial;
            font-size: 55px;
            color: #676767;
            display: block;
            text-align: center;
            padding-top: 78px;
            padding-bottom: 54px;
            @include SCREEN_1300{
                font-size: 40px;
                padding-top: 50px;
                padding-bottom: 26px;
            }
        }

        .serviceArea{
            width: 1280px;
            margin: 0 auto;
            padding-bottom: 94px;
            @include SCREEN_1300{
                width: 100%;
                padding-bottom: 30px;
            }
            >ul{
                display: flex;
                justify-content: space-around;
                @include SCREEN_1300{
                    // flex-direction: column;
                    align-content: flex-start;
                    flex-wrap:wrap;
                }
                >li{
                    text-align: center;
                    @include SCREEN_1300{
                        margin: 10px;
                        margin-bottom: 40px;
                    }
                    &:nth-child(1)>a{
                        background-image: url('../../assets/images/mainBtn1.png');
                    }
                    &:nth-child(2)>a{
                        background-image: url('../../assets/images/mainBtn2.png');
                    }
                    &:nth-child(3)>a{
                        background-image: url('../../assets/images/mainBtn3.png');
                    }
                    &:nth-child(4)>a{
                        background-image: url('../../assets/images/mainBtn4.png');
                    }
                    >a{
                        width: 231px;
                        height: 231px;
                        display: block;
                        background-size: contain;
                        background-repeat: no-repeat;
                        background-position: center;
                        text-decoration: none;
                        transition: all 0.3s;
                        @include SCREEN_1300{
                            width: 170px;
                            height: 170px;
                        }
                        &:hover{
                            background-size: 95%;
                        }
                        &::after{
                            content:"more";
                            display: flex;
                            justify-content: center;
                            align-items: center;
                            height: 100%;
                            background-color: rgba(#387ca2, 0);
                            border-radius: 115.5px;
                            opacity: 0;
                            text-align: center;
                            font-size: 20px;
                            color: #fff;
                            transition: all 0.3s;
                            
                        }
                        &:hover::after{
                            opacity: 1;
                            background-color: rgba(#387ca2, 0.6);
                        }
                    }

                    >span{
                        font-size: 20px;
                        line-height: 24px;
                        color: #676767;
                        display: block;
                        width: 90%;
                        margin: 0 auto;
                        border-top: 1px solid #cacaca;
                        padding-top: 12px;
                        margin-top: 20px;
                        @include SCREEN_1300{
                            font-size: 16px;
                            line-height: 20px;
                        }
                    }
                }
            }
        }
    }
</style>


