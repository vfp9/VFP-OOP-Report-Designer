# VFP-OOP-Report-Designer
世界第一款完全面向对象的VFP报表设计器。

![](screenshot.png)

## 缘由：
VFP 固有的报表设计器，从 VFP3 已经定型了。至 VFP9，功能改进是有目共睹的，但复杂度也相应提高了不少。但是设计UI，几乎没有改变。对大多数 VFP 程序员来说，VFP 的报表设计器就是鸡肋。

2018年，我初次作为一个职业程序员在改动所在公司的软件架构时，遇到一个在当时状态下无法解决的问题，它一直遗留到我从该公司离职：

1. 在运行时，我找不到屏蔽某些影响程序运行的菜单，不是我的能力不够，是 VFP 根本没有提供（参看 SYS(2013) 或者 VFP 帮助中的“系统菜单名”一节）。这相当于在程序运行时如果提供修改/制作报表的功能时，给自己埋了一个不定时的炸弹，而且无法“拆除”！

2. 众所周知，VFP9 提供了一个新的报表引擎：90 。它所能实现的功能已开枝散叶，但是，必须在 ***SET REPORTBEHAVIOR 90**** 的环境下。恰恰是这个设置，造成在运行时修改/制作报表时，工具栏的显示状态会出现“花屏”现象，虽然有解，但解决方案丑陋到无法入目，如果软件本身为一个蛋糕，那么，这个解决方案就是蛋糕中裹着的一坨屎！

在 2019 年夏天的某个时刻，我忽然意识到以上所遇到问题的根本问题：VFP 报表设计器已经是“固化”到 VFP.EXE 里的，在 90 引擎下，在当时的开发团队的现实情况下，所谓的 90 引擎的报表设计，只能以外挂的方式来改进，但是它与 VFP UI，本质上是“分离”的。这是直接导致第 2 个问题的“罪魁祸首”。而第 1 个问题，几乎无解，或许你懂得反编译或汇编才可能有机会。

很感谢 Doug Hennig 提供了一个开源的项目：OOPReports（英文版 https://github.com/VFPX/OOPReports) (中文版 https://github.com/vfp9/OOPReports) 。它几乎就是个所谓的报表引擎！

我所需要实现的，就仅仅是将非可视对象，在UI中予以展现，并将所有的报表设计“结果”回写到非可视对象并使用“引擎”的保存方法就可以获得一个 FRX ！

我知道在设计原理上，它简单到只需上述的一句话就可以完整的说明设计思路。但在实现上，不知道有多少个坑在等着我去填......

我发起了一个所谓的众筹项目。

但是限于个人的私人情况，此项目至今才基本完成。

## 已实现设计目标：
1. 它是对象化的。

2. 它的使用是平滑替代 VFP 报表设计器，几乎无需另外学习。并且，提供了一个相对现代的设计UI。

3. 它在设计时报表是可缩放的，当然，也可以在缩放状态下进行设计，虽然后一个设计方法是我个人不建议的，因为在缩放状态下的设计，报表控件的定位会有可以理解的“偏差”。

4. 在设计报表时，更改“默认打印机”、更改纸张方向或者更改纸型，报表已有布局会自动调整而无需手工操作。

5. 它在一定程度上实现了所见即所得。

## 待实现的设计目标
1. 可以很方便的在报表设计时提供所谓“第三方”支持，例如条形码/二维码/图表等。

2. 报表的保护

3. 真正的所见即所得

## 更新历史

**2023.08.02**

版本：α1.02

修改：属性窗口的行为：点击属性窗口中的属性名，属性值选项控件可以立即获得焦点；在切换当前所选控件后，属性窗口中属性名如果存在，不再定位在行首。

**2023.08.02**

版本：α1.01

修改：增加遗漏的图标文件

**2023.08.01**

α1 测试版发布
