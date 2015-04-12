#多任务处理（Multitasking）

多任务处理让人们可以在最近使用的应用之间进行快速切换。

![multitasking_2x.png](/images/multitasking_2x.png)

为了支持这样的体验，多任务处理会让一款应用在用户切换离开后，在后台进入挂起状态。当用户切换回来时，应用可以快速重新启用，因为它无需重新加载UI。人们使用多任务处理UI( multitasking UI )（如上图）来选择一款最近使用了的应用。

> API 提示：想要了解在你的代码中如何支持多任务处理，请参阅中的[App States and Multitasking](https://developer.apple.com/library/ios/documentation/iPhone/Conceptual/iPhoneOSProgrammingGuide/StrategiesforHandlingAppStateTransitions/StrategiesforHandlingAppStateTransitions.html#//apple_ref/doc/uid/TP40007072-CH8)。

能否出色的运用多任务处理取决于能否与设备中的其他应用和谐共事。
从更高的层面来说，这意味着所有的应用都应该：

*    能够有得体的处理来自其他应用的打断或声音
*    停止和重启，即快速平稳地从后台切换到前台
*    不在前台时应恪守己任

下述指南细则可以帮助你的应用更好的运用多任务处理。

**准备好被打断，并恢复。**多任务处理增加了后台应用中断你的应用的可能性。其他特性，诸如广告出现和更快的应用切换，也会造成更频繁地打断。越快速、越精确地保存应用的当前状态，用户便可以越快地重新运行应用，并从之前离开的位置继续使用。你可以通过利用 UIKit 的状态保存和恢复功能来为用户提供无缝的重新运行体验（查看[ Preserving Your App’s Visual Appearance Across Launches](https://developer.apple.com/library/ios/documentation/iPhone/Conceptual/iPhoneOSProgrammingGuide/StrategiesforImplementingYourApp/StrategiesforImplementingYourApp.html#//apple_ref/doc/uid/TP40007072-CH5-SW2)了解更多信息）。

**确保你的UI可以处理两倍高度的状态栏。**两倍高度的状态栏会在诸如通话、录音和共享等过程中出现。在未作处理的应用中，状态栏的额外高度会引起布局问题，如UI被向下挤压或者被遮住。在多任务处理环境中，正确的处理两倍高状态栏显得尤为重要，因为可能会有更多的应用导致它的出现。

**准备好暂停需要人们注意或主动参与的活动。**例如，如果你的应用是一款游戏或媒体观看应用，你需要确保你的用户从应用切换走时，不会丢失任何内容或事件。当人们切换回游戏或媒体播放器时，他们希望能继续之前的体验，就好像他们从未离开过应用。

**确保音频行为合适。**当你的应用正在运行时，多任务处理会使得其他媒体活动更可能地同时发生，也会有更多可能性使你的音频不得不暂停，并恢复来响应中断。查看 [Sound](https://developer.apple.com/library/ios/documentation/UserExperience/Conceptual/MobileHIG/Sound.html#//apple_ref/doc/uid/TP40006556-CH44-SW1) 来帮助你确保你的音频能满足人们的期望，并与设备中的其他音频和谐共处。

**适度使用本地通知。**应用可以在特定时间发送本地通知，无论应用是在暂停中还是运行中亦或是根本就没有运行。为了达到最好的用户体验，应避免用过多的通知来骚扰人们，并遵循 [notification](https://developer.apple.com/library/ios/documentation/UserExperience/Conceptual/MobileHIG/NotificationCenter.html#//apple_ref/doc/uid/TP40006556-CH39-SW1) 中创建通知内容的指南。

**必要时，在后台完成用户的任务。**当人们开始一个任务时，他们通常会期望即使已经从应用中切换走了，任务仍能够完成。如果你的应用正在执行用户已经初始化了的任务，并且这个任务不需要额外的用户交互，那么你就应该在应用挂起之前就在后台完成任务。


