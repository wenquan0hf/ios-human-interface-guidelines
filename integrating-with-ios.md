# 与 iOS 一体化

与 iOS 一体化意味着，要带给用户一种愉悦的，引人入胜的，与平台连贯的用户体验。但这并不是要创建一个看起来像内置软件复制的应用。

让你独特的应用与平台一体化的最好方式，是去了解那些引导着 iOS 的关键词——它们在 [Designing for iOS](designing-for-ios.md) 中提到过，并不断发掘你应用表达他们的最好方式。当你这样做时，这一部分中指南将会帮助你带来符合用户期待的用户体验。

## 正确使用标准的 UI 部件

尽可能用 UIKit 提供的标准UI部件。当你使用标准而非自定义的部件时，你和你的用户都将受益：

- 当 iOS 引入了新设计的外观时，标准 UI 部件将会自动收到更新——而自定义部件就不会这样。
- 标准 UI 部件倾向于提供不同的方式来自定义他们的外观或行为。例如，所有视图（即那些继承了 UIView 的对象）可以使用 tintColor 来上色，这将会使得为应用添加颜色变得容易。
- 使用标准部件对于用户来说没有学习成本。
- 
为了更好的发挥使用标准 UI 部件的优势，以下这些十分关键：

**遵从每一个 UI 元素的指南。**当 UI 元素的外观和作用都像用户熟悉的那样时，用户之前的经验可以帮助他们在你的应用中使用这些部件。更多 UI 元素指南，参考 [Bars](bars.md), [Content Views](content-views.md), [Controls](controls.md)和[Temporary Views](temporary-views.md)

**不要混用不同版本的 iOS 中的 UI 部件风格。** 使用看起来不像当前设备运行的 iOS 版本而像是来自其他版本的 UI 部件，会使用户感到困惑，而这并不是你希望看到的。

**在一般情况下避免为一个标准操作创建自定义的 UI 部件。**首先，问问自己为什么想要创建一个实际上只是执行标准操作的自定义 UI  部件。如果你只想自定义外观的话，可以考虑通过 UIKit 外观自定义 API 或 tint color 来改变标准的部件外观。如果你只是想要稍微改变一下操作，确定你已经了解，当你改变标准部件的属性和特征时，它还是不是会按你预期的那样工作。如果你确实想要一个完全自定义的操作，最好的实现方式是创建一个，看起来与标准部件不是太像的自定义部件。

>提示：接口建造器（Interface Builder）可以令以下操作变得容易：获得标准 UI 部件、使用外观自定义 API、访问属性和权限、在自己的模块中运用自定义或系统提供的标志。参见[ Xcode Overview](https://developer.apple.com/library/ios/documentation/ToolsLanguages/Conceptual/Xcode_Overview/index.html#//apple_ref/doc/uid/TP40010215)，了解更多关于接口建造器内容。

**不要将系统定义的按钮或标志另作他用。** iOS 提供了很多你可以在你的应用中使用的按钮和标志。确保你已经明白这些按钮和标志文档中的语义含义，不要仅凭你对它们外观的理解就去使用。

如果你认为系统自带的按键和标志不能合理的表达你应用提供的功能，你可以自定义他们，参看[ Bar Button Icons](bar-button-icons.md),帮助你设计你自定义的标志
**如果你的应用提供仿真任务或体验，使用完全自定义控制将会变得合理。**因为此时你在创建一个独特的环境，而了解如何控制这样的环境将会是用户在这类应用中期待的体验。

## 淡化文件和文档处理

iOS 可以帮助用户创建并管理文件，但并不代表用户必须考虑 iOS 设备的文件系统如何运作。

如果你的应用能帮助用户创建并编辑文档，可以提供应用特有的库文件浏览器让用户打开已有文件或者创建新文件。更多关于文档提供器拓展，与文档选择视图控制器的内容参见 [Document Provider Extensions](https://developer.apple.com/library/ios/documentation/UserExperience/Conceptual/MobileHIG/AppExtensions.html#//apple_ref/doc/uid/TP40006556-CH67-SW5)，[Document Picker Programming Guide](https://developer.apple.com/library/ios/documentation/FileManagement/Conceptual/DocumentPickerProgrammingGuide/Introduction/Introduction.html#//apple_ref/doc/uid/TP40014451)。

理论上，这样的文件浏览器应该：

- **高度图形界面化的。** 用户应该可以轻松地通过屏幕上的文件图形化代表，来找到他们想要的文件。
- **允许用户通过最少的手势动作完成操作。**例如，用户可以通过水平拖动，浏览在轮播方式或表格方式下陈列的文件，然后通过点击其中一个，来打开他们想要的文件。
- **包含创建新文件的功能。**一个库文件管理器可能会让用户，通过点击占位图标的方式来创建新文件，而不是在应用之外某处执行这个功能。

例如, Pages 应用在图形化显示库文件的同时，还为用户提供了创建新文件的简单方式：

![document_library_2x.png](/images/document_library_2x.png)

>提示：即使你的应用不能打开文件，你也可以通过提供快速预览功能让用户可以预览内容。

如果你的应用程序想要允许用户使用他们在其他应用程序中创建的文件，你可以通过显示一个模态文件选择视图控制器来帮助他们获取这些文件。除了与其他文件创建或储存应用相关联的文件提供器拓展外，文件选择视图控制器同样也可以在用户的 iCloud 驱动中显示文件。

**让用户相信文件将总是会被保存，除非他们明确要取消或删除**如果你的应用要帮助用户创建或者编辑文档，不要要求单独的保存操作，无论用户是要打开其他文档，还是要从当前应用切换出去，iOS 应用都有责任为用户保存输入。

但如果你应用的主要功能不是创建内容，而是让用户可以在浏览和编辑之间切换，你可以要求一个单独的保存操作。在这种情况下，在显示信息的视图中，提供一个编辑按钮将会是不错的选择。当用户点击了编辑按钮后，用保存按钮替换掉它，并再提供一个取消按钮。编辑按钮的变化，提醒了用户他们当前处在编辑模式中，并可能需要执行保存操作，而取消按钮为他们提供了在不保存变更的情况下退出的选择。

## 如果可以将应用变成可配置的

一些应用需要为用户提供设置或是配置的方式，大多数的应用回避或推迟了这样的处理。但成功的应用不仅能够立即做到，还为用户提供了方便方式来调节他们的体验。

当你将按照大多数用户的期望设计你应用的功能时，你便减少了对于设置的需求。当你需要用户信息的时候，你应该向系统而不是用户发出请求。如果确定要为用户提供他们几乎不怎么变更的应用设置，可以参看[The Settings Bundle](https://developer.apple.com/library/ios/documentation/iPhone/Conceptual/iPhoneOSProgrammingGuide/Inter-AppCommunication/Inter-AppCommunication.html#//apple_ref/doc/uid/TP40007072-CH6-SW7)，了解如何在代码中实现这一需求。

**尽可能在主 UI 中提供配置选项。**当一个选项需要被频繁的变更或者它代表了主要任务时，将该选项放在主界面中会是合理的安排。但如果用户只是偶尔需要改变应用的配置，将选项放到分页面中会比较合理。参看 [Settings Launch URL](https://developer.apple.com/library/ios/documentation/UIKit/Reference/UIApplication_Class/index.html#//apple_ref/doc/constant_group/Settings_Launch_URL)。

**必要时帮助用户直接到达设置中关于你应用的部分。**尤其是你显示的信息是如何找到关于你应用的设置时（如设置 > 我的应用 > 个人 > 本地服务），将它们替换成一个可以直接在设置中打开该路径的按钮

## 更好的运用 iOS 技术

iOS 提供了丰富的技术，这些技术可以以用户期待的方式支持普遍的任务和场景。这里的“期待”指的是，将系统支持的技术整合到你的应用中总会比自己单独设计一套方法来的好。

一些 iOS 技术，像多任务处理（ [Multitasking](multitasking.md) ）和 [VoiceOver](voiceOver.md)，是所有应用都应该包含的系统特征。其他的允许了特定的应用功能，像是处理票务和赠品卡的电子卡包（[Passbook](passbook.md)），允许用户在应用内支付的应用内购买服务（[In-App Purchase](in-app-purchase)），显示应用内广告的iAd 富媒体广告（[iAd Rich Media Ads](iad-rich-media-ads.md)），提供整合服务的游戏中心（[Game Center](game-center.md)），和支持服务的 [iCloud](icloud.md)。


