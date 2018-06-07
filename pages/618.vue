<template>
    <section id="index">
        <div class="index-banner">
        </div>
        <div class="index-content">
            <div class="content">
                <section class="sec-hc">
                    <div class="sec-hc-big">
                        <a :href="item.url" target="_blank" v-for="(item,index) in huicangBigList" :key="index">
                            <img :src="item.img" alt="">
                        </a>
                    </div>
                    <div class="sec-hc-small">
                        <ul>
                            <li v-for="(item,index) in huicangSmallList" :key="index">
                                <a :href="item.url" target="_blank">
                                    <img :src="item.img" alt="">
                                </a>
                            </li>
                        </ul>
                    </div>
                </section>
                <h1 class="title">
                    <img src="../assets/img/index-h1-huodong.png" alt="">
                </h1>
                <section class="sec-hd">
                    <ul>
                        <li>
                            <a href="miaosha.html" target="_blank">
                                <img src="../assets/img/index-hd-1.png" alt="">
                            </a>
                        </li>
                        <li>
                            <a href="chaopianyi.html" target="_blank">
                                <img src="../assets/img/index-hd-2.png" alt="">
                            </a>
                        </li>
                        <li>
                            <a href="baokuan.html" target="_blank">
                                <img src="../assets/img/index-hd-3.png" alt="">
                            </a>
                        </li>
                        <li>
                            <a href="yushou.html" target="_blank">
                                <img src="../assets/img/index-hd-4.png" alt="">
                            </a>
                        </li>
                        <li>
                            <a href="https://www.qiang100.com/zhi/youhuiquan/" target="_blank">
                                <img src="../assets/img/index-hd-5.png" alt="">
                            </a>
                        </li>
                        <li>
                            <a href="https://www.qiang100.com/pinpai/" target="_blank">
                                <img src="../assets/img/index-hd-6.png" alt="">
                            </a>
                        </li>
                        <li>
                            <a href="https://www.qiang100.com/zhi/" target="_blank">
                                <img src="../assets/img/index-hd-7.png" alt="">
                            </a>
                        </li>
                        <li>
                            <a href="https://www.qiang100.com/index.php?g=&m=Zhi&a=history" target="_blank">
                                <img src="../assets/img/index-hd-8.png" alt="">
                            </a>
                        </li>
                    </ul>
                </section>
                <h1 class="title">
                    <img src="../assets/img/index-h1-dianshang.png" alt="">
                </h1>
                <!-- 电商大促 -->
                <seciton class="sec-ds">
                    <ul>
                        <li>
                            <a target="_blank" href="https://union-click.jd.com/jdc?e=0&p=AyIHUytaJQMiQwpDBUoyS0IQWhkeHAxFBUYPCllHGAdFBwtSQEJLcitMV1pFIEVedB1LQglGa1YHWmUebR1VYVYAVwUzUF9PAgllM2UOHmlWGlscHhMDSRhfBAIXDFEbUBQDIgJdGVgUChMGVitbFAMTBlIbXxcKIjdVGmtebBM3UhxTEgQRBFceaxUGEQFWGVsUBRMCURhrEjISBVEaXxICGwdVGDVUMiI3ZStrFzIS&t=W1dCFFlQCxxQVwhPRE5XDVULR0VFUFcZPGsCQEpQcgseOgpbV1sI">
                                <img src="../assets/img/index-ds-1.png" alt="">
                            </a>
                            <p>好货低至6.18</p>
                        </li>
                        <li>
                            <a href="https://sugs.suning.com/u2zDI1ht" target="_blank">
                                <img src="../assets/img/index-ds-2.png" alt="">
                            </a>
                            <p>全品聚惠 不止五折</p>
                        </li>
                        <li>
                            <a href="https://prom.gome.com.cn/html/prodhtml/topics/201805/15/618gonglue.html" target="_blank">
                                <img src="../assets/img/index-ds-3.png" alt="">
                            </a>
                            <p>全民疯抢48小时</p>
                        </li>
                        <li>
                            <a href="##">
                                <img src="../assets/img/index-ds-4.png" alt="">
                            </a>
                            <p>海外购物,全球抢货</p>
                        </li>
                        <li>
                            <a href="http://sale.yhd.com/act/uAUxPqGcz3X.html" target="_blank">
                                <img src="../assets/img/index-ds-5.png" alt="">
                            </a>
                            <p>顶级盛典 满99减50</p>
                        </li>
                    </ul>
                </seciton>
                <!-- 秒杀汇总 -->
                <h1 class="title">
                    <img src="../assets/img/index-h1-miaoshao.png" alt="">
                    <a href="/miaosha" target="_blank">
                        <img src="../assets/img/index-h1-more.png" alt="">
                    </a>
                </h1>
                <section class="sec-list sec-ms" id="index-ms">
                    <ul>
                        <li v-for=" item in msList" :key="item">
                            <a :href="item.pcurl" target="_blank">
                                <div class="sec-img">
                                    <img :src="item.picpc" alt="">
                                </div>
                                <p class="p1">{{item.title}}</p>
                                <p>秒杀价: <span>{{item.price}}</span></p>
                                <p class="p3" v-if="item.isstart">正在疯狂秒杀中</p>
                                <p class="p3" v-else>{{item.onlinestarttime2}}开抢</p>
                                <p>
                                    <span>提前秒杀 到店抢购</span>
                                </p>
                            </a>
                        </li>
                    </ul>
                </section>
                <!-- 便宜货 -->
                <h1 class="title">
                    <img src="../assets/img/index-h1-pianyi.png" alt="">
                    <a href="/pianyi" target="_blank"><img src="../assets/img/index-h1-more.png" alt=""></a>
                </h1>
                <section class="sec-list sec-py" id="index-py">
                    <ul>
                        <li v-for="item in pyList" :key="item">
                            <a :href="item.sourceUrlForOrder" target="_blank">
                                <div class="sec-img">
                                    <img :src="item.logo" alt="">
                                </div>
                                <p class="p1">{{item.name}}</p>
                                <p>
                                    <span>{{item.price}}</span>
                                </p>
                                <p class="p3"><em v-show="item.sales != 0" style="font-style: normal">已有{{item.sales}}抢购</em></p>
                                <p>
                                    <span>前往抢购</span>
                                </p>
                            </a>
                        </li>
                    </ul>
                </section>
                <!-- 爆款清单 -->
                <h1 class="title">
                    <img src="../assets/img/index-h1-baokuan.png" alt="">
                    <a href="/baokuan" target="_blank">
                        <img src="../assets/img/index-h1-more.png" alt="">
                    </a>
                </h1>
                <section class="sec-baokuan" id="index-bk">
                    <ul>
                        <li v-for="(item,index) in bkList" :key="index">
                            <a :href="item.sourceUrlForOrder" target="_balnk" onclick="check_cps(this);" isconvert="1">
                                <div class="sec-img">
                                    <img :src="item.logo" alt="">
                                    <div class="sec-num" v-show="item.sales != 0">
                                        已有{{item.sales}}人抢购
                                    </div>
                                </div>
                                <p class="p1">{{item.name}}</p>
                                <p class="p2">
                                    <span>{{item.price}}</span>
                                    <em v-show="item.couponValue" style="font-style:normal">券后价</em>
                                </p>
                                <p id="plast">
                                    <em v-show="item.couponValue" style="font-style: normal">
                                                <a :href="item.couponUrl" target="_blank" onclick="check_cps(this);"  isconvert="1">
                                                    <span>
                                                        领{{item.couponValue}}元券
                                                    </span>
                                                </a>
                                            </em>
                                    <a :href="item.sourceUrlForOrder" target="_blank" onclick="check_cps(this);" isconvert="1">
                                        <span class="bk-button" :class="{ bkquan : !item.couponValue }">前往抢购</span>
                                    </a>
                                </p>
                            </a>
                        </li>
                    </ul>
                </section>
                <!-- 预售好价 -->
                <h1 class="title">
                    <img src="../assets/img/index-h1-yushou.png" alt="">
                    <a href="/yushou" target="_blank">
                        <img src="../assets/img/index-h1-more.png" alt="">
                    </a>
                </h1>
                <section class="sec-yushou " id="index-ys">
                    <ul>
                        <li v-for="(item,index) in ysList" :key="index">
                            <a :href="item.sourceUrlForOrder" target="_blank" onclick="check_cps(this);" isconvert="1">
                                <div class="sec-img">
                                    <img :src="item.logo" alt="">
                                </div>
                                <p class="p1">{{item.name}}</p>
                                <p class="p2">
                                    <span>{{item.price}}</span>
                                </p>
                                <p class="p3"><em v-show="0" style="font-style: normal"> 预定立减{{item.discount}}元</em></p>
                                <p class="p-yushou">
                                    <em v-show="item.couponValue" style="font-style: normal">
                                        <a :href="item.couponUrl" target="_blank" onclick="check_cps(this);"  isconvert="1">
                                            <span>领{{item.couponValue}}元券</span>
                                        </a>
                                    </em>
                                    <a :href="item.sourceUrlForOrder" target="_blank" onclick="check_cps(this);" isconvert="1">
                                        <span class="ys-button" :class="{ ysquan : !item.couponValue }">前往预订</span>
                                    </a>
                                </p>
                            </a>
                        </li>
                    </ul>
                </section>
            </div>
        </div>
        <foot-component></foot-component>
    </section>
</template>

<script>
    import FootComponent from '../components/FootComponent.vue';
    export default {
        data() {
            return {
                huicangBigList: [{
                        'img': 'img/index-hc-1.png',
                        'url': 'https://s.click.taobao.com/3Yt8RQw'
                    }, //天猫主会场
                    {
                        'img': 'img/index-hc-2.png',
                        'url': 'https://s.click.taobao.com/Cq68RQw'
                    }, //聚划算主会场
                ],
                huicangSmallList: [{
                        'img': 'img/index-hc-3.png',
                        'url': 'https://s.click.taobao.com/LEf5IQw'
                    }, //气质服饰
                    {
                        'img': 'img/index-hc-4.png',
                        'url': 'https://s.click.taobao.com/dTh5IQw'
                    }, //大牌美妆
                    {
                        'img': 'img/index-hc-5.png',
                        'url': 'https://s.click.taobao.com/xzS7RQw'
                    }, //母婴会场
                    {
                        'img': 'img/index-hc-6.png',
                        'url': 'https://s.click.taobao.com/UaQ5IQw'
                    }, //食品会场
                    {
                        'img': 'img/index-hc-7.png',
                        'url': 'https://s.click.taobao.com/8795IQw'
                    }, //数码电器
                    {
                        'img': 'img/index-hc-8.png',
                        'url': 'https://s.click.taobao.com/F965IQw'
                    }, //家用家电
                    {
                        'img': 'img/index-hc-9.png',
                        'url': 'https://s.click.taobao.com/2cW6IQw'
                    }, //潮流箱包
                    {
                        'img': 'img/index-hc-10.png',
                        'url': 'https://s.click.taobao.com/UPf6IQw'
                    }, //运动户外
                    {
                        'img': 'img/index-hc-11.png',
                        'url': 'https://s.click.taobao.com/YLS6RQw'
                    }, //家具生活
                    {
                        'img': 'img/index-hc-12.png',
                        'url': 'https://s.click.taobao.com/NoZ6RQw'
                    }, //家装会场
                ],
                bkUrl: 'https://www.qiang100.com/HuodongApi/hd618/hd2018_bkqd',
                msUrl: 'https://www.qiang100.com/HuodongApi/hd618/hd2018_mshz',
                pyUrl: 'https://www.qiang100.com/HuodongApi/hd618/hd2018_cjpy',
                ysUrl: 'https://www.qiang100.com/HuodongApi/hd618/hd2018_yshj',
                page: 1,
                size: 10,
                category: "男装",
                msList: [],
                pyList: [],
                bkList: [],
                ysList: []
            }
        },
        components:{
            'FootComponent':FootComponent,
        },
        mounted() {
            this.getMiaosha();
            this.getPianyi();
            this.getBaokuan();
            this.getYushou();
        },
        methods: {
            loadPage: function(apiUrl, page, size, category, callback) {
                var _this = this;
                category = encodeURIComponent(category);
                $.ajax({
                    type: "GET",
                    url: apiUrl + "?page=" + page +
                        "&size=" + size + "&catagory=" + category,
                    dataType: "json",
                    success: function(res) {
                        if (res.code = 100) {
                            callback(res);
                        }
                    }
                });
            },
            getMiaosha: function() {
                var _this = this;
                this.loadPage(this.msUrl, this.page, this.size, this.category, function(res) {
                    _this.msList = res.data.productList;
                })
            },
            getPianyi: function() {
                var _this = this;
                this.loadPage(this.pyUrl, this.page, this.size, this.category, function(res) {
                    _this.pyList = res.data.productList;
                })
            },
            getBaokuan: function() {
                var _this = this;
                this.loadPage(this.bkUrl, this.page, this.size, this.category, function(res) {
                    _this.bkList = res.data.productList;
                })
            },
            getYushou: function() {
                var _this = this;
                this.loadPage(this.ysUrl, this.page, this.size, this.category, function(res) {
                    _this.ysList = res.data.productList;
                })
            }
        }
    }
</script>


<style lang="less">
    @import url('../assets/css/public.less');
    @import url('../assets/css/style.less');
</style>
