# 临时视图

## 警告框

警告框向用户提示会影响他们使用应用或设备的重要信息。

![image](images/alert_2x.png)

>API 备注  
如需了解在代码中使用警告框的信息，你可以设置一个 [UIAlertController](https://developer.apple.com/library/ios/documentation/UIKit/Reference/UIAlertController_class/index.html#//apple_ref/occ/cl/UIAlertController) 并设定 [UIAlertControllerStyleAlert](https://developer.apple.com/library/ios/documentation/UIKit/Reference/UIAlertController_class/index.html#//apple_ref/c/econst/UIAlertControllerStyleAlert)。

警告框：

- 显示一个必需的标题，和一条可选的消息
- 包含一个或多个按钮

警告出现的少会有助于用户对其认真对待。最好严格控制你的应用里显示的警告框数量，并确保每一个警告框都提供了重要信息和有用的选择。

**避免创建不必要的警告框。**通常来说，警告框在以下这些场景中是不需要的：

|如果警告框用来做这些事情…	|可以这样做来代替警告框… |
|:-------- |:----------|:-----------|  	
|提供与应用的标准功能相关的信息 |	设计一种引人注目但又和你的应用的样式相协调的方式去展示信息。|
|告知用户任务正在正常进行	       | 使用进度视图或活动指示图（Progress View and Activity Indicator）又或将状态信息融入到应用的界面中去。| 
|要求用户对发起的任务进行确认|	使用操作列表（在 Action Sheet）。|

|告知用户他们所不能解决的问题|	如果问题不是很严重，可以将信息放到应用的界面中显示，否则，请使用警告框。|

你将读到的是警告文本设计指南，了解这些定义非常有用：

- 标题大写样式指的是每一个单词的首字母都要大写，除了冠词、并列连词以及少于四个字母且不是第一个单词的介词。

- 句子大写样式指的是第一个单词的首字母需要大写，单词的其余部分小写，除非他们是专有名词或专有形容词。

**简明扼要地描述当前情境，并告诉人们他们可以做什么。**理想情况下，你撰写的文本要给用户足够的情境，让他们理解为什么警告框会出现，以决定点哪个按钮。

**保持标题足够简短，尽可能以一行显示。**冗长的警告标题让人难以快速阅读，而且它还可能会被截断或者让警告消息需要滚动。

![image](images/alert_title_only_2x.png)

**避免一个词的标题。**单个词的标题，比如错误或警告，很少能提供任何有用的信息。

**可能的话，尽量使用短句。**一段简洁清晰的陈述往往比一个完整的句子更容易理解。

**尽可能撰写一个不需要补充说明的标题。**例如，如果你用一个问句，或者偶尔是两个短句，作为警告标题，很可能你可以不需要添加消息说明。

**不要刻意避免使用负面措辞。**用户理解大多数警告框都是为了告诉他们发生的问题，或者对危机情况做出警告。因此，负面但直接的措辞效果会好于正面但委婉的措辞。

**尽可能避免使用“你”、“你的”，“我”和“我的”。**有时候，这些直接指向人们的文本可能会引起歧义，甚至可能会被理解成侮辱或傲慢。

**恰如其分地使用大小写和标点符号。**具体来说：

|当警告框标题… |则使用… |
|:-------- |:----------|:-----------|  
|是一个短句或一个简单但又不是问句的句子|	标题大写样式，且句末没有标点|
|是一个简单的问句	|句子大写样式，以问号结尾|
|由两个或更多的句子组成 |句子大写样式，为每个句子选用合适的结束标点|

**如果必须为警告框提供一条可选的消息正文，请撰写一个简短、完整的句子。**如果可能，尽量让消息足够简短以便能在一两行之间显示。如果消息过长导致警告框出现滚动条，这会给用户以糟糕的体验。在消息中使用句子大写样式，并以合适的标点作为结束。

![image](images/alert_title_with_msg_2x.png)

**避免在警告文本中描述点击哪个按钮从而导致文本过长。**理想情况下，清楚明白的警告文案和合乎逻辑的按钮标题能给人足够的信息去理解当前情况并作出选择。如果你需要提供详细的指引，请遵循以下准则：

- 确保使用“轻点”（而不是“触摸”或“点击”或“选择”）来描述动作选项。
- 不要用引号将按钮的标题括起来，但要保证其首字母大写。

**确保警告框在竖屏和横屏方向上显示正常。**横屏方向中的警告框高度会有所限制，可能会和竖屏方向中的样子不太一样。建议你优化警告文本的长度，以便在两种方向上不用滚动都可以被阅读。

**一般来说，使用两个按钮的警告框。**两个按钮的警告框通常是最有用的，因为对人们来说在两个按钮之间做出选择最容易。单个按钮的警告狂就不那么有用，因为它通常只是提示用户，并没有赋予用户任何对当前状况的控制能力。包含三个或三个以上按钮的警告框明显比双按钮警告框复杂，应该尽可能避免使用。如果你在一个警告况中添加了太多按钮，它会导致警告框要滚动。这将是一种糟糕的用户体验。

![image](images/two_button_alert_2x.png)

>注意  
如果你发现需要向用户提供超过两个的选择，可以考虑使用操作菜单以代替（如需了解如何使用操作菜单，请参阅 [Action Sheet](https://developer.apple.com/library/ios/documentation/UserExperience/Conceptual/MobileHIG/Alerts.html#//apple_ref/doc/uid/TP40006556-CH14-SW36)）。

**合适放置按钮。**理想情况下，最自然的点击按钮应符合两个标准：它执行了用户最想要的操作；即使用户不小心误点也不会造成严重问题。具体来说：

- 如果按钮不会造成破坏性后果，而这又是用户最有可能的操作，那么它应当在双按钮警告框的右边。取消按钮则应该在左边。

- 如果按钮会造成破坏性后果，而这又是用户最有可能的操作，那么它应该放在双按钮警告框的左边。取消按钮则应该放在右边。

>注意  
在警告框显示时点按主屏幕按钮，应如预期的那样退出此应用。这样做的效果类似于轻点取消按钮——即警告框被取消且操作没有被执行。

**为警告框按钮撰写简短而合乎逻辑的标题。**好的按钮标题一般只有一到两个词，描述了轻点按钮后的结果。当你在创建警告框按钮的标题时，请遵循下面这些准则：

- 和所有的按钮标题一样，使用标题大写样式且句末没有标点符号。
- 使用和警告框文本直接相关的动词和动词短语——例如，“取消”、“查看所有”、“回复”或“忽略”。
- 如果没有更好的选择，使用“好”（OK）作为简单的接受选项。避免使用“是”或“否”。
- 尽可能避免使用“你”、“你的”，“我”和“我的”。使用这些词语的标题往往会引起歧义还可能造成冒犯。

## 操作菜单

操作菜单显示与用户所发起的任务直接相关的一系列选项。

横屏方向下，操作菜单从屏幕底部出现

![image](images/action_sheet_iphone_2x.png)

竖屏方向下，操作菜单通常会在弹出窗口中显示

![image](images/action_sheet_ipad_2x.png)

>API 备注
在代码中使用操作菜单，你可以定义一个 [UIAlertController](https://developer.apple.com/library/ios/documentation/UIKit/Reference/UIAlertController_class/index.html#//apple_ref/occ/cl/UIAlertController) 并设置 [UIAlertControllerStyleActionSheet](https://developer.apple.com/library/ios/documentation/UIKit/Reference/UIAlertController_class/index.html#//apple_ref/c/econst/UIAlertControllerStyleActionSheet)。

操作菜单:

- 作为用户操作的结果出现
- 显示两个或两个以上的按钮

使用操作菜单可以：

- **提供完成一项任务的不同方法。**操作列表让你可以提供在当前任务情境中奏效的一系列选项，而且这些选项不会永远在UI中占据位置。

- **在完成一个有潜在风险的任务前获得用户确认。**操作菜单让用户可以去考虑他们的下一步操作可能带来的潜在风险，并为他们提供一些替代方案。

**在横屏下，要放置取消按钮以便使用户可以轻松但安全地放弃任务。**将取消按钮放置在操作列表的底部，有利于用户在选择前通读所有选项。

**在竖屏下，基于用户发起任务的方式来决定操作列表的显示方式。**如下：

|如果任务从以下情境中发起… |	则显示操作列表时… |	是否包含取消按钮？ |
|:-------- |:----------|:-----------| 
|从弹出窗口外	|不需要动画——即操作列表和弹出窗口同时出现 |	否，因为用户可以在弹出窗口以外轻点就能让操作列表消失 |
|在弹出窗口中	|需要动画——即操作列表从弹出窗口内容的顶端滑出|	是，因为用户希望不用关闭弹出窗口也能取消操作列表     |

**无论在何种设备上，均使用红色来标识那些执行潜在破坏性操作的按钮。**在操作列表顶部显示红色按钮，因为越靠近操作列表顶部的按钮越容易引人注意。

![image](images/action_sheet_red_button_2x.png)

**避免让用户滚动操作列表。**如果你的操作列表中存在太多按钮，用户必须要滚动才能看完所有选项。这对用户来说是一种烦躁的体验，因为他们必须花更多的时间来分辨这些选项。同样，用户在滚动时很可能会误点某个按钮。

## 模态视图

模态视图——是一个以模态形式展现的视图，它为当前任务或情境提供自包含（self-contained）的功能。

![image](images/modal_view_mail_compose_2x.png)

>API备注  
在你的代码中使用模态视图，可以定义一个 [UIPresentationController](https://developer.apple.com/library/ios/documentation/UIKit/Reference/UIPresentationController_class/index.html#//apple_ref/occ/cl/UIPresentationController) 并设置合适的样式（更多样式，请参阅 [Modal Presentation Styles](https://developer.apple.com/library/ios/documentation/UIKit/Reference/UIViewController_Class/index.html#//apple_ref/c/tdef/UIModalPresentationStyle)）。

模态视图:

- 占据整个屏幕，也可能会占据整个父视图的区域（例如一个弹出窗口）或者占据屏幕的一部分
- 包含完成任务所需的文本和控件
- 通常显示一个完成任务并退出视图的按钮，和一个放弃任务并取消视图的取消按钮

当需要完成和你的应用的基本功能相关的自包含任务时，你可以使用模态视图。模态视图尤其适用于那些所需元素在应用的主要界面中并非一直出现且有多个步骤的子任务。

**选择一种适合当前任务以及应用视觉风格的模态视图样式。**你可以使用如下定义的任何一种样式：

<table>		+|模态视图样式	|外观	|推荐用于  |
<tr>		+|:--------|:----------|:-----------| 
<th width="140" align="left" >模态视图样式</th>		+|全屏	|   占据整个屏幕。	|呈现一个较为复杂的任务，用户可以在模态视图情境内部完成这个任务。|
<th align="left" >外观</th>		+|页面列表|	在横屏时，采用部分包含基本内容的视图。未包含的区域变暗，防止用户与其进行交互。（横屏时，与全屏视图的效果相同） |	呈现一个较为复杂的任务，用户可以在模态视图情境内部完成这个任务。|
<th align="left" >推荐用于</th>		+|表格列表|	在横屏时，在屏幕上居中对齐。未包含的区域变暗，防止用户与其进行交互。在某些情况下，键盘出现时模态视图的位置进行调整。（横屏时，与全屏视图的效果相同）|	从用户那里获取结构化信息|
</tr>		+|当前情境|	使用与父视图一样的尺寸	      |    在分栏视图窗格、弹出窗口或其他非全屏视图内部显示模态内容|
<tr>		
<td>全屏</td>		
<td>占据整个屏幕。</td>		
<td>呈现一个较为复杂的任务，用户可以在模态视图情境内部完成这个任务。</td>		
</tr>		
<tr>		
<td>页面列表</td>		
<td>在横屏时，采用部分包含基本内容的视图。未包含的区域变暗，防止用户与其进行交互。（横屏时，与全屏视图的效果相同）</td>		
<td>呈现一个较为复杂的任务，用户可以在模态视图情境内部完成这个任务。</td>		
</tr>		
<tr>		
<td>表格列表</td>		
<td>在横屏时，在屏幕上居中对齐。未包含的区域变暗，防止用户与其进行交互。在某些情况下，键盘出现时模态视图的位置进行调整。（横屏时，与全屏视图的效果相同）</td>		
<td>从用户那里获取结构化信息</td>		
</tr>		
<tr>		
<td>当前情境</td>		
<td>使用与父视图一样的尺寸</td>		
<td>在分栏视图窗格、弹出窗口或其他非全屏视图内部显示模态内容</td>		
</tr>		
</table>

**不要在弹出窗口底部显示模态视图。**除警告外，没有任何元素显示在弹出窗口之上。在极少数情况下，用户在弹出窗口进行的操作结果必须要以模态视图展现，那也请在模态视图出现前先将弹出窗口关闭。

**确保模态视图的整体外观与你的应用的外观相协调。**例如，模态视图常常包含一个导航栏，而导航栏又包含标题和取消完成视图任务的按钮。在这种情况下，模态视图的导航栏应当使用和应用导航栏相同的外观。

**如果合适，在所有设备上都显示一个说明任务内容的标题。**你也许还需要在视图的其它区域中显示文本，以完整描述任务内容或一些指引。

**在所有设备上，选择一个合适的转场样式来展现模态视图。**使用和你的应用相协调的转场样式，可以提升用户对模态视图所代表的临时情境转换的感知，要做到这一点，你可以从以下转场样式中选择一个：

- **垂直型。**在垂直样式中，模态视图会从屏幕底部向上滑入，在被取消时向下滑出（这是默认的转场样式）。

- **翻转型。**在翻转样式中，当前视图从右至左水平翻转，随之显示模态视图。从视觉上来说，模态视图看上去像是当前视图的背面。当模态视图被取消时，它会从左至右翻转，随之显示之前的视图。

**如果你在应用中改变当前模态视图的转场样式，请确保这种改变对用户有价值。**用户很容易就能注意到应用中的行为变化，并且会认为这些变化的特别含义。因此，最好是建立一种合乎逻辑并保持一致的范式，让用户可以轻松感知并记忆。在没有充分理由时，避免改变转场样式。




