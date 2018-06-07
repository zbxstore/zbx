<template>
    <section class="query">
        <section class="content">
            <header>
                <p> <span>前端开发工程师 • 简历</span></p>
                <div class="download">
                    <a href="../../static/lib/web.zip">下载简历</a>
                </div>
            </header>
            <div class="tan">
                <div class="tanPic">
                    <a href="javascript:" title="点击头像下载简历"><img src="../assets/img/html5.png" alt="" width="100%"></a>
                </div>
                <div class="tanInfo">
                    <p><b>谭杰</b>男 26岁</p>
                    <p><span><em>期望行业：</em>非外包</span><span><em>所在地点：</em>安徽合肥蜀山区</span></p>
                    <p><span><em>期望职位：</em>web前端开发工程师</span><span><em>期望月薪：</em>10k-12k</span></p>
                </div>
            </div>
            <div class="basic">
                <p class="title"><i class="iconfont icon-wunderlist"></i><b>个人资料</b> <a href="javascript:"><i class="iconfont icon-arrow-down-drop-circle-outline"></i></a></p>
                <ul>
                    <li><span><em>手　　机：</em>18256072170</span><span><em>工作年限：</em>3年</span></li>
                    <li><span><em>邮　　箱：</em>tanie@foxmail.com</span><span><em>个人网站：</em><a href="//www.zbx.store" target="_blank">www.zbx.store</a></span></li>
                </ul>
            </div>
            <div class="basic">
                <p class="title"><i class="iconfont icon-archive"></i><b>工作经历</b> <a href="javascript:"><i class="iconfont icon-arrow-down-drop-circle-outline"></i></a></p>
                <ul>
                    <li><em></em>安徽强石科技有限公司</li>
                    <li><em></em>百强网旗下相关项目前端开发</li>
                    <br>
                    <li><em></em>安徽索兑软件服务有限公司</li>
                    <li><em></em>负责公司证期、游戏、第三方支付的前端开发工作</li>
                    <br>
                    <li><em></em>合肥东弘信息科技有限公司</li>
                    <li><em></em>负责公司前端基础培训、网站开发与维护工作</li>
                </ul>
            </div>
            <div class="basic">
                <p class="title"><i class="iconfont icon-tooltip-text"></i><b>技能概述</b> <a href="javascript:"><i class="iconfont icon-arrow-down-drop-circle-outline"></i></a></p>
                <ul>
                    <li><em>1)</em>3年web前端开发工作经验;</li>
                    <li><em>2)</em>倾向产品型公司,不太倾向外包和政府类项目;</li>
                    <li><em>3)</em>了解HTML5、Css3、JavaScript、Ajax、Json等各项技术的相关标准;</li>
                    <li><em>4)</em>对web开发有整体认识,熟悉浏览器兼容和跨终端(pc+mobile+pad)开发;</li>
                    <li><em>5)</em>熟练使用jQuery、Vue等前端库与框架;</li>
                    <li><em>6)</em>主要采用基于Vue.js技术桟:vue-cli、vue-router、vuex及其周边资源</li>
                    <li><em>7)</em>熟练使用各种IDE和构建工具，对前端自动化、代码模块化、静态资源优化等有了解;</li>
                    <li><em>8)</em>熟悉node.js开发环境、npm、ES6、webpack等,喜欢研究GitHub . </li>
                </ul>
            </div>
            <div class="basic">
                <p class="title"><i class="iconfont icon-clipboard-text"></i><b>个人标签</b> <a href="javascript:"><i class="iconfont icon-arrow-down-drop-circle-outline"></i></a></p>
                <ul class="aTag">
                    <li><a href="javascript:">前端</a><a href="javascript:">用户体验</a><a href="javascript:">产品思维</a><a href="javascript:">技术控</a><a href="javascript:">交互设计</a><a href="javascript:">移动端</a><a href="javascript:">版本控</a></li>
                </ul>
            </div>
            <div class="footer-bg">
                <p>-- 以技术驱动企业价值增长 --</p>
            </div>
        </section>
    </section>
</template>

<script>
    export default {};
</script>


<style scoped lang="less">
    .query {
        width: 100%;
        height: auto;
        background: #eee;
        float: left;
        position: relative;
        border-top: 3px solid orangered;
        .content {
            width: 800px;
            height: auto;
            border: 1px solid #ddd;
            margin: 50px auto;
            /* 头部 */
            header {
                width: 100%;
                height: 90px;
                background: linear-gradient(45deg, #3034d5, #ff4040);
                position: relative;
                /*  */
                p {
                    text-align: center;
                    height: 90px;
                    color: #fff;
                    font-size: 18px;
                    i {
                        font-size: 30px !important;
                        line-height: 90px;
                        margin-right: 5px;
                        vertical-align: middle;
                        position: relative;
                        top: -2px;
                    }
                    span {
                        line-height: 90px;
                        display: inline-block;
                    }
                }

                /* 下载 */
                .download {
                    position: absolute;
                    top:25px;
                    right:50px;
                    a{
                        width: 120px;
                        height: 40px;
                        color: #fff;
                        display: block;
                        border-radius: 50px;
                        text-align: center;
                        line-height: 40px;
                        border:2px solid #fff;

                    }
                    a:hover{
                        background: #fff;
                        color: #3034d5;
                    }
                }

            }
            .tan {
                width: 100%;
                height: 164px;
                background: #fafafa;
                position: relative;
                .tanPic {
                    width: 100px;
                    height: 100px;
                    float: left;
                    margin: 32px 0px 32px 50px;
                    border-radius: 50%;
                    position: relative;
                    left: -10px;
                    img {
                        width: 100px;
                        height: 100px;
                        position: relative;
                        overflow: hidden;
                    }
                }
                .tanInfo {
                    width: 640px;
                    height: 164px;
                    /*background: pink;*/
                    float: left;
                    p {
                        padding: 10px 0 0 20px;
                        font-size: 14px;
                        b {
                            font-size: 24px;
                            padding-right: 32px;
                        }
                        span {
                            display: inline-block;
                            width: 300px;
                        }
                    }
                    p:first-child {
                        margin-top: 32px;
                    }
                }
            } //基础内容
            .basic {
                width: 100%;
                height: auto;
                border-bottom: 1px dashed #ddd;
                background: #ffffff;
                overflow: hidden;
                p a {
                    margin-left: 580px;
                }
                ul {
                    width: 100%;
                    height: auto;
                    //background: pink;
                    li {
                        margin-left: 173px;
                        font-size: 14px;
                        height: 30px;
                        span {
                            display: inline-block;
                            width: 300px;
                            a {
                                font-size: 14px;
                                color: #353ebf;
                            }
                            a:hover {
                                color: #22a1f4;
                            }
                        }
                    }
                    li:last-child {
                        margin-bottom: 20px;
                    }
                }
                .title {
                    width: 100%;
                    font-size: 16px;
                    color: #454545;
                    padding: 20px 50px;
                    //background: red;
                    i {
                        font-size: 22px;
                        position: relative;
                        top: 3px;
                        padding-right: 3px;
                    }
                }
                .aTag a {
                    display: inline-block;
                    border: 1px solid #ddd;
                    padding: 5px 10px;
                    text-align: center;
                    color: #454545;
                    margin-right: 10px;
                }
            }
            .footer-bg {
                width: 100%;
                height: 90px;
                background: #fff;
                text-align: center;
                line-height: 90px;
                font-size: 18px;
                color: #454545;
            }
        }
    }
</style>

