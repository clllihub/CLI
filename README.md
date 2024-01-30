![img](img/1.png)

网站主要功能及运行原理说明文档

### 1. 网站功能概述

该网站是一个图片展示网站，具有以下主要功能：
- **展示图片：** 网站主界面以轮播方式展示图片，每隔一段时间自动切换一张图片。
- **显示图片信息：** 对每张图片，显示其标题、每日鸡汤、坐标和拍摄设备信息。
- **提取图片颜色：** 从每张图片中提取主要的颜色信息，并以渐变条的形式展示在页面上。
- **播放背景音乐：** 用户与页面的第一次交互（点击任意位置）后，开始播放背景音乐。

### 2. 运行原理

#### 图片切换及信息更新
- 网站通过JavaScript实现定时切换图片的功能。使用`setInterval`函数每隔一段时间调用`changeImage()`函数，切换图片并更新相关信息。
- `changeImage()`函数从预定义的图片数据中获取下一张图片的信息，并更新页面上的标题、每日鸡汤、坐标和拍摄设备信息。然后准备下一张图片的索引，以便在下一次切换时使用。

#### 图片颜色提取及渐变条更新
- 网站利用Color Thief库从每张图片中提取主要的颜色信息。
- 在`updateGradientBar()`函数中，如果图片已经加载完成，会使用Color Thief获取图片的主要颜色，并将其转换为十六进制格式。然后，使用CSS的线性渐变背景，将这些颜色呈现为渐变条，并更新页面上的颜色代码。
- 如果图片尚未加载完成，会监听图片的`load`事件，以便在图片加载完成后执行颜色提取和渐变条更新的操作。

#### 背景音乐播放
- 网站利用JavaScript监听了页面的`click`事件。当用户首次点击页面时，触发`playMusic()`函数。
- `playMusic()`函数通过获取页面上的音频元素并检查其播放状态，来控制音乐的播放与暂停。

### 3. 技术实现

- **HTML：** 定义页面结构和内容。
- **CSS：** 设置页面样式和布局。
- **JavaScript：** 处理页面交互和动态效果。
- **Color Thief库：** 用于从图片中提取颜色信息。
- **阿里云 OSS：** 用于存储网站图片和Logo。

### 4. 总结

该网站通过JavaScript控制图片展示和信息更新，利用Color Thief提取图片颜色，结合CSS创建渐变条效果，同时实现了背景音乐的自动播放功能。整体上，网站利用了前端技术和第三方库来增强用户体验，并呈现出美观的图片展示页面。
