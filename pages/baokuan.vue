<template>
    <section id="baokuan">
    <a href="##" target="_blank" onclick="check_cps(this);" isconvert="1">
        <div class="baokuan-banner">

        </div>
    </a>
    <div class="baokuan-content">
        <div class="content">
            <!-- 爆款清单 -->
            <section class="sec-baokuan">
                <ul>
                    <li v-for="(item,index) in productList" :key="index">
                            <a :href="item.sourceUrlForOrder" target="_balnk" onclick="check_cps(this);"  isconvert="1">
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
                                    <a :href="item.sourceUrlForOrder" target="_blank" onclick="check_cps(this);"  isconvert="1">
                                        <span class="bk-button" :class="{ bkquan : !item.couponValue }">前往抢购</span>
                                    </a>
                                </p>
                           </a>
                    </li>

                </ul>
            </section>
            <div class="loading" v-show="busy">
                <img src="../assets/img/loading.svg" alt="">
            </div>
        </div>
    </div>
</section>
</template>
<script>
export default {
        data() {
            return{
                apiUrl:'https://www.qiang100.com/HuodongApi/hd618/hd2018_bkqd',
                productList: [],
                page: 2,
                size: 30,
                category: "",
                busy: false,
            }
        },
        mounted: function () {
            this.defaultLoad();
            this.loadMore();
        },
        methods: {
           loadPage: function (apiUrl,page, size, category, callback) {
                var _this = this;
                category = encodeURIComponent(category);
                $.ajax({
                    type: "GET",
                    url: apiUrl + "?page=" + page + "&size=" + size + "&catagory=" + category + "&lastTime=",
                    dataType: "json",
                    success: function (res) {
                        if(res.code = 100){
                            callback(res);
                        }
                    }
                });
            },

            defaultLoad: function () {
                var _this = this;
                this.loadPage(this.apiUrl,1, this.size, this.category, function (res) {
                    _this.productList = res.data.productList
                })

            },

            loadMore: function () {
                var _this = this;
                $(window).scroll(function () {　　
                    var scrollTop = $(this).scrollTop();　　
                    var scrollHeight = $(document).height();　　
                    var windowHeight = $(this).height();　　
                    if (scrollTop + windowHeight >= scrollHeight - 50) {
                        console.log('到底了')

                        if (!_this.busy) {
                            _this.busy = true;
                            setTimeout(function () {

                                _this.loadPage(_this.apiUrl,_this.page, _this.size, _this.category,
                                    function (res) {
                                        for (var i = 0; i < res.data.productList.length; i++) {
                                            _this.productList.push(res.data.productList[i]);
                                        }
                                    })

                                _this.page++;
                                _this.busy = false;
                            }, 100);
                        }

                        　　
                    }
                });

            }
        }

}
</script>


<style lang="less">
    @import url('../assets/css/public.less');
    @import url('../assets/css/style.less');
</style>

