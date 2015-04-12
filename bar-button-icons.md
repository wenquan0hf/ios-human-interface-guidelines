#栏按钮图标

iOS 定义了很多标准的栏按钮的图标，如刷新、开始、增加及收藏。你应该尽量使用这些标准按钮和图标来定义应用中一些标准的任务。（学习更多有关可以使用的标准按钮和图标，参见 [Toolbar and Navigation Bar Buttons](https://developer.apple.com/library/ios/documentation/UserExperience/Conceptual/MobileHIG/Bars.html#//apple_ref/doc/uid/TP40006556-CH12-SW33) and [Tab Bar Icons](https://developer.apple.com/library/ios/documentation/UserExperience/Conceptual/MobileHIG/Bars.html#//apple_ref/doc/uid/TP40006556-CH12-SW34)。）

若应用中所包含的任务或模式不能仅仅通过标准图标来呈现，或者这些标准的图标与你的应用的风格不符合，你可以设计自己的栏按钮图标。在设计时，你需要最大限度地满足以下要点：

- **简单的线性图标。**太多的细节会让一个图标显得令人不舒服且难以辨认。
- **不容易被误认为是系统提供的图标。**用户应该能够很轻易地辨认你的图标和系统图标。
- **易于理解和接受。**创建一个大多数用户都能正确理解的图标，不要让用户感到这个图标太过侵略性。

>重要  
避免在设计中使用 Apple 产品的复制图片，这些标志都是具有版权的，并且由于这些标志的设计会频繁地更新，基于它们而设计的图标很快就会显得过时。

不论你是只使用自定义图标还是将自定义图标与标准图标混合使用，应用中的所有图标都应该在尺寸感觉、细节层次以及视觉权重上看起来具有一致性。

例如，观察 iOS 的栏图标，可以发现尺寸、细节以及权重的相似性会呈现一种整体的和谐感。

![image](images/icon_family_2x.png)

要创建一组图标，一致性是关键：尽可能让每个图标都使用相同的透视效果及相同的权重。为了保证所有的图标从感觉上有一致的大小，你需要创建一些实际尺寸不同的图标。例如，下面展示的系统提供的图标集，即使 Favorites 和 Voicemail 的图标实际上会比其他三个图标要大，但还是让人感觉所有图标具有相同的大小。

![image](images/balanced_icons_2x.png)

当你在设计一个自定义的标签栏图标时，你需要考虑两种版本：一种表示未选中状态，一种表示选中状态。选中状态的图标通常是将未选中进行填充，但在设计时这种方法往往需要一些变通。

![image](images/invert_or_fill_2x.png)

创建一个内部有一些细节的图标的填充版本时（如 Radio 图标），将细节部分颠倒，确保选中状态可以保持这些细节。Keypad 图标也拥有一些内部细节，但如果在创建选中状态时，将它的背景部分进行填充，而每个圆圈加上白色的边缘，就会变得很难理解。

![image](images/alternate_design_2x.png)

有时，在设计选中状态时，添加一些细微的变动会有更好的效果。例如，Timer 和 Podcasts 图标都包含一些开放的区域，而对于选中状态，将图标缩小一个 bit 放入一个封闭的圆中反而会有更好的效果。

![image](images/thicker_stroke_2x.png)

如果一个图标填充后会变得难以辨认，那就使用深的描边来表现选中状态，例如 Voicemail 和 Reading List 图标的选中状态就是将原来未选中时的 2 像素的描边增加到了 4 像素。

![image](images/filled_in_both_states_2x.png)

有的图标的形状的细节在增加描边后会变得分辨不清，如 Music 和 Artists 图标，这时，未选中和选中状态都可以使用填充模式，但选中状态的填充应比未选中状态更深，且使用颜色填充，这样一来用户便能很容易的从外观上区别这两个状态。

为工具栏、导航栏、标签栏所创建的自定义图标也称之为模板图片，iOS 会使用这些图片来制作应用运行时的一些图标。如果你创建了一个用颜色填充的模板图标，iOS 会忽视这些颜色。

设计自定义栏图标时，你需要遵循一下守则：
- 使用带有合适的透明度的纯白色
- 不要使用阴影
- 使用图形保真

如果你想要设计一个看起来与 iOS 的图标集类似的图标，那么在设计时为你的图标添加一条非常细的描边。对于细节丰富的图标，使用 2 像素的描边（高分辨率）会有较好的效果，而对与无过多细节的图标，可以使用 3 像素的描边。

不论是何种样式的图标，都要严格按照 表 [41-1](https://developer.apple.com/library/ios/documentation/UserExperience/Conceptual/MobileHIG/IconMatrix.html#//apple_ref/doc/uid/TP40006556-CH27-SW2) 来创建自定义工具栏、导航栏、标签栏的图标。

不要在自定义的标签栏图标中包含文本，而是使用标签栏元素的 API 来为每一个标签设置标题（如 [initWithTitle:image:tag:](https://developer.apple.com/library/ios/documentation/UIKit/Reference/UITabBarItem_Class/index.html#//apple_ref/occ/instm/UITabBarItem/initWithTitle:image:tag:)）。同时，使用标题调整 API 来调整标题的自动布局（如 [setTitlePositionAdjustment:](https://developer.apple.com/library/ios/documentation/UIKit/Reference/UITabBarItem_Class/index.html#//apple_ref/occ/instm/UITabBarItem/setTitlePositionAdjustment:)）。
