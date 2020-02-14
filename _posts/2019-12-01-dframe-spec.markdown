---
layout: post
title: LCD显示面板 - 规格
category: [ee, linux]
comments: false
---

## “车库”和实验室的区别

认识一些在家里做DIY、焊板子，甚至修显卡的朋友，也通过网络观察到各方DIY大师的工作条件。跟实验室相比，这些DIY的条件有几个特点：

* 首先是人。不能说专业实验室里的人动手能力就更强，但是在焊板子这件事情上往往更熟练。
* 设备专业程度，通常是实验室更优。我说的是通常（以下佳同）
* 料件品类的丰富程度，通常是实验室胜。
* 料件数量的丰富程度，当然是公家比较有钱。


## 做一块LINUX板子的选项

#### 从CPU架构开始进行方案选型

消费电子的方案里跑 LINUX 的主流无非就是 MIPS / ARM，我说的是主流。

MIPS里面能跑LINUX，的首先想到的是路由器方案的芯片。又其中的首先想到的就是MTK家族。RT5350,7688,。。

* RT5350在淘宝能买到芯片，15RMB/PCS左右。问题是，
  * BGA芯片不难焊，不过反复利用就很麻烦
  * BGA芯片做两层板相对QFP还是更挑战呐

* MT7688在淘宝也能买到芯片，15RMB/PCS左右。问题是，
  * MT7688使用DDR2，做2层板不容易；更不要说没有技术支持请情况下画两层板的DDR2了
  * DDR2 BGA 封装也存在反复料件利用的问题 
  * MT7688本身的封装是非常不好焊的，比BGA难呐

除了路由器的芯片以外，有诸如君正等的MIPS芯片也可以尝试，但是就更冷门了。

在ARM阵营这边，能跑LINUX的芯片好多都能跑ANDROID，然后就有L1/L2 CACHE、GPU。当然需要大内存，DDR2/DDR3。。这些是不怎么拿的上手的。

ARM阵营非常强大，品类丰富。所以细心找还能发现TI等的一些非ANDROID方案。然而能跑LINUX、好焊又不贵的，还有全志的A13这颗。A13的缺点是：

* 已经 EOL 了
* 设计资料神神叨叨
* 接的是DDR2

这几个问题其实都可以克服，作为优秀的纯粹的MAKER，经过几天的比对发现NXP的LPC系列可能更优。比如LPC1788

* 官方有一堆你看起来嫌多的资料
* 十年老片但是正常供货中
* LQFP封装，好焊。更重要的是方便焊了拆、拆了焊
* 外接SDRAM，跑个100M，不用考虑信号完整性就能跑的


## 规格

阅读了官方的资料之后，计划做一块板子有以下的规格

* 能接800x480分辨率的TFT LCD
* ETHERNET
* USB HOST
* TF-CARD
* 32MB SDRAM
* 跑 linux。可人家是 cotex-m！
  * 同学，nommu linux 已经合并到kernel主干了。[https://www.kernel.org/doc/Documentation/nommu-mmap.txt](https://www.kernel.org/doc/Documentation/nommu-mmap.txt)
