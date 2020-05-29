﻿# eraSQN中文化计划

### 项目说明

个人挺喜欢这黄油，玩着可以吃下三大桶饭，以前一直玩的`v 0.235`的汉化。

但是这个版本的汉化……不是太完全，就连游戏系统的一些字段都没翻译完，而且bug也不少。

所以闲着无事就google了一下，发现这游戏最终版本是`v 1.00`，还有英译版。

于是就萌生了重新开坑的想法，起初是想用英译版来汉化的，毕竟日文水平太差。

但后来发现，英译版加了各种mod，而且这英译的文本跟程序代码完全混在一起了啊，特么竟然连程序逻辑都变得看不懂了！

最终还是决定用日文最终版下手……

### 项目进度

- [x] 完成CSV文件的翻译

- [ ] 尝试跟着游戏加载的流程，读懂ERB文件的代码逻辑（正在进行）

	- [ ] 并完成对应的游戏功能菜单翻译

		- [ ] 进行调教 / 前去会面

		- [ ] 查看能力

		- [ ] 休息

		- [ ] 交换助手和对象

		- [ ] 变更助手

		- [ ] 变更调教对象

		- [ ] 梦魔召唤（正在进行，功能比较复杂，进度会比较慢）

		- [ ] 梦魔出售

		- [ ] 确认着装

		- [ ] 召见御用商人

		- [ ] 去高级服饰店

		- [ ]  去秘法店

		- [x] 去饰品屋

		- [ ] 去酒馆

		- [ ] 外出许可管理

		- [ ] 外出探索

		- [ ] 素材调和

		- [ ] 文书工作

		- [ ] 助手○○处理

		- [ ] 温泉旅行

		- [ ] 偏爱＆弱点设定

		- [ ] 道具＆服装一览

		- [ ] 出售道具

		- [ ] 咖啡店

		- [ ] 保存

		- [ ] 读取

		- [ ] 等级限制器

		- [ ] 系统设定

		- [ ] 迎接ＥＮＤ

- [ ] 尝试优化 / 修复游戏中潜在的问题（同步进行）

	- [ ] 进行调教 / 前去会面

	- [ ] 查看能力

	- [ ] 休息

	- [ ] 交换助手和对象

	- [ ] 变更助手

	- [ ] 变更调教对象

	- [ ] 梦魔召唤（正在进行，功能比较复杂，进度会比较慢）

	- [ ] 梦魔出售

	- [ ] 确认着装

	- [ ] 召见御用商人

	- [ ] 去高级服饰店

	- [ ]  去秘法店

	- [x] 去饰品屋

		+ 第8个饰品会被新鉴定的饰品覆盖

	- [ ] 去酒馆

	- [ ] 外出许可管理

	- [ ] 外出探索

	- [ ] 素材调和

	- [ ] 文书工作

	- [ ] 助手○○处理

	- [ ] 温泉旅行

	- [ ] 偏爱＆弱点设定

	- [ ] 道具＆服装一览

	- [ ] 出售道具

	- [ ] 咖啡店

	- [ ] 保存

	- [ ] 读取

	- [ ] 等级限制器

	- [ ] 系统设定

	- [ ] 迎接ＥＮＤ

- [ ] Emuera引擎的Wiki翻译

- [ ] 完成游戏剧情文本翻译

- [ ] 整合原版发布站在`v 1.00`发布后追加的一些附加内容和口癖

### 游戏资源

1. [eraSQN Wiki](/Wiki)

2. 相关资源

    + [\[Emuera引擎开源仓库\]](https://osdn.net/projects/emuera/)

    + [\[游戏下载链接\]](https://github.com/chinanoahli/eraSQN-to-chs/archive/master.zip)<sub>这个链接会自动指向最新的汉化版</sub>

3. 游戏许可证

    + [\[日版及其引擎许可证\]](/Original_Edition_External_Info/License%40Emuera.txt)

    + [\[汉化版许可证\]](/LICENSE)

### 相关提示

1. 当你在游玩时遇到类似以下的图片的提示时，请先点击`否(N)`试一试。<br/>这个提示是Emuera引擎为了防止游戏脚本发生死循环而设计的保护机制。<br/>一般来说有些脚本执行的时间比较长，就会弹出此提示，让玩家决定是否**中止**当前**正在运行**的游戏脚本。<br/>点击`否(N)`游戏就会继续运行，否则游戏脚本会被强制中止并抛出错误提示。<br/>若游戏确实长时间无响应，再按`是(Y)`，并参考页面最后一节的[Bug反馈](#bug反馈)，将你遇到的情况反馈一下。

	![infinite_loop_en](/Wiki/Resources/infinite_loop_en.png)

	> 当你要快速跳过大量文本时，建议使用按键精灵之类的软件连续输出大量的鼠标左键点击。
	> 因为这个提示默认的按钮是`是(Y)`，也就是说如果你长按`Enter`进行快进时，有可能会错误地将正在运行的游戏中止了！

### BUG反馈

如果在游玩时，遇到致命错误，导致游戏异常退出的情况。

一般来说此时Emuera引擎会在游戏根目录生成一个名为`emuera.log`的日志文件。

请复制这个日志文件的全部内容（至少是最后一次显示主菜单后面的全部内容）。

然后点击页面上方的[`Issues`](https://github.com/chinanoahli/eraSQN-to-chs/issues)，然后点击绿色按钮`New issue`新建一个反馈并将日志内容粘贴到反馈内。
