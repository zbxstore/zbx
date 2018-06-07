<template>
    <section id="yushou">
        <a href="##" target="_blank" onclick="check_cps(this);" isconvert="1">
            <div class="yushou-banner">
            </div>
        </a>
        <div class="tab-link tab-yushou">
            <div class="content">
                <ul>
                    <li class="active" @click="toggleCategory('爆款预售')">爆款预售</li>
                    <li @click="toggleCategory('服装鞋包')">服装鞋包</li>
                    <li @click="toggleCategory('美妆护肤')">美妆护肤</li>
                    <li @click="toggleCategory('数码家电')">数码家电</li>
                    <li @click="toggleCategory('母婴儿童')">母婴儿童</li>
                    <li @click="toggleCategory('生活百货')">生活百货</li>
                    <li @click="toggleCategory('美食吃货')">美食吃货</li>
                    <li @click="toggleCategory('家居建材')">家居建材</li>
                </ul>
            </div>
        </div>
        <div class="yushou-content">
            <div class="content">
                <section class="sec-yushou">
                    <ul>
                        <li v-for="(item,index) in productList" :key="index">
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
        <div class="loading" v-show="busy">
            <img src="../assets/img/loading.svg" alt="">
        </div>
    </section>
</template>

<script>

    export default {
        data() {
            return {
                apiUrl: 'https://www.qiang100.com/HuodongApi/hd618/hd2018_yshj',
                productList: [],
                page: 2,
                size: 30,
                category: "爆款预售",
                busy: false,
            }
        },
        mounted: function() {
            this.toggleCategory(this.category);
            this.activeToggle();
        },
        methods: {
            activeToggle: function() {
                $('.tab-yushou ul li').on('click', function(event) {
                    $(this).addClass('active').siblings().removeClass('active');
                });
            },
            toggleCategory: function(setCategory) {
                var _this = this;
                this.category = setCategory;
                this.loadPage(this.apiUrl, 1, this.size, this.category, function(res) {
                    _this.productList = res.data.productList;
                });
                this.page = 2;
                this.loadMore();
                this.$forceUpdate();
                console.log(this.category)
            },
            loadPage: function(apiUrl, page, size, category, callback) {
                var _this = this;
                category = encodeURIComponent(category);
                $.ajax({
                    type: "GET",
                    url: apiUrl + "?page=" + page + "&size=" + size + "&category=" + category,
                    dataType: "json",
                    success: function(res) {
                        if (res.code = 100) {
                            callback(res);
                        }
                    }
                });
            },
            loadMore: function() {
                var _this = this;
                $(window).scroll(function() {　　
                    var scrollTop = $(this).scrollTop();　　
                    var scrollHeight = $(document).height();　　
                    var windowHeight = $(this).height();　　
                    if (scrollTop + windowHeight >= scrollHeight - 50) {
                        console.log('到底了')
                        if (!_this.busy) {
                            _this.busy = true;
                            setTimeout(function() {
                                _this.loadPage(_this.apiUrl, _this.page, _this.size, _this.category, function(res) {
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
    @import url("../assets/css/public.less");
    @import url("../assets/css/style.less");
</style>
