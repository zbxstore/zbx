<template>
    <secion id="miaosha">
        <a href="##" target="_blank">
            <div class="miaosha-banner">
                <div class="content">
                    <!--             <div class="miaosha-time">
                            <p>距6月01日0点开抢还有</p>
                            <p><span>{{times.d}}</span><em class="em-1">天</em><span>{{times.h}}</span><em>:</em><span>{{times.m}}</span><em>:</em><span>{{times.s}}</span></p>
                        </div> -->
                </div>
            </div>
        </a>
        <div class="miaosha-content">
            <div class="content">
                <section class="sec-list sec-ms">
                    <ul>
                        <li v-for=" (item,index) in productList" :key="index">
                            <a :href="item.pcurl" target="_blank" onclick="check_cps(this);" isconvert="1">
                                <div class="sec-img">
                                    <img :src="item.picpc" alt="">
                                </div>
                                <p class="p1">{{item.title}}</p>
                                <p>秒杀价:
                                    <span>{{item.price}}</span>
                                </p>
                                <p class="p3" v-if="item.isstart">正在疯狂秒杀中</p>
                                <p class="p3" v-else>{{item.onlinestarttime2}}开抢</p>
                                <p>
                                    <span>提前加购，到点秒杀</span>
                                </p>
                            </a>
                        </li>
                    </ul>
                </section>
            </div>
        </div>
<!--         <div class="loading" v-show="busy">
            <img src="..assets/img/loading.svg" alt="">
        </div> -->
    </secion>
</template>

<script>

    export default {
        data() {
            return {
                times: {
                    'd': 0,
                    'h': 0,
                    'm': 0,
                    's': 0
                },
                apiUrl: 'https://www.qiang100.com/HuodongApi/hd618/hd2018_mshz',
                productList: [],
                page: 2,
                size: 30,
                category: "",
                busy: false,
            }
        },
        mounted: function() {
            //this.daojishi();
            this.defaultLoad();
            this.loadMore();
        },
        methods: {
            //倒计时
            daojishi() {
                var vm = this;
                var time_end = new Date("2018/6/01 00:00:00"); // 设定结束时间
                time_end = time_end.getTime();
                var jishi = setInterval(function() {
                    var time_now = new Date(); // 获取当前时间
                    time_now = time_now.getTime();
                    var time_distance = time_end - time_now; // 结束时间减去当前时间
                    var int_day, int_hour, int_minute, int_second;
                    if (time_distance >= 0) {
                        // 天时分秒换算
                        int_day = Math.floor(time_distance / 86400000)
                        time_distance -= int_day * 86400000;
                        int_hour = Math.floor(time_distance / 3600000)
                        time_distance -= int_hour * 3600000;
                        int_minute = Math.floor(time_distance / 60000)
                        time_distance -= int_minute * 60000;
                        int_second = Math.floor(time_distance / 1000)
                        // 时分秒为单数时、前面加零站位
                        if (int_hour < 10)
                            int_hour = "0" + int_hour;
                        if (int_minute < 10)
                            int_minute = "0" + int_minute;
                        if (int_second < 10)
                            int_second = "0" + int_second;
                        // 显示时间
                        vm.times = {
                            'd': int_day,
                            'h': int_hour,
                            'm': int_minute,
                            's': int_second
                        };
                    } else {
                        clearInterval(jishi); //停止
                    }
                }, 1000);
            },
            loadPage(apiUrl, page, size, category, callback) {
                var _this = this;
                category = encodeURIComponent(category);
                $.ajax({
                    type: "GET",
                    url: apiUrl + "?page=" + page + "&size=" + size + "&catagory=" + category,
                    dataType: "json",
                    success: function(res) {
                        if (res.code = 100) {
                            callback(res);
                        }
                    }
                });
            },
            defaultLoad() {
                var _this = this;
                this.loadPage(this.apiUrl, 1, this.size, this.category, function(res) {
                    _this.productList = res.data.productList
                })
            },
            loadMore() {
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
                                _this.loadPage(_this.apiUrl, _this.page, _this.size, _this.category,
                                    function(res) {
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


<style lang="less" >
    @import url('../assets/css/public.less');
    @import url('../assets/css/style.less');
</style>

