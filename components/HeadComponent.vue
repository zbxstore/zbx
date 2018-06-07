<style lang="less" scoped>
    @headHeight: 70px;
    header {
        width: 100%;
        min-width: 1200px;
        height: @headHeight;
        position: absolute;
        top: 0;
        left: 0;
        z-index: 999;
        background: #3034D5;
        .container{
            display: flex;
        }
        .head-logo {
            flex: 1;
            position: relative;
            font-size: 30px;
            color: #fff;
            line-height: 70px;
            b {
                margin-left: 72px;
            }
            i {
                position: absolute;
                top: 2px;
                left: 0;
                width: 70px;
                height: 70px;
                text-align: center;
                font-size: 50px;
                animation: tanScale 1.5s ease infinite;
            }
        }
        ul {
            flex: 2;
            //background: pink;
            li {
                width: 100px;
                height: @headHeight;
                float: left;
                text-align: center;
                line-height: @headHeight;
                a {
                    font-size: 16px;
                    padding-bottom: 5px;
                    color: #fff;
                    position: relative;
                    .head-hot {
                        width: 30px;
                        height: 30px;
                        background: url('../assets/img/hot.png') no-repeat;
                        display: block;
                        position: absolute;
                        top: -20px;
                        right: -35px;
                        background-size: contain;
                    }
                    i {
                        font-size: 20px;
                    }
                    .wechat {
                        width: 240px;
                        height: auto;
                        background: #fff;
                        position: absolute;
                        border: 1px solid #ddd;
                        img {
                            width: 100%;
                        }
                    }
                    .wechat::before {
                        content: "";
                        display: block;
                        width: 0;
                        height: 0;
                        border-left: 20px solid transparent;
                        border-right: 20px solid transparent;
                        border-bottom: 20px solid #fff;
                        position: absolute;
                        top: -20px;
                        left: 20px;
                    }
                }
                a:hover,
                a.active,
                .router-link-active {
                    border-bottom: 2px solid #086CEA;
                    color: #fff;
                }
            }
            li:last-child {
                a:hover {
                    border: none;
                    color: #3DA149;
                }
            }
        }
        .head-log-reg {
            width: 300px;
            height: @headHeight;
            float: left;
            text-align: center;
            line-height: @headHeight;
            /* background: pink; */
            a {
                padding: 5px 20px;
                border: 2px solid #fff;
                margin: 0 10px;
                color: #fff;
                font-size: 14px;
                border-radius: 50px;
            }
            a:hover {
                background: #086CEA;
                border-color: #086CEA;
                color: #fff;
            }
            a.active {
                background: #086CEA;
                border-color: #086CEA;
                color: #fff;
            }
        }
    }
    .headBgcolor {
        background: #000;
        .head-logo {
            i {
                display: none;
            }
            b {
                position: relative;
                left: -20px;
            }
        }
        .logo-wrap {
            color: #fff;
            width: 230px;
            transform: skewX(-15deg);
            background: linear-gradient(90deg, #086CEA, #3034D5);
        }
    }
</style>


<template>
    <header :class="{headBgcolor: false}">
        <div class="container">
            <div class="head-logo">
                <div class="logo-wrap">
                    <i class="iconfont icon-ruleengine-data"></i>
                    <b>zbx.Store</b>
                </div>
            </div>
            <ul>
                <li>
                    <router-link to="/" exact>首页</router-link>
                </li>
                <li>
                    <router-link to="/video">
                        视频
                        <span class="head-hot"></span>
                    </router-link>
                </li>
                <li>
                    <router-link to="/box">
                        宝箱
                    </router-link>
                </li>
                <li>
                    <router-link to="/case">
                        演示
                    </router-link>
                </li>
                <li>
                    <a href="javascript:" @click="wechat()">
                        <i class="iconfont icon-qrcode"></i>
                        <div class="wechat" v-show="wechatShow">
                            <img src="../assets/img/wechat.jpg" alt="">
                        </div>
                    </a>
                </li>
            </ul>
            <div class="head-log-reg" v-if="false">
                <router-link to="/login">登录</router-link>
                <router-link to="/reg">注册</router-link>
            </div>
        </div>
    </header>
</template>

<script>
    export default {
        data() {
            return {
                wechatShow: false,
            }
        },
        methods: {
            wechat() {
                if (this.wechatShow) {
                    this.wechatShow = false;
                } else {
                    this.wechatShow = true;
                }
            }
        },
    }
</script>
