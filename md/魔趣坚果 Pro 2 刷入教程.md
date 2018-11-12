# 魔趣 MK71.2 坚果 Pro 2 刷入教程

## 写在前面

1. 该手机的厂商不提供刷机保修，意味着**刷机后你将失去保修资格**，且需要自己承担失手造成故障的风险；
2. 该手机首次刷机**需要特殊的工具和极强的动手能力**，请**先充分阅读本帖**再决定是否继续刷机；
3. 未测试过是否能在 Pro 2 特别版（骁龙 636 版）是否正常， 请谨慎尝试；
4. 魔趣是原生系统，不包含（也不会加入）一步、大爆炸等 Smartisan OS 特色功能。如果你离不开他们，不建议你尝试魔趣；
5. 考虑到刚开始适配可能还存在一些 BUG，不建议你在日常使用的手机上尝试，以免耽误正常工作和生活。

## 准备工具

1. **高通 EDL 线**（也称为 9008 线、救砖线、工程线），自行上淘宝购买（10几块的就够了，反正就用一次。淘宝上有些卖家会写着「小米工程线」，其实是同一个东西，通用的）。
2. **TWRP QPST 工具包**，下载地址：[https://pan.baidu.com/s/1evUlfOTzT46i_Q02_A5OJA](https://pan.baidu.com/s/1evUlfOTzT46i_Q02_A5OJA#9jm3) 419 (密码: 9jm3)
3. **底包**，下载地址：[https://pan.baidu.com/s/1IuopqXHXQU41z2GqluRrsw](https://pan.baidu.com/s/1IuopqXHXQU41z2GqluRrsw#ddr3) 211 (密码: ddr3)
4. **魔趣刷机包**：[http://rom.mk/?device=osborn 1。2K](http://rom.mk/?device=osborn)

考虑到大家的动手能力，不建议自己 DIY 刷机线。能买就买吧。

**再次警告：坚果 Pro 2 刷机会丧失保修资格；且需要极强的动手能力，稍有失误可能会使你的手机永久损坏。如果你没有 100% 的把握，请放弃！**

## 〇、准备

1. 将魔趣刷机包（文件名一般是 `MK71.2-osborn-` 开头）下载放在你的内置存储根目录下
2. 如果你刷过老外的 TWRP 且这个 TWRP 可以正确读取你的内置存储，请看【二】
3. 如果你刷过老外的 TWRP，但这个 TWRP 无法读取内置存储，请看【一】
4. 如果你之前没刷过 TWRP，或者不知道这一段在说什么，请看【一】
5. 如果你看到这里有点怂了，请放弃

## 一、刷入 TWRP

1. 解压上面下载的 QPST 工具包（`QPST_TWRP_U3Pro_20180518-2.7z`），安装里面的 `1. Qualcomm HS-USB QDLoader` 和 `2. QPST 2.7.460` 两个文件夹里的安装包，重启电脑；
2. 打开刚安装的 Qfil 软件
3. 拔掉数据线， 关机。等待手机彻底关机、屏幕不亮为止；
4. 把 EDL 线插到电脑上，按住 EDL 线上的小开关把另一头插入手机。等待大概 3 秒松手，此时电脑上的 Qfil 应该会识别到 `Qualcomm HS-USB QDLoader` 设备；
5. 在 Qfil 里选择 `Flat Build`
6. 点击 Programmer 的那个 Browse，选择刷机工具包内 `3. TWRP` 目录里的 `prog_emmc_ufs_firehose_Sdm660_ddr.elf`
7. 点击 Load XML，选择工具包里的 `rawprogram_unsparse.xml`
8. 它会再次弹出选择框，选工具包里的 `patch0.xml`

现在，**这是你最后一次认怂的机会。如果你想放弃，现在拔掉数据线并长按音量加和电源键即可退出；如果你想继续，那么就继续看**：

1. 点击 Download 按钮，你会看到下面的文字花花花滚了很多，然后结束了
2. 长按**音量减**和**电源**键。直到你看到白色锤子的时候松开电源键（继续按住音量减键）；直到你看到 TWRP 的时候才松开所有按键
3. 你已经刷完 TWRP 了。不要重启，继续看【二】

如果失败了，你可以按住**音量加**和**电源**键退出 EDL 模式，回到正常系统，并考虑是否要放弃。

## 二、刷入魔趣

1. 进 Wipe（清除），把下面那个条条拖住向右划一下
2. 返回上一层，进 Install（安装），刷入底包（`RADIO-osborn-` 开头的那个）
3. 返回上一层（不要重启），再次进安装，刷入魔趣（`MK71.2-osborn-` 开头的那个）
4. 刷完重启，完成

## 注意事项

- 由于坚果的 Bootloader 仍然会校验 boot.img 的签名，所以请勿自己刷入 Magisk 等需要改动 boot 的模块。否则会导致卡在白锤子

------

## 三、如何刷回 Smartisan OS 官方系统

1. 下载官方 4.2.1 版并放到内置存储根目录：[http://dl2.smartisan.cn/ota/OSBORN/osborn/4.2.1/20180426/4.2.1-2018042519-user-ob-208e77d2cd.zip 2。2K](http://dl2.smartisan.cn/ota/OSBORN/osborn/4.2.1/20180426/4.2.1-2018042519-user-ob-208e77d2cd.zip)
2. 长按**音量减**和**电源**键。直到你看到白色锤子的时候松开电源键（继续按住音量减键）；直到你看到 TWRP 的时候才松开所有按键
3. 进 Wipe（清除），把下面那个条条拖住向右划一下
4. 返回上一层，进 Install（安装），找到你之前下载的官方卡刷包
5. 刷完重启，完成





## MK81.0 (Oreo)

#### 底包

对应魔趣版本：MK81.0 自 20180909 起
AFH：[RADIO-osborn-20180904222847.zip 358](https://androidfilehost.com/?fid=1322778262904000089)
百度盘：[点此下载](https://pan.baidu.com/s/1GbGec1iFmDbBV4Lu7rC8IQ#kg7e) (密码: kg7e)

对应魔趣版本：MK81.0 自 20180824 起
AFH： [RADIO-osborn-20180819093819.zip 181](https://androidfilehost.com/?fid=1322778262903988568)
百度盘：[点此下载](https://pan.baidu.com/s/1Jl6S0VdDf2rt2ugyH8vnXQ#tqu9) (密码: tqu9)

#### TWRP

百度盘：[点此下载](https://pan.baidu.com/s/1Om0i9RKYl5i-xaTH2io6iQ#f2m7)(提取码: f2m7)
(MK71.2 无法使用 MK81.0 的 TWRP 进行 OTA 增量更新，请注意区分)

------

## MK71.2 (Nougat)

详见 [魔趣 MK71.2 坚果 Pro 2 刷入教程](https://bbs.mokeedev.com/t/topic/6377)

------

扩展阅读：[什么是底包](https://bbs.mokeedev.com/t/topic/281)



把8.1底包，刷机包，还有第二贴下载的8.1twrp放入储存根部,先按7.1教程刷入twrp，然后在twrp中刷入8.1的twrp，再重启twrp依次刷入底包，刷机包，ok



坚果 Pro 在英文版官网被称作 U2 Pro 

坚果 Pro 2在英文官网被称作U3 Pro   （osborn）

坚果 3 在英文官网分别被称作U3

**刷入8.1需要使用8.1的TWRP（3.2.x版本）**





因为高通给 9.0 的内核更新了 F2FS，不向后兼容，降级比较麻烦。 

说一下坚果 Pro 2 魔趣 9.0 正确的降级到魔趣 8.1、魔趣 7.1、

官方系统的方法： 

1. 将你的所有数据（包括内置存储）备份到电脑上 

2. 进 TWRP 3.1.1（也就是刷 7.1 用的那个版本）格式化 data 分区 

3. 刷官方系统或魔趣 7.1（或升级回 TWRP 3.2 之后刷 8.1）



   注意：千万不要尝试用任何方法在 TWRP 3.2（刷 8.1 用的那个）里格式化 data，会让你降级更麻烦。 

   另外，破二的魔趣 9.0 和 8.1 都重新添加了 EXT4 支持，更加成熟稳定（但魔趣 7.1 和官方系统只支持 F2FS）。 

   珍爱生命，远离 F2FS。



简而言之，

破二刷 Android 8.1 专用的 TWRP：
链接: [http://t.cn/RrNUexA 228](http://t.cn/RrNUexA) 密码: iby3

破二魔趣 8.1 专用底包（7.1 不要刷，会死）：
链接: [http://t.cn/RrNUexZ 116](http://t.cn/RrNUexZ) 密码: x7vv

不卡 fastboot 的 Magisk（8.1 和 7.1 通用，OTA后需要重刷）：
链接: [http://t.cn/RrNUexw 89](http://t.cn/RrNUexw) 密码: cvku



某破二的 TWRP 3.2.3 已更新到 20180918-1 版
适用于破二刷入 MK81.0 及 MK90.0

主要变化：
1. 修复刷入 MK90.0 之后无法双清的问题
2. 修复刷入 MK90.0 之后无法刷入 Open GApps 的问题
3. 完善 NV 备份功能，加入之前漏掉备份的一个分区（当然，希望你们永远不需要用到这个功能）

注意：
1. 如果你需要降级回 MK71.2 或官方系统，你仍然需要降级到 TWRP 3.1 并格式化整个 Data 分区
2. 如果你之前用我的旧 TWRP 备份过 NV，建议用这个新的 TWRP 重新备份一次，以便补上之前遗漏备份的部分
3. 切记 NV 只能自己恢复自己的！千万不可以使用别人的 NV！
4. 使用别人的 Persist 备份也可能会导致传感器失效，不建议冒险

链接:http://t.cn/Rkj4WBZ 提取码:j9f3



MK90.0-osborn-201810310226-UNOFFICIAL.zip 

没仔细测过，不知道会有什么问题； 

TWRP、底包和现行 MK81.0 一样； 

相比上个版本只是更新了主代码； 

声音问题暂时懒得修； 

不知道什么时候上夜版，再问拉黑。

[下载地址](https://pan.baidu.com/s/19aNTPCanOwCSQpAxFcg8AQ)

提取码: sq9x



锤子科技的所有机型的完整卡刷包   [链接](http://sm.xingrz.me/)



* NV 代表了 modemst* fs* 那些 IMEI 之类的信息，建议备份
* Persist 是传感器数据，有些移植 ROM 可能会意外地使这个分区数据出错，建议刷机前备份一下 



7.1每夜版升8.1必须双清；
8.1 0628之前的测试版必须双清；
8.1 0628测试版升每夜版不需要双清

