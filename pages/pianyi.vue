<template>
    <section id="pianyi">
        <a href="##" target="_blank" onclick="check_cps(this);" isconvert="1">
            <div class="pianyi-banner">
            </div>
        </a>
        <div class="tab-link">
            <div class="content">
                <ul>
                    <li class="active" @click="toggleCategory('0')">精选</li>
                    <li @click="toggleCategory('1')">1-3元</li>
                    <li @click="toggleCategory('2')">4-5元</li>
                    <li @click="toggleCategory('3')">6-8元</li>
                    <li @click="toggleCategory('4')">9-10元</li>
                </ul>
            </div>
        </div>
        <div class="pianyi-content">
            <div class="content">
                <section class="sec-list sec-py">
                    <ul>
                        <li v-for="(item,index) in productList" :key="index">
                            <a :href="item.sourceUrlForOrder" target="_blank" onclick="check_cps(this);" isconvert="1">
                                <div class="sec-img">
                                    <img :src="item.logo" alt="">
                                </div>
                                <p class="p1">{{item.name}}</p>
                                <p>
                                    <span>{{item.price}}</span>
                                </p>
                                <p class="p3"> <em v-show="item.sales != 0" style="font-style: normal">已有{{item.sales}}抢购</em></p>
                                <p>
                                    <span>前往抢购</span>
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
            return{
                apiUrl: "https://www.qiang100.com/HuodongApi/hd618/hd2018_cjpy",
                productList: [],
                page: 2,
                size: 30,
                category: 0,
                busy: false
            }
        },
        mounted: function() {
            this.toggleCategory(this.category);
            this.activeToggle();
        },
        methods: {
            activeToggle: function() {
                $(".tab-link ul li").on("click", function(event) {
                    $(this)
                        .addClass("active")
                        .siblings()
                        .removeClass("active");
                });
            },
            toggleCategory: function(setCategory) {
                var _this = this;
                this.category = setCategory;
                this.page = 2;
                this.loadPage(this.apiUrl, 1, this.size, this.category, function(res) {
                    _this.productList = res.data.productList;
                });
                this.loadMore();
                this.$forceUpdate();
            },
            loadPage: function(apiUrl, page, size, category, callback) {
                var _this = this;
                category = encodeURIComponent(category);
                $.ajax({
                    type: "GET",
                    url: apiUrl + "?page=" + page + "&size=" + size + "&price=" + category,
                    dataType: "json",
                    success: function(res) {
                        if ((res.code = 100)) {
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
                        console.log("到底了");
                        if (!_this.busy) {
                            _this.busy = true;
                            setTimeout(function() {
                                _this.loadPage(
                                    _this.apiUrl,
                                    _this.page,
                                    _this.size,
                                    _this.category,
                                    function(res) {
                                        for (var i = 0; i < res.data.productList.length; i++) {
                                            _this.productList.push(res.data.productList[i]);
                                        }
                                    }
                                );
                                _this.page++;
                                _this.busy = false;
                            }, 100);
                        }
                    }
                });
            }
        }
    };
</script>


<style lang="less">
    @import url("../assets/css/public.less");
    @import url("../assets/css/style.less");
</style>
