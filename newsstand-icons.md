#报刊杂志图标

对于使用 NewsstandKit 来发布订阅期刊内容的应用，需要提供显示在 App Store 上和设备上的图标。

![image](images/newsstand_intro_2x.png)

所有的杂志摊应用需要提供一个默认的杂志封面图标显示在 App Store 中，这个图标的最长边不能小于 1024 像素（对于标准分辨率的设备不能小于 512 像素）。注意，这个图标与所有 iOS 应用都必须提供的应用图标不同。
>重要  
所有杂志摊图标的比例都必须介于 1:2 与 2:1 之间。  
所有杂志摊图标都必须是扁平且为直角边缘。  
不要为杂志摊图标增加任何透视效果。

默认的杂志摊图标必须能够表示这份期刊整体的内容，所呈现的内容对于每一期不同的期刊来说，都具有一致性。例如：
- 不要在默认封面图标上增加在实际的一期杂志封面上不会出现的元素，如类似“点击这里查看最新一期”的本文。
- 不要使用具有时效性的插图或标题，如一些与节日有关的图片或与时事有关的标题。

特别注意，不要使用往期杂志的封面作为应用默认的封面图标，否则用户会将应用与具体的某一期杂志混淆。例如某个默认的报刊杂志图标：

![image](images/magazine_default.jpg)

![image](images/newspaper_default.jpg)

除了默认的图标之外，你同样需要为每一期新的期刊提供单独的图标，这个图标会出现在杂志书架及 iOS 设备的多任务界面上。与默认封面图标不同，每一期期刊的图标需要详细展示了这一期内容的细节。

建议每一期期刊都单独创建一个大尺寸的图标，这样 iOS 可以在所有需要的地方将这个图标缩放使用。

所创建的每一期期刊的图标的最长边也不能小于 1024 像素（对于标准分辨率的设备不能小于 512 像素），当将这个图标放在杂志书架及多任务界面上时，iOS 会将这个大图标缩放为以下尺寸：

表 45-1 每期期刊图标最大缩放尺寸

|设备|缩放尺寸（杂志书架）| 最长边缩放尺寸（多任务界面）|
|---|:---:|:---|
|iPhone 6 Plus|270 x 240 像素|180 像素|
|所有其他 iPhone 设备|180 x 160 像素 (@1x 为90 x 80 像素)|120 像素 (@1x为 60 像素)|
|iPad|最长边 252 像素 (@1x 为 126 像素)|152 像素 (@1x 为 76 像素)|

了解更多有关创建杂志摊应用的信息，查阅 [iTunes Connect Developer Guide](https://developer.apple.com/library/ios/documentation/LanguagesUtilities/Conceptual/iTunesConnect_Guide/Chapters/About.html#//apple_ref/doc/uid/TP40011225)。

>重要  
从 iOS7 起，系统不会为杂志摊的图标增加任何视觉增强效果（如订书钉边缘或多层页面堆叠效果）。  
如果你的应用要适应 iOS 早期的版本，你可以在 Info.plist 文件中增加 bingding 类型和 binding edge 参数，来定义如何在 iOS7 之前版本的系统中呈现图标的效果。了解更多有关这些参数及其值的信息，参见 [Contents of the UINewsstandIcon Dictionary](https://developer.apple.com/library/ios/documentation/General/Reference/InfoPlistKeyReference/Articles/CoreFoundationKeys.html#//apple_ref/doc/uid/TP40009249-SW15)。
