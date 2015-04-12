# 云打印 (AirPrint)

用户可以通过 AirPrint 无线打印 app 上的内容，并且可以在打印中心查看打印进度。

![](images/print_options_2x.png)

你可充分利用内置的图片、PDF 打印技术的优点，或者你可以用特定的打印程序界面来自定义格式。ios 在被选中的打印机中解决打印的启动、调度和执行问题。

一般来说，当用户想打印东西的时候，他们会点击你 app 中的动作按钮。他们会先选择要打印的内容，然后选择打印机，设定打印参数，最后点击打印按钮。

用户可以在“打印中心”里查看打印进度，这是一个只能在打印进程中使用的系统应用。在“打印中心”，用户可以查看打印队列，查看某个打印任务的具体信息，也可以取消打印。

在你的应用中，你可以通过添加相对较少的额外代码来实现打印功能。（想了解更多关于如何添加打印功能，请点击 [Drawing and Printing Guide for iOS](https://developer.apple.com/library/ios/documentation/2DDrawing/Conceptual/DrawingPrintingiOS/Introduction/Introduction.html#//apple_ref/doc/uid/TP40010156)）

**使用系统提供的动作按钮。**用户熟悉系统这类按钮的含义和功能，所以请尽量使用它。如果你的 app 中不含工具栏或导航栏，那么你可以不这么做。你需要自己设计打印按钮，因为系统的动作按钮只可以在工具栏和导航栏里使用。

**当打印在当前环境下是主要任务时再显示打印内容。**当打印内容不适宜出现在当前页面，或者用户现在不需要打印时，不要显示出打印列表。

**在合适的地方给用户提供额外的打印选择。**例如，你可以允许用户选择打印页码或打印多份。

**如果用户不能打印，不要显示打印用的 UI 图标。**却确保知道用户的设备是否支持打印功能，如果不能，就不要显示打印图标。想了解更多关于如何写这部分的代码，请点击 [UIPrintInteractionController Class Reference](https://developer.apple.com/library/ios/documentation/UIKit/Reference/UIPrintInteractionController_Class/index.html#//apple_ref/doc/uid/TP40010141)
