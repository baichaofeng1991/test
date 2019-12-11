<template>
    <div>
        <my-head></my-head>
        <div class="list-con w1200" v-if="index == 1">
            <div class="content">
                <div class="part">
                    <label>一、对于MVVM的理解</label>
                    <p>MVVM 是 Model-View-ViewModel 的缩写。</p>
                    <p><strong>Model</strong>代表数据模型，也可以在Model中定义数据修改和操作的业务逻辑。</p>
                    <p><strong>View</strong>代表UI 组件，它负责将数据模型转化成UI 展现出来。</p>
                    <p><strong>ViewModel</strong>监听模型数据的改变和控制视图行为、处理用户交互，简单理解就是一个同步View 和 Model的对象，连接Model和View。</p>
                    <p>在MVVM架构下，View 和 Model 之间并没有直接的联系，而是通过ViewModel进行交互，Model 和 ViewModel 之间的交互是双向的， 因此View 数据的变化会同步到Model中，而Model 数据的变化也会立即反应到View 上。</p>
                    <p><strong>ViewModel</strong>通过双向数据绑定把 View 层和 Model 层连接了起来，而View 和 Model 之间的同步工作完全是自动的，无需人为干涉，因此开发者只需关注业务逻辑，不需要手动操作DOM, 不需要关注数据状态的同步问题，复杂的数据状态维护完全由 MVVM 来统一管理。</p>
                </div>
                <div class="part">
                    <label>二、Vue的生命周期</label>
                    <p><strong>beforeCreate（创建前）</strong>在数据观测和初始化事件还未开始</p>
                    <p><strong>created（创建后）</strong>完成数据观测，属性和方法的运算，初始化事件，$el属性还没有显示出来</p>
                    <p><strong>beforeMount（载入前）</strong>在挂载开始之前被调用，相关的render函数首次被调用。实例已完成以下的配置：编译模板，把data里面的数据和模板生成html。注意此时还没有挂载html到页面上。</p>
                    <p><strong>mounted（载入后）</strong>在el 被新创建的 vm.$el 替换，并挂载到实例上去之后调用。实例已完成以下的配置：用上面编译好的html内容替换el属性指向的DOM对象。完成模板中的html渲染到html页面中。此过程中进行ajax交互。</p>
                    <p><strong>beforeUpdate（更新前）</strong>在数据更新之前调用，发生在虚拟DOM重新渲染和打补丁之前。可以在该钩子中进一步地更改状态，不会触发附加的重渲染过程。</p>
                    <p><strong>updated（更新后）</strong>在由于数据更改导致的虚拟DOM重新渲染和打补丁之后调用。调用时，组件DOM已经更新，所以可以执行依赖于DOM的操作。然而在大多数情况下，应该避免在此期间更改状态，因为这可能会导致更新无限循环。该钩子在服务器端渲染期间不被调用。</p>
                    <p><strong>beforeDestroy（销毁前）</strong>在实例销毁之前调用。实例仍然完全可用。</p>
                    <p><strong>destroyed（销毁后）</strong>在实例销毁之后调用。调用后，所有的事件监听器会被移除，所有的子实例也会被销毁。该钩子在服务器端渲染期间不被调用。</p>
                    <p>
                        <span>1.什么是vue生命周期？</span><br>
                        <span>答： Vue 实例从创建到销毁的过程，就是生命周期。从开始创建、初始化数据、编译模板、挂载Dom→渲染、更新→渲染、销毁等一系列过程，称之为 Vue 的生命周期。</span>
                    </p>
                    <p>
                        <span>2.vue生命周期的作用是什么？</span><br>
                        <span>答：它的生命周期中有多个事件钩子，让我们在控制整个Vue实例的过程时更容易形成好的逻辑。</span>
                    </p>
                    <p>
                        <span>3.vue生命周期总共有几个阶段？</span><br>
                        <span>答：它可以总共分为8个阶段：创建前/后, 载入前/后,更新前/后,销毁前/销毁后。</span>
                    </p>
                    <p>
                        <span>4.第一次页面加载会触发哪几个钩子？</span><br>
                        <span>答：会触发 下面这几个beforeCreate, created, beforeMount, mounted。</span>
                    </p>
                    <p>
                        <span>5.DOM 渲染在 哪个周期中就已经完成？</span><br>
                        <span>答：DOM 渲染在 mounted 中就已经完成了。</span>
                    </p>
                </div>
                <div class="part">
                    <label>三、 Vue实现数据双向绑定的原理：Object.defineProperty（）</label>
                    <p>vue实现数据双向绑定主要是：<strong>采用数据劫持结合发布者-订阅者模式的方式</strong>，通过Object.defineProperty（）来劫持各个属性的setter，getter，在数据变动时发布消息给订阅者，触发相应监听回调。当把一个普通 Javascript 对象传给 Vue 实例来作为它的 data 选项时，Vue 将遍历它的属性，用 Object.defineProperty 将它们转为 getter/setter。用户看不到 getter/setter，但是在内部它们让 Vue 追踪依赖，在属性被访问和修改时通知变化。</p>
                    <p>vue的数据双向绑定 将MVVM作为数据绑定的入口，整合Observer，Compile和Watcher三者，通过Observer来监听自己的model的数据变化，通过Compile来解析编译模板指令（vue中是用来解析 {{}}），最终利用watcher搭起observer和Compile之间的通信桥梁，达到数据变化 —>视图更新；视图交互变化（input）—>数据model变更双向绑定效果。</p>
                    <p>
                        <strong>js实现简单的双向绑定</strong><br>
                        <input type="text" id="txt">
                        <span id="show"></span>
                        <!-- <script type="text/javascript">
                            var obj = {}
                            Object.defineProperty(obj, 'txt', {
                                get: function () {
                                    return obj
                                },
                                set: function (newValue) {
                                    document.getElementById('txt').value = newValue
                                    document.getElementById('show').innerHTML = newValue
                                }
                            })
                            document.addEventListener('keyup', function (e) {
                                obj.txt = e.target.value
                            })
                        </script> -->
                    </p>
                </div>
                <div class="part">
                    <label>四、Vue组件间的参数传递</label>
                    <p>
                        <strong>1.父组件与子组件传值</strong><br>
                        <span>父组件传给子组件：子组件通过props方法接受数据;</span><br>
                        <span>子组件传给父组件：$emit方法传递参数</span>
                    </p>
                    <p>
                        <strong>2.非父子组件间的数据传递，兄弟组件传值</strong><br>
                        <span>eventBus，就是创建一个事件中心，相当于中转站，可以用它来传递事件和接收事件。项目比较小时，用这个比较合适。（虽然也有不少人推荐直接用VUEX，具体来说看需求咯。技术只是手段，目的达到才是王道。）</span>
                    </p>
                </div>
                <div class="part">
                    <label>五、Vue的路由实现：hash模式 和 history模式</label>
                    <p><strong>hash模式：</strong>在浏览器中符号“#”，#以及#后面的字符称之为hash，用window.location.hash读取；</p>
                    <p>特点：hash虽然在URL中，但不被包括在HTTP请求中；用来指导浏览器动作，对服务端安全无用，hash不会重加载页面。</p>
                    <p>hash 模式下，仅 hash 符号之前的内容会被包含在请求中，如 http://www.xxx.com，因此对于后端来说，即使没有做到对路由的全覆盖，也不会返回 404 错误。</p>
                    <p><strong>history模式：</strong>history采用HTML5的新特性；且提供了两个新方法：pushState（），replaceState（）可以对浏览器历史记录栈进行修改，以及popState事件的监听到状态变更。history 模式下，前端的 URL 必须和实际向后端发起请求的 URL 一致，如 http://www.xxx.com/items/id。后端如果缺少对 /items/id 的路由处理，将返回 404 错误。<strong>Vue-Router 官网里如此描述：</strong>“不过这种模式要玩好，还需要后台配置支持……所以呢，你要在服务端增加一个覆盖所有情况的候选资源：如果 URL 匹配不到任何静态资源，则应该返回同一个 index.html 页面，这个页面就是你 app 依赖的页面。”</p>
                </div>
                <div class="part">
                    <label>六、vue-cli如何新增自定义指令？</label>
                    <p>
                        <span>1.创建局部指令</span><br>
                        <img src="../assets/image/1.png" alt="">
                    </p>
                    <p>
                        <span>2.全局指令</span><br>
                        <img src="../assets/image/2.png" alt="">
                    </p>
                    <p>
                        <span>3.指令的使用</span><br>
                        <img src="../assets/image/3.png" alt="">
                    </p>
                </div>
                <div class="part">
                    <label>七、vue如何自定义一个过滤器？</label>
                    <p>
                        <span>html代码：</span><br>
                        <img src="../assets/image/4.png" alt="">
                    </p>
                    <p>
                        <span>JS代码：</span><br>
                        <img src="../assets/image/5.png" alt="">
                    </p>
                    <p>
                        <span>全局定义过滤器</span><br>
                        <img src="../assets/image/6.png" alt="">
                    </p>
                    <p>过滤器接收表达式的值 (msg) 作为第一个参数。capitalize 过滤器将会收到 msg的值作为第一个参数。</p>
                </div>
                <div class="part">
                    <label>八、一句话就能回答的面试题</label>
                    <p>
                        <strong>1.css只在当前组件起作用</strong><br>
                        <span>答：在style标签中写入scoped即可 例如：<!-- <style scoped></style> --></span>
                    </p>
                    <p>
                        <strong>2.v-if 和 v-show 区别</strong><br>
                        <span>答：v-if按照条件是否渲染，v-show是display的block或none；</span>
                    </p>
                    <p>
                        <strong>3.$route和$router的区别</strong><br>
                        <span>答：$route是“路由信息对象”，包括path，params，hash，query，fullPath，matched，name等路由信息参数。而$router是“路由实例”对象包括了路由的跳转方法，钩子函数等。</span>
                    </p>
                    <p>
                        <strong>4.vue.js的两个核心是什么？</strong><br>
                        <span>答：数据驱动、组件系统</span>
                    </p>
                    <p>
                        <strong>5.vue几种常用的指令</strong><br>
                        <span>答：v-for 、 v-if 、v-bind、v-on、v-show、v-else</span>
                    </p>
                    <p>
                        <strong>6.vue常用的修饰符？</strong><br>
                        <span>答：.prevent: 提交事件不再重载页面；.stop: 阻止单击事件冒泡；.self: 当事件发生在该元素本身而不是子元素的时候会触发；.capture: 事件侦听，事件发生的时候会调用</span>
                    </p>
                    <p>
                        <strong>7.v-on 可以绑定多个方法吗？</strong><br>
                        <span>答：可以</span>
                    </p>
                    <p>
                        <strong>8.vue中 key 值的作用？</strong><br>
                        <span>答：当 Vue.js 用 v-for 正在更新已渲染过的元素列表时，它默认用“就地复用”策略。如果数据项的顺序被改变，Vue 将不会移动 DOM 元素来匹配数据项的顺序， 而是简单复用此处每个元素，并且确保它在特定索引下显示已被渲染过的每个元素。key的作用主要是为了高效的更新虚拟DOM。</span>
                    </p>
                    <p>
                        <strong>9.什么是vue的计算属性？</strong><br>
                        <span>答：在模板中放入太多的逻辑会让模板过重且难以维护，在需要对数据进行复杂处理，且可能多次使用的情况下，尽量采取计算属性的方式。好处：①使得数据处理结构清晰；②依赖于数据，数据更新，处理结果自动更新；③计算属性内部this指向vm实例；④在template调用时，直接写计算属性名即可；⑤常用的是getter方法，获取数据，也可以使用set方法改变数据；⑥相较于methods，不管依赖的数据变不变，methods都会重新计算，但是依赖数据不变的时候computed从缓存中获取，不会重新计算。</span>
                    </p>
                    <p>
                        <strong>10.vue等单页面应用及其优缺点</strong><br>
                        <span>答：优点：Vue 的目标是通过尽可能简单的 API 实现响应的数据绑定和组合的视图组件，核心是一个响应的数据绑定系统。MVVM、数据驱动、组件化、轻量、简洁、高效、快速、模块友好。缺点：不支持低版本的浏览器，最低只支持到IE9；不利于SEO的优化（如果要支持SEO，建议通过服务端来进行渲染组件）；第一次加载首页耗时相对长一些；不可以使用浏览器的导航按钮需要自行实现前进、后退。</span>
                    </p>
                    <p>
                        <strong>11.怎么定义 vue-router 的动态路由? 怎么获取传过来的值</strong><br>
                        <span>答：在 router 目录下的 index.js 文件中，对 path 属性加上 /:id，使用 router 对象的 params.id 获取。</span>
                    </p>
                </div>
                <div class="part">
                    <label>九、$router和$route的区别</label>
                    <p>$route为当前router跳转对象里面可以获取name、path、query、params等</p>
                    <p>$router为VueRouter实例，想要导航到不同URL，则使用$router.push方法，返回上一个history使用$router.go方法。</p>
                    <p>
                        <strong>路由传参的方式：</strong><br>
                        <span><strong>用params传递：</strong>this.$router.push({name:'Login',params:{id:'leelei'}})</span><br>
                        <span><strong>用query传递：</strong>this.$router.push({path:'/login',query:{id:'leelei'})</span><br>
                        <span>query传参是针对path的，params传参是针对name的。。接收参数的方式都差不多。。this.$route.query.和this.$route.params.</span><br>
                        <span style="color: rgb(243, 171, 83);">使用query传参的话，会在浏览器的url栏看到传的参数类似于get请求，使用params传参的话则不会，类似于post请求。</span>
                    </p>
                </div>
            </div>
        </div>
        <div class="list-con w1200" v-if="index == 3">
            <div class="content">
                <div class="part">
                    <label>vue创建项目</label>
                    <p>1.首先安装vue-cli</p>
                    <p>npm install -g vue-cli</p>
                    <p>2.vue初始化项目</p>
                    <p>vue init webpack 项目名</p>
                    <p><img src="../assets/image/7.png" alt=""></p>
                    <p>Use ESLint to lint your code? (Y/n)   是否使用ESLint管理代码，ESLint是个代码风格管理工具，是用来统一代码风格的</p>
                    <p>Setup unit tests with Karma + Mocha? (Y/n)   是否安装单元测试</p>
                    <p>Setup e2e tests with Nightwatch(Y/n)?    是否安装e2e测试</p>
                    <p>最后，因为各个模板间都是相互依赖的，所以要安装依赖，用命令进入项目的目录，在命令行输入npm install</p>
                </div>
                <div class="part">
                    <label>上传项目到git中</label>
                    <p class="p">
                        <span>1、先进入项目文件夹，通过命令 git init 把这个目录变成git可以管理的仓库</span>
                        <span class="bg">git init</span>
                    </p>
                    <p class="p">
                        <span>2、把文件添加到版本库中，使用命令 git add .添加到暂存区里面去，不要忘记后面的小数点“.”，意思为添加文件夹下的所有文件。</span>
                        <span class="bg">git add .</span>
                    </p>
                    <p class="p">
                        <span>3、用命令 git commit告诉Git，把文件提交到仓库。引号内为提交说明。</span>
                        <span class="bg">git commit -m 'message'</span>
                    </p>
                    <p class="p">
                        <span>4、关联到远程库。</span>
                        <span class="bg">git remote add origin 你的远程库地(如：https://github.com/jwhuang59/vue-element-traveling.git)</span>
                    </p>
                    <p class="p">
                        <span>5、将项目所有push文件到仓库中。</span>
                        <span class="bg">git push -u origin master</span>
                    </p>
                    <p>
                        <strong>常见问题</strong><br>
                        <img src="../assets/image/8.png" alt=""><br>
                        <span>原因：本地和远程的文件应该合并后才能上传本地的新文件</span>
                    </p>
                    <p>
                        <strong>解决:</strong><br>
                        <span>拉取合并master代码</span><br>
                        <span>git pull --rebase origin master</span><br>
                        <span>然后再提交：git push -u origin master</span>
                    </p>
                </div>
            </div>
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
            index: 1

        };
    },
    computed: {

    },
    created() {

    },
    mounted() {
        this.index = this.$route.query.index
        console.log('获取路由传递过来的参数',this.$route.query.index)

    },
    watch: {

    },
    methods: {

    },
    components: {
        myHead
    },
};
</script>

<style scoped>
.list-con {background: #ffffff;margin-top: 20px;box-sizing: border-box;padding: 30px 50px;}

.content p {line-height: 24px;margin: 8px 0;font-size: 14px;}
.content .part {margin-bottom: 20px;background: #ffffff;padding: 10px;}
.content .part label {display: inline-block;padding-bottom: 10px;border-bottom: 1px solid #cccccc;width: 100%;font-size: 18px;
font-weight: bold;}
.content .part p.p span {display: block}
.content .part p.p span.bg {background: #eef0f4;padding: 10px 20px;font-size: 15px;color: #666666;}
@media screen and (max-width:640px){
    .list-con {background: #ffffff;margin-top: .2rem;box-sizing: border-box;padding: .3rem;}
    .w1200 {width: 100%;}
    .content p {line-height: .46rem;margin: .3rem 0;font-size: .28rem;}
    .content .part {margin-bottom: .2rem;background: #ffffff;padding: .1rem;}
    .content .part label {display: inline-block;padding-bottom: .1rem;border-bottom: 1px solid #cccccc;width: 100%;font-size: .36rem;
    font-weight: bold;}
    .content .part img {width: 100%;}
    .content .part p.p span.bg {background: #eef0f4;padding: .2rem .4rem;font-size: .3rem;color: #666666;}
}
</style>

