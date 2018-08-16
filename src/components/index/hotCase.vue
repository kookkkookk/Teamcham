<template>
    <div class="hotCaseArea">
        <h1>Hot Case <span>熱銷案件</span></h1>
        <ul>
            <li><img src="../../assets/images/left_ad1__.jpg"><h3>君臨天廈</h3><p>地點: 永和中正路</p><div><span></span><span></span></div></li>
            <li><img src="../../assets/images/left_ad2__.jpg"><h3>貴興路</h3><p>地點: 板橋亞東商圈</p><div><span></span><span></span></div></li>
            <li><img src="../../assets/images/left_ad3__.jpg"><h3>山妍四季</h3><p>地點: 內湖路二段</p><div><span></span><span></span></div></li>
            <li><img src="../../assets/images/left_ad4__.jpg"><h3>貴興路</h3><p>地點: 板橋亞東商圈</p><div><span></span><span></span></div></li>
        </ul>
        <div class="moreHotCase"><a href="javascript:;">更多熱銷 <span></span></a></div>
    </div>
</template>
<script>
export default {
    name: "hot-case"
}
</script>
<style lang="scss">
    @import '../../assets/scss/_mixin.scss';
    .hotCaseArea{
        float: left;
        width: 640px;
        @include SCREEN_1300{
            float: none;
            width: 100%;
        }
        >h1{
            font-size: 60px;
            color: #ababab;
            font-family: initial;
            margin-bottom: 47px;
            @include SCREEN_1300{
                font-size: 40px;
                margin-bottom: 30px;
                text-align: center;
            }
            >span{
                font-size: 24px;
                color: #676767;
                font-family: "Microsoft JhengHei", "PMingLiU", "Arial Unicode MS", sans-serif;
                font-weight: bold;
                @include SCREEN_1300{
                    font-size: 18px;
                }
            }
        }
        >ul{
            overflow: hidden;
            >li{
                width: 49%;
                margin: 0.5%;
                background-color: #f7f7f7;
                border: 1px solid #e0e0e0;
                float: left;
                overflow: hidden;
                >img{
                    width: 100%;
                }
                >h3{
                    font-size: 22px;
                    color: #676767;
                    margin-top: 30px;
                    margin-left: 36px;
                    padding-right: 20px;
                    position: relative;
                    z-index: 1;
                }
                >p{
                    font-size: 16px;
                    color: #676767;
                    margin-top: 10px;
                    margin-left: 36px;
                    padding-right: 20px;
                    position: relative;
                    z-index: 1;
                }
                >div{
                    width: 67px;
                    height: 67px;
                    background-color: #acc8d4;
                    float: right;
                    position: relative;
                    cursor: pointer;
                    &::before{
                        content: "";
                        display: block;
                        width: 100px;
                        height: 100px;
                        background-color: #f7f7f7;
                        pointer-events: none;
                        transform: rotate(45deg);
                        margin-top: -50px;
                        margin-left: -50px;
                    }
                    >span{
                        width: 25px;
                        height: 4px;
                        background-color: #fff;
                        display: block;
                        border-radius: 2px;
                        position: absolute;
                        right: 8px;
                        bottom: 17px;
                        &:last-child{
                            transform: rotate(90deg);
                        }
                    }
                }
            }
        }
        .moreHotCase{
            width: 100%;
            margin: 40px 0 25px 0;
            text-align: center;
            >a{
                font-size: 20px;
                color: #676767;
                text-decoration: none;
                line-height: 30px;
                display: flex;
                justify-content: center;
                align-items: center;
                &:hover{
                    color: blue;
                }
                >span{
                    width: 30px;
                    height: 20px;
                    background-image: url('../../assets/images/arrow.jpg');
                    margin-left: 8px;
                }
            }
        }
    }
</style>