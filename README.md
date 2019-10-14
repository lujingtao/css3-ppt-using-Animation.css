@[toc](跟我做css3的ppt（Animation介绍&Animate.css应用）)

# 一、前言
上一篇文章[《翻滚吧少年！（自定义css3动画过渡中的贝塞尔曲线）》](https://blog.csdn.net/iamlujingtao/article/details/102558382)我简单介绍了css3中transition的使用，和自定义过渡中的贝塞尔曲线，效果已经很好了，但有一个比较明显的缺点就是还动画方面还不够强大，只能定义开始和结束的状态，如果我要详细控制多个阶段的动画效果，实现更多的效果应该怎么办呢，其实css3中年有专门为动画而设的属性：**Animation**（目前测试兼容chrome、firefox、ie10+）

# 二、Animation 介绍和demo
Animation其实和flash中的动画差不多，有一个关键属性“keyframes”，用与定义不同阶段属性变化，下面用一个例子看看就知道了，核心代码：

```css
    @keyframes bigBoy {
        0% {
            margin-left: 0;
            width: 35px;
            height: 35px;
            line-height: 35px;
            background: #f07709;
        }

        50% {
            margin-left: 180px;
            width: 70px;
            height: 70px;
            line-height: 50px;
            background: #c00;
        }

        100% {
            margin-left: 360px;
            width: 35px;
            height: 35px;
            line-height: 35px;
            background: #514bad;
        }
    }
    .demo:hover .box {
        animation-name: bigBoy;
        /*动画属性名，也就是我们前面keyframes定义的动画名*/
        animation-duration: 2s;
        /*动画持续时间*/
        -webkit-animation-name: bigBoy;
        /* 兼容webkit内核 */
        -webkit-animation-duration: 2s;
        /* 兼容webkit内核 */

    }
```
这里我们定义了一个“bigBoy”的“keyframes”，然后设置 .box 的 animation-name 对应“bigBoy”，动画持续时间2秒，那么当鼠标移到demo这个层上时，了里面的box就会动起来了。
Animation还有很多属性，具体自行百度了。

效果：
![在这里插入图片描述](https://img-blog.csdnimg.cn/20191015001602400.gif)
[-->在线demo](https://lujingtao.github.io/css3-ppt-using-Animation.css/animationDemo.html)

有了Animation，就能就很多很多动画了，是不是有点小激动呢～

# 三、Animate.css 介绍
每次写代码是不是有点麻烦？不怕这里帮到你，http://daneden.github.io/animate.css/ 这个css已经定义了常用的动画效果css，你需要做的只是用js把不同的类名加到对应div上，就有效果了。
例如：`$(".box").addClass("bounce")`;
 
 # 四、使用Animate.css做一个ppt
 
现在发挥想象力，做一个ppt试下：
一开始以为挺容易的，写着写着发现写了不少js，**核心思路就是不断addClass、removeClass**啦。
例如： 点击第二页-->第一页元素添加移除效果的class（例如bounceOutDown）然后隐藏-->第二页元素显示并添加移入效果的class（例如bounceInLeft）。

效果：
![在这里插入图片描述](https://img-blog.csdnimg.cn/20191015002836403.gif)
[-->GitHub地址](https://github.com/lujingtao/css3-ppt-using-Animation.css)
[-->在线演示](https://lujingtao.github.io/css3-ppt-using-Animation.css/)
