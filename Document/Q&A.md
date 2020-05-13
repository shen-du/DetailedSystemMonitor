# 问题解答


#### 1. 为什么在我的电脑上，皮肤看起来很小？

* 皮肤默认尺寸为200x750像素，而不同计算机显示器的像素密度不同，在小尺寸但高分辨率屏幕上显示，看起来会很小。解决方法是调整皮肤的缩放比例参数（如图）：建议固定选择**1.20**，**1.50**或**2.00**。特别注意**刷新皮肤前请检查小数点位置！！**

![](https://github.com/Lssg97/DetailedSystemMonitor/blob/master/Image/1.png)


#### 2. 为什么我的皮肤和图片展示的不一样，感觉缺东西？

* 这个现象可能主要体现在GPU监控显示的内容上。皮肤会根据系统环境和硬件环境自动适应，隐藏当前环境下无法显示的内容。如：受到系统环境影响，Windows 10 1709以前的系统无法显示非NVIDIA核心显卡的使用率，没有独立显卡的计算机无法显示显存使用情况，等等。如果您实在觉得皮肤在您的计算机上缺少某些内容属于功能性问题，可以参考 [首页](https://github.com/Lssg97/DetailedSystemMonitor) 建议。


#### 3. 为什么使用本皮肤后，我的电脑上其它Rainmeter皮肤的动画每秒钟都会卡顿一次？

* 得益于Rainmeter软件本身的高效，该皮肤的CPU使用率其实非常低（大约只有1%-2%左右）。但是尽管如此，该皮肤每秒钟还是要搜集并刷新大量信息。尤其是GPU监测方面，每秒钟要额外更新将近1000个变量信息。并且受Rainmeter本身机制限制，整个皮肤的全部信息更新与内容绘制要在16ms内完成。因此对于那些本身拥有高刷新率的动画皮肤来说，该皮肤的刷新会消耗一部分它们所需的性能，尤其是打开Rainmeter日志时。不过正常来说，这些影响基本上微乎其微，且该皮肤也不会对Rainmeter以外的软件造成任何影响。解决方法上，开启Rainmeter的硬件加速功能（Rainmeter管理器 - 设置）可以将那些高刷新率皮肤的绘制工作交由GPU负责，大幅降低Rainmeter的CPU使用率。如果你实在认为该皮肤影响了你的电脑性能，那我只能很遗憾的说：这款皮肤不适合您的桌面。


#### 4. 为什么“显示器分辨率”监控和系统设置的不一样？

* 这是因为你的计算机开启了Windows的显示缩放功能，Rainmeter识别分辨率错误造成的，请参考下图来进行设置：打开Rainmeter安装目录，鼠标右键点击`Rainmeter.exe`,属性，兼容性，更改高DIP设置，勾选“替代高DIP缩放行为”，确定。完成操作后重启Rainmeter软件。

![](https://github.com/Lssg97/DetailedSystemMonitor/blob/master/Image/2.png)


#### 5. 为什么“显卡温度”显示为“Nun”或者“N/A”？

* 这是两种不同的情况，请按照下面流程依次判断：
  * 如果皮肤显示为“N/A”，且你的计算机只拥有AMD独立显卡，请检查是否安装了皮肤安装包内自带的`AMDTemperature.dll`插件；
  * 如果皮肤显示为“N/A”，且你的计算机只拥有NVIDIA独立显卡，请检查是否安装了皮肤安装包内自带的`NvidiaGPU.dll`插件；
  * 如果皮肤显示为“N/A”，且你的计算机同时拥有核心显卡和独立显卡，请确保独立显卡已经工作（这种双显卡计算机，一般只有高图形运算要求情况，如玩游戏时，才会令独立显卡工作，平时独立显卡处于关闭状态）；
  * 如果皮肤显示为“N/A”，且你的计算机只有Intel核心显卡，请检查是否在系统后台运行了 [CoreTemp](https://www.alcpu.com/CoreTemp/) 应用；
  * 如果皮肤显示为“N/A”但你的硬件情况不符合上述流程或者皮肤显示为“Nun”，请参考 [首页](https://github.com/Lssg97/DetailedSystemMonitor) 建议。不过如果你走到了这一步，解决问题的可能性就很小了。


#### 6. 为什么我的笔记本“核心显卡使用率”正常，而“独立显卡使用率”和“显存使用率”都是“0”？

* 参考上一条问题的流程3。


#### 7. 为什么任何“显卡使用率”都显示为“0”？

* 首先确保你的系统版本在Windows 10 1709及以上，然后检查你是否还在Rainmeter中加载了其它的和“显卡监控”有关的皮肤。若有，尝试关闭其它和“显卡监控”有关的皮肤，再刷新该皮肤确认情况。若问题没有解决，请参考 [首页](https://github.com/Lssg97/DetailedSystemMonitor) 建议。


#### 8. 为什么“DNS服务器”展示的地址是“网关（路由器）”的地址？

* 应该是你的计算机网络的“DNS服务器”设置为了`自动`。现在绝大部分路由器均接管了其管理的局域网DNS设置。


#### 9. 为什么电脑刚开机，但是“开机时长”已经好几天了？

* 这是Windows的“快速启动”机制导致的，是系统原因。


#### 10. 为什么网络正常但无法显示“广域网IP”或者“归属地”？

* 由于“广域网IP”或者“归属地”信息均来自网站，而网站经常改版，可能会导致皮肤无法正确获取信息。如果你不熟悉Rainmeter皮肤工作方式，遇到这种情况，除了等待下次皮肤更新外没有其他办法。还有一种情况就是你可能在短时间内过于频繁的刷新了皮肤，导致皮肤不断向监测网站服务器发送请求，而被网站服务器认定为恶意攻击。这种情况下请关闭该皮肤，过一段时间后再使用。

