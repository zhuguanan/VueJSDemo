1.仅供学习交流，有疑问和错误麻烦指出

============================================================================
时间：2018-4-9 23:28:09
标题：v-show
日志：
#1.v-if是有惰性的，如果初始条件渲染时为false，则说明也不做，再条件第一次变为true时才开始局部编译（编译会被缓存起来）
#2.相比之下，v-show简单的多，元素始终被编译并且保留，只是简单的基于CSS切换
#3.一般来说，v-if有更高的切换消耗，而v-show有更高的初始渲染消耗。因此，如果需要频繁的切换，则使用v-show较好;
如果在运行时条件不大可能改变，则使用v-if较好。
标题：v-else
日志：
#1.顾名思义，v-else就是JS中的else的意思，他必须跟着v-if或者v-show，充当else功能
#2.v-else尽量不要和v-show一起使用，详细代码见Demo5

时间：2018-4-14 17:16:52
标题：Do not mount Vue to <html> or <body> - mount to normal elements instead.错误
#1.Vue body标签下面要放一个<div id="example"></div>

标题：v-model.lazy 属性
#1.官方文档给的例子是<input type="text" v-model="message" lazy>,按照这个写法没有效果；
网上查了一下资料改成了一下写法可以<input type="text" v-model.lazy="message">。
#2.v-model在input事件中同步输入框的值和数据，我们可以添加一个lazy特性，从而将数据改到在change事件中发生。
详情见：Demo6_VueVmodel
#3.Vue2.0 移除了属性debounce,该属性在每次敲击之后延时同步输入框的值和数据。如果每次更新都要进行高耗操作
（例如：在input中输入内容时随时发送AJAX请求），那么它较为有用。由于2.0移除了该数据，暂时不写具体实例。自行
参考Vue1.0