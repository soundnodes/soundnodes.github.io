---
layout: post
title: PCB EDA 工具（1） - 先后使用过的各种画板软件
category: ee
comments: false
---

## 最早从PADS开始

最早使用 PADS 是因为公司的硬件部门是使用 OrCAD + PADS，对于当时的我来说学习曲线很陡峭。幸好有才哥分享资料，然后慢慢就上手了。套路跟公司的 OrCAD + PADS 的搭配还不同，我也用 PADS 画原理图。使用 PADS 先后做了几块电路板，现在回头最开始的那块，真的太 wacky 了，全部直角拐弯，线宽也乱来。。

#### 感受

* 版本基本就没有见到更新过
* 工作流、界面，很老旧
* PADS 的 router 是挺好使的
* 不推荐新手学习

#### 最早时用 pads 画的板子

时间比较久，实物图片找到再拍照补，贴几个截图纪念一下
（现在自己看都想笑）

这个好像是第一块，Linkit Smart(MT7688) 接 WM7840；也画了树莓派的接口，就是没有接过
![w800](/images/2019-07-16-talk-about-eda-tools-01.jpg)

这算是第一块的改进版，加了些 MT7866 模块的焊盘、接口
![w800](/images/2019-07-16-talk-about-eda-tools-02.jpg)

这个是用PCB做的机箱前后盖子
![w800](/images/2019-07-16-talk-about-eda-tools-03.jpg)

这个是 STA339 的 CLASS-D 功放板子，接的还是 MT7688
![w800](/images/2019-07-16-talk-about-eda-tools-04.jpg)


这个是 STA339 + MT7688 + 编码开关 + DCDC + LCD彩屏

直到这块板子还是经常走90度的线，很厉害对不对
![w800](/images/2019-07-16-talk-about-eda-tools-05.jpg)

---

## EAGLE

因为网上很多开源的库，有很多清楚明了的教程。然后就学习了并且用 EAGLE 做了好多块板子，做板子也越来越快了、看上去也越来越顺眼了。

板子画了好几块，以后再补图。

#### 感受

* 还不错，推荐新手学习；
* 如果要画非常复杂的板子，还是不要了。不过对于新手，挺够用的；
* 自动布线用得比较顺手、其它 EDA 也有自动布线，但是 EAGLE 的自动布线用得比较多。简单板子上午画原理图下午自动布线在改一下就可以发了；
* 免费版本可以画 8CMx10CM 两层板，对 DIYer 基本够用。

---

## ALTIUM

用 EAGLE 画 DDR3 的板子还是比较吐血了，所以就决心学一个正经的 EDA。算学了一半，画过一个 MCU + DDR3 的模块板子，没有发板。

下图是之前用ALTIUM画DDR3等长，是比 EAGLE 好使得多
![w800](/images/2019-07-16-talk-about-eda-tools-21.jpg)

#### 感受

* 运行超级慢。运行速度来说，如果 pads 是汽车，那么 eagle 是火箭，ALTIUM 是蜗牛。用 8G内存 + SSD + 较快 CPU 的电脑还比较顺利运行；
* 更新快，但是不稳定。EAGLE 超级稳定，从不崩溃；PADS 偶尔；ALTIUM 经常；
* 国内用的人是相当多的，可能是国内最流行的 PCB EDA 了；
* 可能是因为：
  1. 国内使用学习版本软件的情况多，免费软件的免费意义不大；
  2. 相比 PADS 界面是好很多；
  3. 相比 allegro 学习更容易。
* 因为用的人确实多，所以还是蛮建议学习的。


---

## ALLEGRO

试图学习，没有完成全部的学习。感觉我不会画一个超级大的 16 层板子，所以还是不要折磨自己了。

是的我放弃了。学会以后，我以后用它来干嘛呢？我想不出来。

#### 感受

* 软件的交互体验很不习惯，就是打开软件是必然有一个对话框要选一个原理图工具或者一个PCB工具这一点已经让我吐血好久了。
* 不建议初学者学习。

---

## KiCAD

因为我认为使用一直使用学习版本的软件而不付授权是不对的，并且授权是支付不起的；所以我不应该继续花时间在 ALTIUM 上面，这是我的自身情况。同时 EAGLE 在画一些板子时已经显得吃力了，我应该找一个更厉害的 EDA。KiCAD 在 ALTIUM 之前就视图学习了，但是没有成果。现在就下定决心。。

今天火速地画了一块超级简单的板子，当天发板了。基本上掌握整个流程，下一步就是深入学习了。

#### 感受

* 工作流是不一样的，EAGLE 的流程还是比较更舒服些；
* 交互性、功能性、易用程度，跟 ALTIUM 是不能比的，不过功能是比 EAGLE 强大；
* 如果你有 ALTIUM 的授权，或者愿意用学习版，那么就不要折腾了；如果想用开源软件，那么试试KiCAD吧。

