<template>
    <div class="below">
        <div class="belowContent">
            <ul>
                <li>
                    <a href="javascript:;"><img src="../../assets/images/below_ad1.jpg" alt=""></a>
                </li>
                <li>
                    <a href="javascript:;"><img src="../../assets/images/below_ad2.jpg" alt=""></a>
                </li>
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
    .below{
        width: 100%;
        height: 320px;
        background-image: url("../../assets/images/below_adBg.jpg");
        background-size: cover;
        background-repeat: no-repeat;
        background-position: 100% 50%;
        @include SCREEN_1300{
            background-image: url("");
        }
        .belowContent{
            width: 1280px;
            height: 320px;
            margin: 0 auto;
            @include SCREEN_1300{
                width: 100%;
            }
            >ul{
                display: flex;
                justify-content: space-around;
                padding-top: 40px;
                @include SCREEN_1300{
                    width: 90%;
                    display: block;
                    margin: 0 auto;
                }
                >li{
                    >a{
                        display: block;
                        img{
                            width: 100%;
                        }
                    }
                }
            }
        }
    }
</style>


