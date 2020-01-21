<template>
    <div>
        <my-head :index = 'num' @transmit = 'transmitData'></my-head>

        <div class="list-con w1000" v-if="receive == 1">
            <ul>
                <li>
                    <p class="title">
                        <router-link :to ="{path:'/detail',query:{index:'vue-1',title:'Vue面试知识点总结'}}">Vue面试知识点总结</router-link>
                    </p>
                    <p class="intro">看看面试题，只是为了查漏补缺，看看自己那些方面还不懂。切记不要以为背了面试题，就万事大吉了，最好是理解背后的原理，这样面试的时候才能侃侃而谈。不然，稍微有水平的面试官一看就能看出，是否有真才实学还是刚好背中了这道面试题。</p>
                </li>
                <li>
                    <p class="title">
                        <router-link :to ="{path:'/detail',query:{index:'vue-2',title:'vue中使用axios'}}">vue中使用axios</router-link>
                    </p>
                    <p class="intro">...........</p>
                </li>
                <li>
                    <p class="title">
                        <router-link :to ="{path:'/detail',query:{index:'vue-3',title:'vue创建项目并且上传到git中的步骤'}}">vue创建项目并且上传到git中的步骤</router-link>
                    </p>
                    <p class="intro">创建vue项目步骤，将vue项目上传至git中的步骤</p>
                </li>
                <li>
                    <p class="title">
                        <router-link :to ="{path:'/detail',query:{index:'vue-4',title:'vue中使用vue-video-player'}}">vue中使用vue-video-player</router-link>
                    </p>
                    <p class="intro">。。。。。。。。</p>
                </li>
            </ul>
        </div>
        <div class="list-con w1000" v-if="receive == 2">
            <ul>
                <li>
                    <p class="title"><router-link to='/detail'>JQ</router-link></p>
                    <p class="intro">看看面试题，只是为了查漏补缺，看看自己那些方面还不懂。切记不要以为背了面试题，就万事大吉了，最好是理解背后的原理，这样面试的时候才能侃侃而谈。不然，稍微有水平的面试官一看就能看出，是否有真才实学还是刚好背中了这道面试题。</p>
                </li>
                <li>
                    <p class="title">vue移动端h5页面根据屏幕适配的四种方案</p>
                    <p class="intro">最近做了两个关于h5页面对接公众号的项目，不得不提打开微信浏览器内置地图导航的功能确实有点恶心。下次想起来了的话，进行总结分享一下如何处理。在vue移动端h5页面当中，其中适配是经常会遇到的问题，这块主要有死个方法可以适用。</p>
                </li>
                <li>
                    <p class="title">Vue面试知识点总结</p>
                    <p class="intro">看看面试题，只是为了查漏补缺，看看自己那些方面还不懂。切记不要以为背了面试题，就万事大吉了，最好是理解背后的原理，这样面试的时候才能侃侃而谈。不然，稍微有水平的面试官一看就能看出，是否有真才实学还是刚好背中了这道面试题。</p>
                </li>
            </ul>
        </div>
        <div class="list-con w1000" v-if="receive == 3">
            <ul>
                <li>
                    <p class="title">
                        <router-link :to ="{path:'/detail',query:{index:'js-1',title:'js 中的类'}}">js 中的类</router-link>
                    </p>
                    <p class="intro">............</p>
                </li>
            </ul>
        </div>

        <div class="list-con w1000" v-if="receive == 4">
            <ul>
                <li>
                    <p class="title">
                        <router-link :to ="{path:'/detail',query:{index:'wx-1',title:'使用Promise封装小程序wx.request'}}">使用Promise封装小程序wx.request</router-link>
                    </p>
                    <p class="intro">因为业务需要，每个http请求都要加上一个请求头，所以每次都要写很多重复的代码。现在尝试把wx.request简单的封装了一下，调用一个request方法，每次请求自动携带header头信息，这样就省事多了，包含了常见的get post put delete 四种请求方法，支持Promise方式调用。</p>
                </li>
            </ul>
        </div>

        <div class="list-con w1000" v-if="receive == 5">
            <ul>
                <li>
                    <p class="title">
                        <router-link :to ="{path:'/detail',query:{index:'ht-1',title:'前端中对象的分类'}}">前端中对象的分类</router-link>
                    </p>
                    <p class="intro">前端中包含的诸多对象，包括js对象、dom对象、HTML对象，及浏览器对象（Browser对象）</p>
                </li>
            </ul>
        </div>

        <div class="list-con w1000" v-if="receive == 6">
            <ul>
                <li>
                    <p class="title">
                        <router-link :to ="{path:'/detail',query:{index:'m-1',title:'毒液',url:'https://cdn.letv-cdn.com/2018/12/05/JOCeEEUuoteFrjCg/playlist.m3u8'}}">《毒液》</router-link>
                    </p>
                </li>
                <li>
                    <p class="title">
                        <router-link :to ="{path:'/detail',query:{index:'m-1',title:'斯坦森',url:'http://tx.hls.huya.com/huyalive/30765679-2554414705-10971127618396487680-3048991636-10057-A-0-1.m3u8'}}">斯坦森</router-link>
                    </p>
                </li>
                <li>
                    <p class="title">
                        <router-link :to ="{path:'/detail',query:{index:'m-1',title:'甄子丹',url:'http://ws4.streamhls.huya.com/huyalive/29169025-2686219938-11537226783573147648-2847699096-10057-A-1524024759-1_1200/playlist.m3u8'}}">甄子丹</router-link>
                    </p>
                </li>
                <li>
                    <p class="title">
                        <router-link :to ="{path:'/detail',query:{index:'m-1',title:'李连杰',url:'http://js.hls.huya.com/huyalive/94525224-2460686093-10568566295157014528-2789253848-10057-A-0-1_1200.m3u8'}}">李连杰</router-link>
                    </p>
                </li>
                <li>
                    <p class="title">
                        <router-link :to ="{path:'/detail',query:{index:'m-1',title:'高清电影',url:'http://aldirect.hls.huya.com/huyalive/29169025-2686219962-11537226886652362752-2710080226-10057-A-0-1_1200.m3u8'}}">高清电影</router-link>
                    </p>
                </li>
                <li>
                    <p class="title">
                        <router-link :to ="{path:'/detail',query:{index:'m-1',title:'怪物科幻',url:'http://tx.hls.huya.com/huyalive/30765679-2478268764-10644083292078342144-2847699106-10057-A-0-1.m3u8'}}">怪物科幻</router-link>
                    </p>
                </li>
                <li>
                    <p class="title">
                        <router-link :to ="{path:'/detail',query:{index:'m-1',title:'女神系列',url:'https://aldirect.hls.huya.com/huyalive/94525224-2472147404-10617792251071299584-2777026638-10057-A-0-1_1200.m3u8'}}">女神系列</router-link>
                    </p>
                </li>
                <li>
                    <p class="title">
                        <router-link :to ="{path:'/detail',query:{index:'m-1',title:'女神港片',url:'http://tx.hls.huya.com/huyalive/30765679-2484192476-10669525441389264896-2789274564-10057-A-0-1.m3u8'}}">女神港片</router-link>
                    </p>
                </li>
                <li>
                    <p class="title">
                        <router-link :to ="{path:'/detail',query:{index:'m-1',title:'漫威电影',url:'http://tx.hls.huya.com/huyalive/30765679-2504742278-10757786168918540288-3049003128-10057-A-0-1.m3u8'}}">漫威电影</router-link>
                    </p>
                </li>
                <li>
                    <p class="title">
                        <router-link :to ="{path:'/detail',query:{index:'m-1',title:'韩-GOODTV',url:'http://mobliestream.c3tv.com:554/live/goodtv.sdp/playlist.m3u8'}}">韩-GOODTV</router-link>
                    </p>
                </li>
                <li>
                    <p class="title">
                        <router-link :to ="{path:'/detail',query:{index:'m-1',title:'韩国高清1',url:'http://123.108.164.71/etv2sb/phd10062/playlist.m3u8'}}">韩国高清1</router-link>
                    </p>
                </li>
                <li>
                    <p class="title">
                        <router-link :to ="{path:'/detail',query:{index:'m-1',title:'韩国高清2',url:'http://123.108.164.110/etv1sb/phd10497/playlist.m3u8'}}">韩国高清2</router-link>
                    </p>
                </li>
                <li>
                    <p class="title">
                        <router-link :to ="{path:'/detail',query:{index:'m-1',title:'dddd',url:'rtmp://198.211.33.185/livepkgr/1C'}}">dddd</router-link>
                    </p>
                </li>
                <li>
                    <p class="title">
                        <router-link :to ="{path:'/detail',query:{index:'m-1',title:'',url:''}}"></router-link>
                    </p>
                </li>
            </ul>
        </div>

    </div>
</template>

<script>

import myHead from '../components/header';

export default {
    props: {

    },
    data() {
        return {
            num: 11,//父组件传递给子组件的数据
            receive: 1//子组件传递给父组件的数据
        };
    },
    computed: {

    },
    created() {

    },
    mounted() {

    },
    watch: {

    },
    methods: {
        //接收子组件中传递来的数据方法
        transmitData(data) {
            this.receive = data
        }

    },
    components: {
        myHead
    },
};
</script>

<style scoped>
.list-con {background: #ffffff;margin-top: 20px;box-sizing: border-box;padding: 30px 50px;}
.list-con li {padding: 30px 0;border-bottom: 1px solid #eeeeee;}
.list-con li:last-child {margin-bottom: 0;border-bottom: 0;}
.list-con li p.title {font-size: 20px;font-weight: bold;color: #333333;margin-bottom: 10px;cursor: pointer;}
.list-con li p.title:hover {color: #d72b00;}
.list-con li p.intro {font-size: 14px;color: #666666;font-weight: 400;line-height: 24px;}
</style>
