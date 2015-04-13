# 启动和终止 (Starting and Stopping)

## 即时启动

据说，人们通常不会花超过一两分钟来审视一个新的 app。当你可以快速并简洁的展示出有用的信息时，你的 app 就会吸引用户，并且给用户提供了十分好的体验。

>**重要**
>
>不要在用户安装完你的 app 后要求他们重启设备。重启会占据用户的时间并且会显得你的 app 看起来不可信又难以使用。
>
>如果你的 app 有内存使用方面的问题，不重启就难以流畅运行，那么你需要声明这些问题。关于如何开发一个能流畅运行的 app，请点击 [Use Memory Efficiently](https://developer.apple.com/library/ios/documentation/iPhone/Conceptual/iPhoneOSProgrammingGuide/PerformanceTips/PerformanceTips.html#//apple_ref/doc/uid/TP40007072-CH7-SW8)

**尽可能不使用闪屏等启动效果。**最好可以令用户快速启动你的 app。

推荐样式：

![](images/avoid_startup_r_2x.png)

不推荐样式：

![](images/avoid_startup_nr_2x.png)

**不要要求用户设置太多的信息。**而应该这样：

* **关注你 80% 的用户群的需求。**当你完成了这个要求，大多数人们就不需要额外更改设定，因为你的默认设置就已经完成了他们的预期。对于那些只有一小部分人需要的和大多数人很少能用到的功能，就不要管了。
* **尽量从其他地方获取用户信息。**如果你能从内置 app 或设备设置中获取用户信息，就不要再询问用户了。
* **如果你必须要求用户更改设定，直接在你的 app 中提示用户修改。**然后尽快保存这些信息（包括潜在的信息）。这样，人们在享受你的 app 前不用被迫更改设定。如果用户需要更改，他们也可以随时进入 app 的设定界面更改设置。

**尽量推迟用户登录的时间。**用户在不登陆的情况下就可以使用一部分功能是很好的选择。例如，App Store 不要求用户登录直到他们决定购买东西。用户通常会停止使用一些在他们还没有进行任何有用的操作前就要求他们登陆的 app。

如果用户必须登录，那么请将登陆界面设计的简洁、友好，同时注明用户必须登录的理由和好处。

**仔细思考新手指导部分。**（新手指导介绍了一个 app 的特点，解释了如何操作常见的功能。）在你考虑使用新手指导之前，一定要使你的 app 的所有特性和功能都是直观且易于找到的。“好的应用不需要新手指导。”如果你一定要使用，那么请参考以下建议，设计一个简洁、有针对性并且不会妨碍用户的新手指导。

* **只提供开始使用 app 时必要的信息。**一个好的新手指导向用户展示了首先要做的事，简洁的示范了一些大多数用户感兴趣的特性。如果你在用户使用前就提供了太多的信息，用户需要在一开始就记住这些他们可能并不急需的细节，这会给用户一种你的 app 难以使用的感觉。
* **使用动画和交互功能来吸引用户，让用户通过实际操作来学习。**谨慎地添加文本信息，且只在文字会提升用户体验时添加；不要指望用户阅读长文章。例如，如果你能使用动画就不要用文字去描述一个简单的任务。在引导用户做一个复杂的操作时，可以通过一些引导浮层来简要说明每一个步骤用户需要做什么。尽量不要使用 app 的截图，因为他们不能产生交互，用户会混淆截图和应用界面。
* **能够简单地取消或跳过新手引导界面。**当用户看过一次新手引导后，他们不会想看第二次；也有些用户可能根本不想看引导。确保用户可以选择是否观看，并且不要在每次打开 app 时都出现引导环节。

**不要太早让用户给你的 app 打分。**太早要求评分的 app 会使用户感到厌烦，而且这会减少你收到的有效的反馈信息。为了鼓励用户提供更有价值的反馈，请给用户多一点时间思考。例如，等待用户访问了一定数量的界面，使用了一部分功能后再要求他们评价。

**通常情况下，使你的应用在设备的当前方向启动。**当然，如果你的 app 仅支持一个方向，它就只在那个方向启动，让用户来调整设备的方向。例如，如果一个游戏或视频应用只能在水平方向横屏模式运行，那么就应该以横屏模式启动，即使当前设备处于竖直状态。这样的话，即使用户是在竖直方向上开启了 app，他们也能明白此时应该调整设备来观看。

![](images/default_orientation_2x.png)

>**提示**
>
>仅支持横屏的 app 最好可以支持两种方向的横屏，即 Home 键在左侧和右侧。如果设备此时已经是横屏状态，那么该 app 就应该在那个方向启动，除非你有一个更好理由不这样做。其他情况时，建议按 Home 键处于右侧的方式启动应用。（想了解更多关于如何支持不同的设备方向，请点击 [Adaptivity and Layout](https://developer.apple.com/library/ios/documentation/UserExperience/Conceptual/MobileHIG/LayoutandAppearance.html#//apple_ref/doc/uid/TP40006556-CH54-SW1)）

**准备一个启动图像。**ios 会在你的 app 启动时展示一个启动图像，这既能给用户一个关于你的 app 的印象，也能给 app 一段加载内容的时间。学习如何创建一个启动图像，请点击 [Launch Images](https://developer.apple.com/library/ios/documentation/UserExperience/Conceptual/MobileHIG/LaunchImages.html#//apple_ref/doc/uid/TP40006556-CH22-SW1)

**尽可能不要让用户在初次使用时就阅读免责声明或确认用户协议。**你可以让 App Store 展示你的免责声明或用户协议，这样用户可以在下载前就看到它们。如果你一定要在你的 app 中显示这些内容，请确保它们与你的 UI 和谐并且能与用户需求间达到一个平衡。

**当你的 app 重新启动时，读取用户离开时的状态信息以便他们可以继续使用。**用户不需要记住之前的状态。想了解更多关于保存和读取 app 状态的有效方法，请点击 [Preserving Your App’s Visual Appearance Across Launches](https://developer.apple.com/library/ios/documentation/iPhone/Conceptual/iPhoneOSProgrammingGuide/StrategiesforImplementingYourApp/StrategiesforImplementingYourApp.html#//apple_ref/doc/uid/TP40007072-CH5-SW2)

## 时刻准备停止

**ios app 从来没有关闭或退出选项。**人们停止使用当前的 app 的时机，可以在转换到另一个 app 时，可以是返回到主屏幕时，也可以是将它们的设备调成睡眠模式时。

当用户离开了你的 app 时，ios 的多任务功能会将它转换到后台，并且用新 app 的 UI 替换它的 UI。为了适应这种情况，你的 app 需要做到以下几点：

* **尽快且尽可能合理的保存用户数据。**因为后台的 app 有可能在任何时候被退出。
* **当应用停止时保存当前状态的细节。**这要的话，当用户回到你的 app 时，可以继续之前的操作。例如，如果你的 app 支持滑动查看数据，就保存当前的滑动位置。想了解更多关于保存和读取 app 状态的有效方法，请点击 [Preserving Your App’s Visual Appearance Across Launches](https://developer.apple.com/library/ios/documentation/iPhone/Conceptual/iPhoneOSProgrammingGuide/StrategiesforImplementingYourApp/StrategiesforImplementingYourApp.html#//apple_ref/doc/uid/TP40007072-CH5-SW2)

有些 app 在后台也会继续运行，即使此时用户在运行另外的 app。例如，当用户听音乐时，他们也可以查看未做事项清单或者玩游戏。想了解更多关于如何正确的使用多任务功能，请点击 [Multitasking](https://developer.apple.com/library/ios/documentation/UserExperience/Conceptual/MobileHIG/Multitasking.html#//apple_ref/doc/uid/TP40006556-CH38-SW1)

**不要强制让程序退出。**强制退出会让用户以为这是个意外。如果你的 app 发生了一些预料之外的事，你需要告诉用户这个情况，并且解释该如何做。这里是两个很好的方法：

* **如果 app 所有的功能都无法使用，在屏幕上显示这个情况然后提出一个正确的方案。**这些信息会告诉用户他们的 app 没有出现什么问题。这也能稳定用户，让他们决定是否要采取正确的方法继续使用或是更换其他的 app。

![](images/all_features_unavailable_2x.png)

* **如果你的部分功能无法使用，弹出一个文本框或警示来告诉用户这些功能不可用。**除此以外，人们可以继续使用 app 的其他部分。如果你要使用警示，确保它仅会在用户选择不可用功能时弹出。


![](images/one_feature_unavailable_2x.png)
