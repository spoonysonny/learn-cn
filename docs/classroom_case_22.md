## 投票机

用多块micro:bit来制作一个投票机吧！

[https://youtu.be/77HOqf8BaNg](https://youtu.be/77HOqf8BaNg)

在这个项目中，一个**投票**程序被下载到玩家的micro:bit上。玩家用按钮来选择`yes`或`no`的投票，并用无线电将投票结果发送到一块作为**控制面板**的micro:bit上。控制面板给每个玩家分配一颗LED灯，并根据投票结果来将它点亮或熄灭。

#### 投票程序
假设按钮`A`代表NO（反对）投票，按钮`B`代表YES（支持）投票，那么投票程序看起来像这样：

#### 发送一个NO（反对）投票
当按钮`A`被按下，通过无线电发送数字`0`，屏幕上就会显示图标`X`。

![](https://i.imgur.com/Fax3S6P.png)

#### 发送一个YES（支持）投票
当按钮`B`被按下，通过无线电发送数字`255`，屏幕上就会显示图标`Y`。

![](https://i.imgur.com/xfr9srN.png)

#### 设置序列号
为了追踪投票结果，我们也会让无线电传输设备的序列号。

![](https://i.imgur.com/imV728b.png)

#### 设置无线电组
我们选择将无线电阻设置为`4`用于通信。

![](https://i.imgur.com/hRvSznV.png)

将所有的代码部分放到一起，这就是投票程序的完整代码：

![](https://i.imgur.com/UYsuqkl.png)

### 控制面板

控制面板的代码在无线电控制面板的案例中。
从那个案例中下载代码到micro:bit以显示投票结果。
当控制面板收到一块micro:bit的信息，它会在那块micro:bit上显示一个像素点（记住它），并用收到的数字来作为LED的亮度。
当micro:bit一段时间没有收到信息，它的像素点将会开始闪烁。之后，这个像素点就会熄灭。

<div style="position:relative;height:0;padding-bottom:70%;overflow:hidden;"><iframe style="position:absolute;top:0;left:0;width:100%;height:100%;" src="https://makecode.microbit.org/#pub:_cyA0wJioC4mp" frameborder="0" sandbox="allow-popups allow-forms allow-scripts allow-same-origin"></iframe></div>

