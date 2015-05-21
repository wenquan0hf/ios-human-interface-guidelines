# 图标与图片尺寸

每一个应用都需要一个图标以及一个启动文件或图片。此外，一些应用还需要在导航栏、工具栏或标签栏中使用自定义的图标，来传达应用独特的内容、功能及模式。

与自定义应用的其他界面设计不同，应用中使用的图标与图片必须严格遵从特定的标准，才能够在 iOS 上良好的呈现出来，在下面的表格中给出了在不同设备上对这些文件的尺寸规定。此外，图标和图片文件都有严格的命名要求（了解学习关于命名这些文件的方法，可查阅[应用图标](https://developer.apple.com/library/ios/documentation/iPhone/Conceptual/iPhoneOSProgrammingGuide/ExpectedAppBehaviors/ExpectedAppBehaviors.html#//apple_ref/doc/uid/TP40007072-CH3-SW1)和[应用默认图片](https://developer.apple.com/library/ios/documentation/iPhone/Conceptual/iPhoneOSProgrammingGuide/ExpectedAppBehaviors/ExpectedAppBehaviors.html#//apple_ref/doc/uid/TP40007072-CH3-SW3)）。

下表自定义图标和图片的尺寸（以像素为单位）

| 属性 | iPhone 6 Plus (@3x)| iPhone 6 and iPhone 5 (@2x)| iPhone 4s (@2x) | iPad and iPad mini (@2x) | iPad 2 and iPad mini (@1x)|
|:--- |:---|:---|:---|:---|:---|
|应用图标（所有的应用都必须严格遵从）|180 x 180 | 120 x 120| 120 x 120| 152 x 152| 76 x 76|
|App Store 中的应用图标（所有的应用都必须严格遵从）|1024 x 1024|1024 x 1024|1024 x 1024|1024 x 1024|1024 x 1024|
|启动文件或图片（所有的应用都必须严格遵从）|使用启动文件参见[启动文件](https://developer.apple.com/library/ios/documentation/UserExperience/Conceptual/MobileHIG/LaunchImages.html#//apple_ref/doc/uid/TP40006556-CH22-SW1)|对于 iPhone 6， 使用启动文件参见[启动文件](https://developer.apple.com/library/ios/documentation/UserExperience/Conceptual/MobileHIG/LaunchImages.html#//apple_ref/doc/uid/TP40006556-CH22-SW1)；对于 iPhone 5， 640 x 1136|640 x 960|1536 x 2048 (人像) 2048 x 1536 (风景)|768 x 1024 (人像) 1024 x 768 (风景)|
|显示在 Spotlight 搜索结果中的图标（建议尺寸）|120 x 120|80 x 80|80 x 80|80 x 80|40 x 40|
|显示在设置中的图标（建议尺寸）|87 x 87|58 x 58|58 x 58|58 x 58|29 x 29|
|工具栏和导航栏中的图标（参考尺寸）|约 66 x 66|约 44 x 44|约 44 x 44|约 44 x 44|约 22 x 22|
|标签栏中的图标 (参考尺寸)|约 75 x 75 (最大允许： 144 x 96)|约 50 x 50 (最大允许：96 x 64)|约 50 x 50 (最大允许： 96 x 64)|约 50 x 50 (最大允许： 96 x 64)|约 25 x 25 (最大允许： 48 x 32)|
|默认的 App Store 中的报刊杂志封面图标（所有的报刊杂志应用都必须严格遵从）|最长边至少 1024 像素|最长边至少 1024 像素|最长边至少 1024 像素|最长边至少 1024 像素|最长边至少 512 像素|
|网页收藏夹中的图标（建议网页应用和网站使用）|180 x 180|120 x 120|120 x 120|152 x 152|76 x 76|

对于所有的图片和图标，建议使用 PNG 格式。但避免使用交错的 PNG 格式。

所有图片和图标的标准 bit 深是 24 bits，即红绿蓝分别 8 bits，加上一个 8-bit 的alpha 通道，总共为 32 bits。

你不需要将你的色板选择限制在对于网页是安全的颜色区块中。
