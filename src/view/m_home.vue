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
                    <p class="title">vue移动端h5页面根据屏幕适配的四种方案</p>
                    <p class="intro">最近做了两个关于h5页面对接公众号的项目，不得不提打开微信浏览器内置地图导航的功能确实有点恶心。下次想起来了的话，进行总结分享一下如何处理。在vue移动端h5页面当中，其中适配是经常会遇到的问题，这块主要有死个方法可以适用。</p>
                </li>
                <li>
                    <p class="title">
                        <router-link :to ="{path:'/detail',query:{index:'vue-3',title:'vue创建项目并且上传到git中的步骤'}}">vue创建项目并且上传到git中的步骤</router-link>
                    </p>
                    <p class="intro">创建vue项目步骤，将vue项目上传至git中的步骤</p>
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
                        <router-link :to ="{path:'/detail',query:{index:'m-1',title:'轮播',url:'http://dlhls.cdn.zhanqi.tv/zqlive/35349_iXsXw.m3u8'}}">《轮播》</router-link>
                    </p>
                </li>
                <li>
                    <p class="title">
                        <router-link :to ="{path:'/detail',query:{index:'m-1',title:'动作电影',url:'http://183.207.249.15/PLTV/3/224/3221225529/index.m3u8'}}">动作电影</router-link>
                    </p>
                </li>
                <li>
                    <p class="title">
                        <router-link :to ="{path:'/detail',query:{index:'m-1',title:'科幻电影',url:'http://aldirect.hls.huya.com/huyalive/28466698-2689656864-11551988268341919744-2847699194-10057-A-0-1_1200.m3u8'}}">科幻电影</router-link>
                    </p>
                </li>
                <li>
                    <p class="title">
                        <router-link :to ="{path:'/detail',query:{index:'m-1',title:'速度与激情',url:'http://aldirect.hls.huya.com/huyalive/29169025-2686219962-11537226886652362752-2710080226-10057-A-0-1_1200.m3u8'}}">速度与激情</router-link>
                    </p>
                </li>
                <li>
                    <p class="title">
                        <router-link :to ="{path:'/detail',query:{index:'m-1',title:'赌博电影',url:'http://js.hls.huya.com/huyalive/29106097-2689446042-11551082794746642432-2789253870-10057-A-0-1_1200.m3u8'}}">赌博电影</router-link>
                    </p>
                </li>
                <li>
                    <p class="title">
                        <router-link :to ="{path:'/detail',query:{index:'m-1',title:'赌神全集新木乃伊',url:'http://aldirect.hls.huya.com/huyalive/29169025-2686220018-11537227127170531328-2847699120-10057-A-1524041208-1_1200.m3u8'}}">赌神全集新木乃伊</router-link>
                    </p>
                </li>
                <li>
                    <p class="title">
                        <router-link :to ="{path:'/detail',query:{index:'m-1',title:'王晶导演',url:'https://aldirect.hls.huya.com/huyalive/94525224-2579683592-11079656661667807232-2847687574-10057-A-0-1_1200.m3u8'}}">王晶导演</router-link>
                    </p>
                </li>
                <li>
                    <p class="title">
                        <router-link :to ="{path:'/detail',query:{index:'m-1',title:'徐克导演',url:'http://tx.hls.huya.com/huyalive/29106097-2689447148-11551087544980471808-2789253872-10057-A-1525420294-1.m3u8'}}">徐克导演</router-link>
                    </p>
                </li>
                <li>
                    <p class="title">
                        <router-link :to ="{path:'/detail',query:{index:'m-1',title:'黄渤',url:'https://aldirect.hls.huya.com/huyalive/30765679-2554414680-10971127511022305280-3048991634-10057-A-0-1_1200.m3u8'}}">黄渤</router-link>
                    </p>
                </li>
                <li>
                    <p class="title">
                        <router-link :to ="{path:'/detail',query:{index:'m-1',title:'徐峥',url:'https://aldirect.hls.huya.com/huyalive/29106097-2689278568-11550363499393712128-2710090468-10057-A-0-1_1200.m3u8'}}">徐峥</router-link>
                    </p>
                </li>
                <li>
                    <p class="title">
                        <router-link :to ="{path:'/detail',query:{index:'m-1',title:'斯坦森',url:'http://tx.hls.huya.com/huyalive/30765679-2554414705-10971127618396487680-3048991636-10057-A-0-1.m3u8'}}">斯坦森</router-link>
                    </p>
                </li>
                <li>
                    <p class="title">
                        <router-link :to ="{path:'/detail',query:{index:'m-1',title:'黄百鸣',url:'http://ws4.streamhls.huya.com/huyalive/29169025-2686220062-11537227316149092352-2777037828-10057-A-1524041857-1_1200/playlist.m3u8'}}">黄百鸣</router-link>
                    </p>
                </li>
                <li>
                    <p class="title">
                        <router-link :to ="{path:'/detail',query:{index:'m-1',title:'陈小春',url:'http://ws4.streamhls.huya.com/huyalive/30765679-2523417522-10837995731143360512-2777068634-10057-A-0-1_1200/playlist.m3u8'}}">陈小春</router-link>
                    </p>
                </li>
                <li>
                    <p class="title">
                        <router-link :to ="{path:'/detail',query:{index:'m-1',title:'黄日华',url:'http://ws4.streamhls.huya.com/huyalive/30765679-2523417506-10837995662423883776-2777071322-10057-A-0-1_1200/playlist.m3u8'}}">黄日华</router-link>
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
                        <router-link :to ="{path:'/detail',query:{index:'m-1',title:'刘德华',url:'http://aldirect.hls.huya.com/huyalive/94525224-2467341872-10597152648291418112-2789274550-10057-A-0-1_1200.m3u8'}}">刘德华</router-link>
                    </p>
                </li>
                <li>
                    <p class="title">
                        <router-link :to ="{path:'/detail',query:{index:'m-1',title:'成龙',url:'http://aldirect.hls.huya.com/huyalive/94525224-2460685722-10568564701724147712-2789253838-10057-A-0-1_1200.m3u8'}}">成龙</router-link>
                    </p>
                </li>
                <li>
                    <p class="title">
                        <router-link :to ="{path:'/detail',query:{index:'m-1',title:'周星驰',url:'http://aldirect.hls.huya.com/huyalive/94525224-2460685313-10568562945082523648-2789274524-10057-A-0-1_1200.m3u8'}}">周星驰</router-link>
                    </p>
                </li>
                <li>
                    <p class="title">
                        <router-link :to ="{path:'/detail',query:{index:'m-1',title:'林正英',url:'http://js.hls.huya.com/huyalive/94525224-2460686034-10568566041753944064-2789274542-10057-A-0-1_1200.m3u8'}}">林正英</router-link>
                    </p>
                </li>
                <li>
                    <p class="title">
                        <router-link :to ="{path:'/detail',query:{index:'m-1',title:'CCTV-1综合',url:'http://223.110.242.130:6610/gitv/live1/G_CCTV-1-HQ/1.m3u8'}}">CCTV-1综合</router-link>
                    </p>
                </li>
                <li>
                    <p class="title">
                        <router-link :to ="{path:'/detail',query:{index:'m-1',title:'湖南卫视高清',url:'http://112.50.243.8/PLTV/88888888/224/3221225827/1.m3u8'}}">湖南卫视高清</router-link>
                    </p>
                </li>
                <li>
                    <p class="title">
                        <router-link :to ="{path:'/detail',query:{index:'m-1',title:'江苏卫视高清',url:'http://112.50.243.8/PLTV/88888888/224/3221225847/1.m3u8'}}">江苏卫视高清</router-link>
                    </p>
                </li>
                <li>
                    <p class="title">
                        <router-link :to ="{path:'/detail',query:{index:'m-1',title:'东方卫视高清',url:'http://112.50.243.8/PLTV/88888888/224/3221225828/1.m3u8'}}">东方卫视高清</router-link>
                    </p>
                </li>
                <li>
                    <p class="title">
                        <router-link :to ="{path:'/detail',query:{index:'m-1',title:'北京卫视高清',url:'http://112.50.243.8/PLTV/88888888/224/3221225826/1.m3u8'}}">北京卫视高清</router-link>
                    </p>
                </li>
                <li>
                    <p class="title">
                        <router-link :to ="{path:'/detail',query:{index:'m-1',title:'Newtv动作电影',url:'http://183.207.249.15/PLTV/3/224/3221225529/index.m3u8'}}">Newtv动作电影</router-link>
                    </p>
                </li>
                <li>
                    <p class="title">
                        <router-link :to ="{path:'/detail',query:{index:'m-1',title:'Newtv惊悚悬疑',url:'http://183.207.249.7/PLTV/3/224/3221225561/index.m3u8'}}">Newtv惊悚悬疑</router-link>
                    </p>
                </li>
                <li>
                    <p class="title">
                        <router-link :to ="{path:'/detail',query:{index:'m-1',title:'Newtv精品电影',url:'http://183.207.249.14/PLTV/3/224/3221225567/index.m3u8'}}">Newtv精品电影</router-link>
                    </p>
                </li>
                <li>
                    <p class="title">
                        <router-link :to ="{path:'/detail',query:{index:'m-1',title:'Newtv明星大片',url:'http://183.207.249.14/PLTV/3/224/3221225535/index.m3u8'}}">Newtv明星大片</router-link>
                    </p>
                </li>
                <li>
                    <p class="title">
                        <router-link :to ="{path:'/detail',query:{index:'m-1',title:'Newtv家庭剧场',url:'http://183.207.249.14/PLTV/3/224/3221225549/index.m3u8'}}">Newtv家庭剧场</router-link>
                    </p>
                </li>
                <li>
                    <p class="title">
                        <router-link :to ="{path:'/detail',query:{index:'m-1',title:'Newtv精品大剧',url:'http://183.207.249.14/PLTV/3/224/3221225569/index.m3u8'}}">Newtv精品大剧</router-link>
                    </p>
                </li>
                <li>
                    <p class="title">
                        <router-link :to ="{path:'/detail',query:{index:'m-1',title:'Newtv金牌综艺',url:'http://183.207.249.16/PLTV/3/224/3221225559/index.m3u8'}}">Newtv金牌综艺</router-link>
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
.list-con {background: #ffffff;margin-top: .2rem;box-sizing: border-box;padding: .3rem;}
.list-con li {padding: .3rem 0;border-bottom: 1px solid #eeeeee;}
.list-con li:last-child {margin-bottom: 0;border-bottom: 0;}
.list-con li p.title {font-size: .3rem;font-weight: bold;color: #333333;margin-bottom: .1rem;cursor: pointer;}
.list-con li p.title:hover {color: #d72b00;}
.list-con li p.intro {font-size: .28rem;color: #666666;font-weight: 400;line-height: .48rem;}
.w1000 {width: 100%}
</style>
