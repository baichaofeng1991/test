<template>
    <div>
        <my-head :index = 'num' @transmit = 'transmitData'></my-head>

        <div class="list-con w1200" v-if="receive == 1">
            <ul>
                <li>
                    <p class="title"><router-link to='/detail'>Vue面试知识点总结</router-link></p>
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
        <div class="list-con w1200" v-if="receive == 2">
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
        <div class="list-con w1200" v-if="receive == 5">
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
.list-con li p.title {font-size: .28rem;font-weight: bold;color: #333333;margin-bottom: .1rem;cursor: pointer;}
.list-con li p.title:hover {color: #d72b00;}
.list-con li p.intro {font-size: .28rem;color: #666666;font-weight: 400;line-height: .48rem;}
.w1200 {width: 100%}
</style>
