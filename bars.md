# 栏

## 状态栏

状态栏显示了设备和当前环境的重要信息（在 iphone 上显示如下）。

默认（白底黑字）

![image](images/status_bar_default_2x.png)

浅色内容（黑底白字）

![image](images/status_bar_light_2x.png)

状态栏：

- 透明的
- 总是在设备顶部边缘出现

>API 备注  
你可以为整个应用设置统一的状态栏样式，也可以为单独试图设置合适样式。如需了解更过关于 [UIStatusBarStyle](https://developer.apple.com/library/ios/documentation/UIKit/Reference/UIApplication_Class/index.html#//apple_ref/c/tdef/UIStatusBarStyle) 常量和 [preferredStatusBarStyle](https://developer.apple.com/library/ios/documentation/UIKit/Reference/UIViewController_Class/index.html#//apple_ref/occ/instm/UIViewController/preferredStatusBarStyle) 属性的信息，参阅 [UIApplication Class Reference](https://developer.apple.com/library/ios/documentation/UIKit/Reference/UIApplication_Class/index.html#//apple_ref/doc/uid/TP40006728) 和 [UIViewController Class Reference](https://developer.apple.com/library/ios/documentation/UIKit/Reference/UIViewController_Class/index.html#//apple_ref/doc/uid/TP40006926)。

**不要创建自定义状态栏。**用户会依赖于系统状态栏的一致性。就算你在应用中隐藏了它，也优于自定义一个新的 UI 来代替它。

**防止让滚动内容透过状态栏显示。**当用户滑动页面时，你不会希望他们在状态栏区域将应用内容和状态栏本身混淆。为了让用户感觉宽敞的同时仍然保证最佳的可能性，要确保状态栏背景会模糊其背后的内容。这里有一些方法让滚动内容可以透过状态栏隐约呈现：

- 使用导航控制器来显示内容。导航控制器会自动显示状态栏背景，并确保其内容视图不会在状态栏后出现。（如需了解更多关于导航控制器的信息，详见 [Navigation Controllers](https://developer.apple.com/library/ios/documentation/WindowsViews/Conceptual/ViewControllerCatalog/Chapters/NavigationControllers.html#//apple_ref/doc/uid/TP40011313-CH2)）。
- 创建一个不醒目的自定义图片——例如渐变——并放到状态栏后显示。为确保这张图片显示在状态栏后面，你可以使用视图控制器来保证这张图片在滚动视图之上，或者你可以使用滚动视图并让其固定在顶部。
- 定位内容，以避开状态栏区域（即，由应用的 [statusBarFrameproperty](https://developer.apple.com/library/ios/documentation/UIKit/Reference/UIApplication_Class/index.html#//apple_ref/occ/instp/UIApplication/statusBarFrame) 定义的区域）。如果你这样做了，要使用窗口的背景颜色以在状态栏后提供一个固定的颜色。

**避免在状态栏后面放置干扰性内容。**尤其是，你不能让用户觉得轻触状态栏之后可以获取内容或激活你的应用中的控件。

**隐藏状态栏时请慎重。**由于状态栏是透明的，通常情况下不需要隐藏它。始终隐藏状态栏意味着用户必须退出你的应用中切换出去才能看到当前时间，或者是否有 Wi-Fi 连接。

**在用户全屏观看多媒体内容时，考虑隐藏状态栏——和其它所有界面元素。**当你这么做的时候，请确保用户在轻触屏幕时即可恢复状态栏（和其它所有界面元素）。如果没有充分的理由，则要避免重新定义一个手势来让用户唤起状态栏，因为用户很难发现并难以记住这个手势。

**选择一个和你的应用相协调的状态栏颜色。**默认样式以白底黑字显示，适合用在浅色内容的应用的顶部。而黑底白字的状态栏适合放在深色内容的应用的顶部。

**在适当的时候展示网络活动指示器。**网络活动指示器可以出现在状态栏中，以向用户显示长时间的网络接入状态。如需了解如何在代码中执行实现这样的指示器，请参考 [Network Activity Indicator](https://developer.apple.com/library/ios/documentation/UserExperience/Conceptual/MobileHIG/Controls.html#//apple_ref/doc/uid/TP40006556-CH15-SW44)。


## 导航栏

导航栏能够实现在应用不同信息层级结构间的导航，有时候也可用于管理当前屏幕内容。

![image](images/nav_bar_iphone_2x.png)

![image](images/nav_bar_ipad_7_2x.png)

导航栏：

- 半透明的
- 通常位于应用页面顶部，状态栏正下方

在横向常规环境中，一个导航栏也可以不延长屏幕显示在一个视图上，如分裂的一个窗格视图控制器。

- 键盘出现，用户的手势，或视图控制器转换为一个垂直紧凑的环境时，可以隐藏。
- 可以染色。（使用 [tintColor](https://developer.apple.com/library/ios/documentation/UIKit/Reference/UIBarButtonItem_Class/index.html#//apple_ref/occ/instp/UIBarButtonItem/tintColor) 色彩栏按钮项;使用 [barTintColor](https://developer.apple.com/library/ios/documentation/UIKit/Reference/UINavigationBar_Class/index.html#//apple_ref/occ/instp/UINavigationBar/barTintColor) 设置状态栏背景色）。

>API 备注  
导航栏包含在导航控制器（navigation controller）中，该控制器是一个用于管理自定义视图中信息层级展示形式的编程对象。想要了解如何在代码中定义你的导航栏内容，请参考 [Navigation Controllers](https://developer.apple.com/library/ios/documentation/WindowsViews/Conceptual/ViewControllerCatalog/Chapters/NavigationControllers.html#//apple_ref/doc/uid/TP40011313-CH2),[UINavigationController Class Reference](https://developer.apple.com/library/ios/documentation/UIKit/Reference/UINavigationController_Class/index.html#//apple_ref/doc/uid/TP40006934), 和 [UINavigationBar Class Reference](https://developer.apple.com/library/ios/documentation/UIKit/Reference/UINavigationBar_Class/index.html#//apple_ref/doc/uid/TP40006887)。

使用导航栏可以在各个视图之间导航，并能够提供管理视图中条目的控件（如果合适的话）。如果你需要提供更多的控件而且不需要启用导航，考虑使用工具栏代替（如需了解更多信息，请参阅 [Toolbar](https://developer.apple.com/library/ios/documentation/UserExperience/Conceptual/MobileHIG/Bars.html#//apple_ref/doc/uid/TP40006556-CH12-SW4)）。

当用户在导航层级中进入一个新的层级，会发生两个变化：

- 导航栏标题可以适时变成新层级的标题。
- 在导航栏左侧显示返回按钮，并以上一级页面的标题命名。

**如果导航栏需要一个标题，那就使用当前视图的标题作为导航栏的标题。**如果觉得给导航栏增加标题毫无必要，你也可以将标题留空。例如，便签并没有当前便签的标题，因为内容的第一行已经给了用户其所需要的所有情境。 

![image](images/nav_bar_title_not_required_2x.png)

**可以考虑在应用的最顶层导航栏中放置分段控件。**这样会非常有助于扁平化你的信息层级，也会让用户更容易找到所需内容。如果在导航栏中使用了分段控件，请确保选择一个准确的返回按钮标题。（更多详情请参考 [Segmented Control](https://developer.apple.com/library/ios/documentation/UserExperience/Conceptual/MobileHIG/Controls.html#//apple_ref/doc/uid/TP40006556-CH15-SW27)）。

**必要时，可以考虑使用提示语告诉用户当前页面可以做什么。**提示语是一句紧靠着导航栏顶部的简短句子。例如，股票使用一个提示语，以确保用户知道如何找到他们想要的信息。

![image](images/prompt_stocks_2x.png)

如果你需要使用提示语，那就写一句足够简短并以合适标点结尾的话。

**避免用过多的控件将导航栏挤满，即使看上去还有大量的空间。**一般来说，导航栏应至多包含当前视图的标题，返回按钮和一个管理视图内容的控件。如果你在导航栏中使用了分段控件，那就不应该显示标题，而且也不应该包含分段控件以外的任何控件。

**确保文字按钮之间有足够的间隔。**如果在导航栏中那些或左或右的按钮之间没有足够的间隔，按钮上的文字就会被挤到一起，而这会让用户很难区分它们。如果导航栏里按钮的标题看起来太近，可以使用 UIBarButtonSystemItemFixedSpace 在它们之间增加适当的间距。（如需了解更多信息，请参阅 [UIBarButtonItem Class](https://developer.apple.com/library/ios/documentation/UIKit/Reference/UIBarButtonItem_Class/index.html#//apple_ref/doc/uid/TP40007519)）。

**尽可能确保自定义的导航栏外观在整个你的应用中保持一致。**例如，不要将不透明的导航栏和半透明的工具栏组合在一起。同样，最好要避免在同一方向的不同页面中使用不同的导航栏图像、颜色或透明度。

**确保自定义的返回按钮的外观和行为看上去仍然是一个返回按钮。**用户知道，标准的返回按钮可以让他们在信息层级之间原路返回。如果你决定要用自定义图像替代掉系统自带的返回箭头，请确保这是一个自定义的蒙版图层。iOS 会使用蒙版，让按钮标题在过渡为返回箭头期间渐入或渐出。

>要点  
不要创建多节的返回按钮。通常，返回按钮会将用户带到当前页面的父级页面。如果你认为用户只有在显示一个面包屑路径式的多节控件时才不会迷路，那多半意味着你需要扁平化你的信息层级。

**考虑隐藏导航栏，当用户希望把重点放在内容。**如果这样做，一定要保证用户可用一个简单的动作恢复导航栏，比如轻触。

导航栏（和工具栏）可见的地图

![image](images/nav_bar_visible_2x.png)

导航栏（和工具栏）可见的地图	

![image](images/nav_bar_hidden_2x.png)

## 工具栏

工具栏包含了对页面或视图中对象进行操作的控件。

![image](images/mail_toolbar_iphone_2x.png)

![image](images/mail_toolbar_ipad_2x.png)

工具栏：

- 半透明的
- 在iphone上始终在屏幕或视图底部出现，在ipad上也可以在屏幕或视图顶部出现。
- 当键盘出现，用户做一个手势或视图控制器转换到一个垂直的界面时，工具栏可隐藏。

>API备注  
工具栏通常包含于导航控制器（一个管理一系列自定义视图显示的程序对象）中。如需了解更多关于如何在代码中定义一个工具栏的更多信息，请参阅 [Displaying a Navigation Toolbar](https://developer.apple.com/library/ios/documentation/WindowsViews/Conceptual/ViewControllerCatalog/Chapters/NavigationControllers.html#//apple_ref/doc/uid/TP40011313-CH2-SW4) 和 [UIToolbar Class Reference](https://developer.apple.com/library/ios/documentation/UIKit/Reference/UIToolbar_Class/index.html#//apple_ref/doc/uid/TP40006927)。

使用工具栏可以向用户提供一系列当前情境下可用的操作。

**包含当前情境下最常用的指令。**尽可能避免让工具栏提供一些只会偶尔用到的指令。

**考虑使用分段控件，用来切换当前情境中的不同视图或模式。**最好不要在工具栏中使用分段控件来显示应用级任务或模式，因为工具栏对应的就是当前页面或视图。如果你需要让用户在你的应用中接触基本任务、视图或模态窗口，那就使用标签栏作为替代。如需了解更多关于分段控件的信息，请参阅 [Segmented Control](https://developer.apple.com/library/ios/documentation/UserExperience/Conceptual/MobileHIG/Controls.html#//apple_ref/doc/uid/TP40006556-CH15-SW27)；请参阅如需了解更多关于标签栏的信息，请参阅 [Tab Bar](https://developer.apple.com/library/ios/documentation/UserExperience/Conceptual/MobileHIG/Bars.html#//apple_ref/doc/uid/TP40006556-CH12-SW52)。

**如果需要在工具栏中放置超过三个项目，请使用图标。**由于文字按钮通常会比图标更占空间，因此很难做到让文字标题不挤到一起。

**确保文本标题之间有足够间隔。**如果在工具栏中两个或更多按钮之间没有足够的间隔，按钮上的文字就会被挤到一起，而这会让用户很难区分它们。如果工具栏里按钮的标题看起来太近，可以使用 [UIBarButtonSystemItemFixedSpace] 在它们之间增加适当的间距。（如需了解更多信息，请参阅 [UIBarButtonItem Class Reference](https://developer.apple.com/library/ios/documentation/UIKit/Reference/UIBarButtonItem_Class/index.html#//apple_ref/doc/uid/TP40007519)）。


## 工具栏和导航栏按钮

iOS 提供了大量的标准工具栏和导航栏按钮，这些按钮被用在了内置应用当中。如需了解如何设计自定义的条栏目图标，请参阅 [Bar Button Icons](https://developer.apple.com/library/ios/documentation/UserExperience/Conceptual/MobileHIG/BarIcons.html#//apple_ref/doc/uid/TP40006556-CH21-SW1)。工具栏和导航栏上的项目可以使用 [tintColor](https://developer.apple.com/library/ios/documentation/UIKit/Reference/UIBarButtonItem_Class/index.html#//apple_ref/occ/instp/UIBarButtonItem/tintColor) 属性着色。

如需了解表 35-1 中符号名称和按键的对应关系，请参阅 [UIBarButtonItem Class Reference](https://developer.apple.com/library/ios/documentation/UIKit/Reference/UIBarButtonItem_Class/index.html#//apple_ref/doc/uid/TP40007519) 中关于 [UIBarButtonSystemItem](https://developer.apple.com/library/ios/documentation/UIKit/Reference/UIBarButtonItem_Class/index.html#//apple_ref/c/tdef/UIBarButtonSystemItem) 的内容。

>要点  
和所有标准的按钮和图标一样应当根据按钮的含义而不是外观来决定其用途。这样，即便对应着特定含义的按钮改变了样子，你的应用的 UI 仍然可以继续使用。

表37-1 工具栏和导航栏适用的标准按钮

|按钮 	|名称 	|含义   |
|:--------|:----------|:-----------|:----------|	  
|![image](images/UIBarButtonAction_2x.png)    |分享（Action）|打开一个操作菜单，上面列出了针对当前内容，由系统提供或是由应用自定义的操作服务。|
|![image](images/UIBarButtonCamera_2x.png)      |相机（Camera）	|打开一个操作菜单，在相机模式下显示了一个图片选择器|
|![image](images/UIBarButtonCompose_2x.png)     |撰写（Compose）	|打开一个处于编辑模式的新消息视图|
|![image](images/UIBarButtonBookmarks_2x.png)  |书签（Bookmarks）|显示针对此应用的书签|
|![image](images/UIBarButtonSearch_2x.png)     |搜索（Search）	|显示一个搜索框|
|![image](images/UIBarButtonAdd_2x.png)         |新增（Add）	|创建一个新项目|
|![image](images/UIBarButtonTrash_2x.png)       |回收站（Trash）	|删除当前项|
|![image](images/UIBarButtonOrganize_2x.png)    |整理（Organize）	|移动一个项到应用内的目标位置，例如文件夹|
|![image](images/UIBarButtonReply_2x.png)       |回复（Reply）	|发送一个项到另一个位置|
|![image](images/UIBarButtonRefresh_2x.png)     |刷新（Refresh）	|刷新内容（只在必要时使用，尽量自动刷新）|
|![image](images/UIBarButtonPlay_2x.png)       |播放（Play）	|开始播放多媒体或幻灯片|
|![image](images/UIBarButtonFastForward_2x.png) |快进（Fast Forward）|在多媒体或幻灯片播放过程中快进|
|![image](images/UIBarButtonPause_2x.png)      |暂停（Pause）	|暂停多媒体或幻灯片播放（注意，这意味着要保留所处情境）|
|![image](images/UIBarButtonRewind_2x.png)      |快退（Rewind）	|在多媒体或幻灯片播放过程中后退|

除了以上在表 37-1 中显示的按钮外，你也可以在应用中使用系统自带的编辑、取消、保存、完成、重做和撤销等按钮，用来支持编辑或其它类型内容的操作。每个按钮的外观由其标题决定，如需了解符号名称和按钮的对应关系，请参阅 [UIBarButtonItem Class Reference](https://developer.apple.com/library/ios/documentation/UIKit/Reference/UIBarButtonItem_Class/index.html#//apple_ref/doc/uid/TP40007519) 中的 [UIBarButtonSystemItem](https://developer.apple.com/library/ios/documentation/UIKit/Reference/UIBarButtonItem_Class/index.html#//apple_ref/c/tdef/UIBarButtonSystemItem) 。

最后，你也可以在工具栏中使用系统自带的信息按钮。

![image](images/info_button_2x.png)

## 标签栏

标签栏赋予了用户在不同子任务、视图和模态之间切换的能力。

![image](images/music_tab_bar_iphone_2x.png)

![image](images/music_tab_bar_ipad_2x.png)

>API 备注  
标签栏包含于标签栏控制器中，这是一个可以管理一系列自定义视图显示的程序对象。如需了解更多关于如何在代码中定义标签栏的更多信息，参阅 [Tab Bar Controllers](https://developer.apple.com/library/ios/documentation/WindowsViews/Conceptual/ViewControllerCatalog/Chapters/TabBarControllers.html#//apple_ref/doc/uid/TP40011313-CH3) 和 [UITabBars](https://developer.apple.com/library/ios/documentation/UIKit/Reference/UITabBar_Class/index.html#//apple_ref/occ/cl/UITabBar)。

标签栏：

- 半透明的
- 通常出现在屏幕底部
- 横向屏幕同时显示不超过5个标签（如果有更多标签，标签栏会显示其中4个并增加一个更多标签，再将其他的标签以列表形式收纳其中）。
- 标签栏高度不随设备方向改变而改变
- 可以用徽标来显示和应用有关的特有信息（一个红底白字并显示数字或感叹号的椭圆形）

使用标签可以让用户在同一组数据的不同视图中切换，或是在和应用整体功能相关的不同子任务中。

**一般来说，标签栏可以用来在应用层面上组织信息。**标签栏非常适合于应用的主界面中，因为它可以很好地扁平化信息层级，并同时提供了进入多个不同信息分类或模态的入口。

**不要用标签栏来让用户对当前模态或页面上的元素进行操作。**如果你需要为用户提供这些操作，你可以使用工具栏作为替代（如需了解更多使用准侧，请参阅 [Toolbar](https://developer.apple.com/library/ios/documentation/UserExperience/Conceptual/MobileHIG/Bars.html#//apple_ref/doc/uid/TP40006556-CH12-SW4)）。

**在某个标签的功能不可用时，不要移除它。**如果某个标签所代表的部分功能在当前情境下不可用了，相比移除这个标签，更好的做法是显示一个禁用的标语。如果你在某些情况下已处理表亲而其他时候又没有，这会让你的应用的界面变得不稳定且不可预测。最好的解决方案是确保所有标签都可用，但解释标签内容不可用的原因。比如，如果用户的ios设备中没有歌曲，在音乐应用的歌曲标签中就会显示一个页面去说明如何下载歌曲。

**考虑在标签上使用徽标以低调地传达信息。**你可以在标签栏图标上显示徽标来暗示该视图或模态中有信息。

**在横向常规界面中，你可能会在分栏视图或弹出窗口中用到标签栏。**如果这些标签是用于切换或过滤视图内容，你就可以这样做。不过，在弹出窗口或分栏视图窗格的底部使用分段控件效果往往会更好。因为分段控件的外观和分栏视图或弹出窗口的外观更协调（如需了解使用分段控件的更多信息，请参阅 [Segmented Control](https://developer.apple.com/library/ios/documentation/UserExperience/Conceptual/MobileHIG/Controls.html#//apple_ref/doc/uid/TP40006556-CH15-SW27)）。

**避免让过多的标签挤满标签栏。**在标签栏放置过多的标签会让用户很难点中他们需要的标签。每多一个标签，你的应用又多了一份复杂。

**水平常规界面，避免使用更多这一标签。**在水平常规界面运行的应用，专门用一个页面显示一列多余的标签是很浪费空间的。

**尽可能横屏竖屏都显示一样的标签。**横屏竖屏都显示相同的标签可以给用户一种应用的视觉稳定感。横屏方向时，你应该将同样的标签沿屏幕宽度居中。

## 标签栏图标

iOS 为标签栏提供了标准图标，见表 37-2。如需了解如何设计自定义标签栏图标，请参阅 [Bar Button Icons](https://developer.apple.com/library/ios/documentation/UserExperience/Conceptual/MobileHIG/BarIcons.html#//apple_ref/doc/uid/TP40006556-CH21-SW1)。标签栏图标可以使用 [tintColor](https://developer.apple.com/library/ios/documentation/UIKit/Reference/UIView_Class/index.html#//apple_ref/occ/instp/UIView/tintColor)属性着色。

想要了解符号名称和按键的对应关系，请参阅 [UITabBarItem Class Reference](https://developer.apple.com/library/ios/documentation/UIKit/Reference/UITabBarItem_Class/index.html#//apple_ref/doc/uid/TP40006928) 中的关于 [UITabBarSystemItem](https://developer.apple.com/library/ios/documentation/UIKit/Reference/UITabBarItem_Class/index.html#//apple_ref/c/tdef/UITabBarSystemItem) 的文档。

>要点  
和所有标准按钮盒图标一样，你需要根据按钮的语义含义去决定其用途，而不是外观。这会让你的应用的界面符合直觉，即使是相关含义的图标外观被改变了。

下表用于标签栏的标准标签图标

|按钮	|名称	|含义   |
|:--------|:----------|:-----------|:----------|	
|![image](images/UITabBarBookmarks_2x.png)|	书签（Bookmarks）|	显示此应用中的书签|
|![image](images/UITabBarContacts_2x.png)|	联系人（Contacts）|	显示联系人|
|![image](images/UITabBarDownloads_2x.png) |	下载（Downloads）|	显示下载项|
|![image](images/UITabBarFavorites_2x.png) |	收藏（Favorites）|	显示用户的收藏|
|![image](images/UITabBarFeatured_2x.png)|	推荐（Featured）|	显示该应用的推荐内容|
|![image](images/UITabBarHistory_2x.png) |	历史（History）	|显示用户的操作历史|
|![image](images/UITabBarMore_2x.png) |	更多（More）	|显示额外的标签栏项目|
|![image](images/UITabBarMostRecent_2x.png)|	最新（Most Recent）|	显示最新的项目|
|![image](images/UITabBarMostViewed_2x.png)|	最多浏览（Most Viewed）|	显示所有用户中最流行的项目|
|![image](images/UITabBarRecents_2x.png)|	最近（Recents）|	显示在应用规定时间内用户访问的项目|
|![image](images/UITabBarSearch_2x.png )|	搜索（Search）|	进入搜索模式|
|![image](images/UITabBarTopRated_2x.png)|	最高评分（Top Rated）|	显示由用户产生的最高评分项目|

## 搜索栏

搜索栏可以接收用户输入的文本并将其作为一次搜索输入（如下图所示）。

![image](images/search_bar_2x.png)

>API 备注  
如需了解如何在代码中定义搜索栏，请参阅 [UISearch Bars](https://developer.apple.com/library/ios/documentation/UIKit/Reference/UISearchBar_Class/index.html#//apple_ref/occ/cl/UISearchBar)。如需了解有关搜索栏的显示，请参阅 [UISearchDisplayController](https://developer.apple.com/library/ios/documentation/UIKit/Reference/UISearchDisplayController_Class/index.html#//apple_ref/occ/cl/UISearchDisplayController)。

搜索栏可以显示一些可选的元素，如这些:

- 占位符文本。此文本可能会说明这个控件的功能（例如，“搜索”）或者提醒用户在何种搜索情境之下（例如，“Google”）。
- 书签按钮。此按钮可以给用户提供一种快捷方式，再次抵达他们想要轻松找到的信息。例如，地图搜索模式中的书签按钮可以让人访问收藏的位置、最近搜索和联系人。

![image](images/search_bar_bookmarks_2x.png)

书签按钮只在搜索栏中没有用户输入的或非占位符文本时显示。当搜索栏包含这样的文本时，则显示清除按钮以使用户可以清除文本。

- **清除按钮。**大多数搜索栏都包含清除按钮，用户轻点一下就能清除搜索栏中的内容。

![image](images/search_bar_clear_2x.png) 

当搜索栏中包含任意文本时，显示清除按钮以使用户清除文本。如果搜索栏中没有任何用户输入的或非占位符的文本时，则隐藏清除按钮。

- 结果列表图标。此图标用来表示搜索结果。当用户点击这个图标时，应用就显示他们最近搜索的结果。

![image](images/search_bar_results_2x.png)

- **提示语。**一个放置在搜索栏中的描述性标题，称之为提示语。通常来说，提示语是一个简短的句子，以提供引导或搜索栏在应用中所处的情境。

![image](images/search_bar_prompt_2x.png)

使用搜索栏可以在应用中进行搜索。不要用一个文本框表示搜索因为它没有用户预期的搜索栏的样子。

在 iOS8 和更高版本中，使用 [UISearchController](https://developer.apple.com/library/ios/documentation/UIKit/Reference/UISearchController/index.html#//apple_ref/occ/cl/UISearchController) 会让在导航栏中放一个搜索栏变得容易。请注意，搜索视图控制器包含于导航控制器中，当用户进入搜索时，搜索栏会自动在导航栏中渐变呈现，如邮件这个例子一样。

选择一个与应用内搜索功能重要性一致的搜索栏风格。如果在你的应用中搜索是一个基本功能，你可能倾向于使用突显的搜索栏风格；如果在你的应用中用户不需经常进行搜索，你可能就倾向于精简的搜索栏风格。

突显的搜索栏风格（在邮件中显示）

![image](images/search_bar_prominent_2x.png)

精简的搜索栏风格（在音乐中显示）

![image](images/search_bar_minimal_2x.png)

## 范围栏

范围栏随搜索栏一起出现，它允许用户定义搜索范围。

![image](images/scope_bar_2x.png)

>API 备注  
如需了解如何在代码中定义搜索栏和范围栏，请参阅 [UISearch Bars](https://developer.apple.com/library/ios/documentation/UIKit/Reference/UISearchBar_Class/index.html#//apple_ref/occ/cl/UISearchBar)。

当搜索栏出现时，范围栏也会在其附近出现。范围栏的外观会和搜索栏保持一致。

当用户想要在明确定义或清晰分类的范围内搜索时，范围栏会非常有用。当然更好的做法是提升搜索结果质量，让用户不需要对搜索进行筛选。














