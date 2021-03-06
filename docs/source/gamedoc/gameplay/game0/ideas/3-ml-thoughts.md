# 有关 AI 训练的三个想法

```{admonition} 作者
&emsp;&emsp;早起侠
```

&emsp;&emsp;这些想法还⽐较初步。  
&emsp;&emsp;想多交流、看⼀下反馈，再看之后怎么⾛。

## 1. 加⼊更多连续的⾏为，代替⼀些离散的⾏为

&emsp;&emsp;连续的⾏为，就像现在游戏中的移动，可以移动0.1，0.3，1.2等等。  
&emsp;&emsp;离散的⾏为，就像现在游戏中的攻击、闪避、跳跃，按⼀下执⾏⼀次。

### 可⾏的⽅案：

&emsp;&emsp;把攻击、跳跃替换为类似于蓄⼒的模式。  
&emsp;&emsp;攻击中，射箭⽐较容易设计。⽐如射箭的距离&伤害 和 蓄⼒的时间 有关，最⼤蓄⼒2s。  
&emsp;&emsp;近战攻击不那么好设计，想到的1个是——蓄⼒时间与伤害有关；再进⼀步，可能要超出常规的设计，不⼀定好，⽐如按键事件决定挥⻓⽭的时候挥动到多远距离，或者⼀个系列动作完成到多少⽐例。  
&emsp;&emsp;跳跃，我没太好的想法。⼀个是，两段跳，由于第⼆次跳可以有不同的时间点，也许能带来些东西。第⼆个是，蓄⼒后跳得⾼、跳的久，我也觉得有些奇怪。

### 这样想的原因：

&emsp;&emsp;我这样想，第⼀个原因是，我觉得，在我们游戏中，⼩⼈是模仿or学习我的⾏为，如果我的⾏为是离散的，那它能学的、我能教的东西好像⽐较有限。在这种情况下，可能更容易体现游戏的⼀些缺点，⽐如，因为它学习的⽅式和我认为的不⼀样，他就⼀直学不会我的想法。如果把⾏为变成连续的，好像玩家可以调配的空间⼤⼀些，也许⼀条路不⾏还有另⼀条路。  
&emsp;&emsp;第⼆个原因，和第⼀个类似。我和建建沟通时，他的⼀个想法是增加策略性。我觉得把⾏为连续化，也许可以增加策略性，⽐如射箭的时候，我站位的距离和射箭的蓄⼒时间，就 可以成为⼀个策略因素。

### 其他：

&emsp;&emsp;我看的那篇⽂章（https://zhuanlanzhihu.com/p/89607509）⾥有说道，决策树有两种，(1)分类树，输出为离散值、(2)回归树，输出为连续值。  
&emsp;&emsp;看起来连续的⾏为是有可能的。但我也不太懂这个，不确定具体时间中的困难。

## 2. 不同的性格

&emsp;&emsp;我们游戏的机器学习，和我原来认识的机器学习不太⼀样。（当然，这很⼤程度是因为我对机器学习的了解很少）  
&emsp;&emsp;我的认识主要来⾃于AlphaGo的新闻。我想象的，机器学习这个东西有模仿，但还有反馈，它根据反馈去调整⾃⼰的⾏为，像是AlphaGo⾃⼰和⾃⼰下棋什么的，还可以超越他所模仿的⼈类。  
&emsp;&emsp;我们的游戏，它通过决策树来模仿我的⾏为，没有反馈的部分。

&emsp;&emsp;从这⾥出发，我产⽣的⼀个想象是：我是⼀个幼⼉园⽼师，我带着3个⼩朋友，带他们学习、练习，让他们⾃⼰去打败敌⼈。  
&emsp;&emsp;⼀个意思是，我觉得这个游戏⾥的⼩⼈，可以有⼀些笨笨的、可爱的⻛格。（这可能并⾮我⾃⼰的想法，游戏现在有些这样的⻛格，促使我去这么想。）我觉得，它既然是模仿我的⾏为，那就不可能模仿得完全⼀样，会有些出⼊——玩家也许会觉得，我做的挺好的，为什么他学习出来却不够好呢。通过把游戏⾥的⼩⼈塑造得笨笨的、可爱的，产⽣⼀种预期，让玩家更容易接受它们最后模仿出来的效果。 

&emsp;&emsp;第⼆个意思是说，我觉得，如果做机器学习的算法，准确可能是⽆⽌境，不容易做到的。所以尝试去做⻛格化，也许更能带来趣味。我们的算法有特点，是容易理解的，玩家在⼀定程度上可以预测、掌握。更近⼀步，就是为3个游戏⻆⾊，设置⾏为，也就是机器学习算法的特点。⽐如说，⼩红把⽼师的动作看作跳舞⼀样，她倾向于完全按照⽼师的时间顺序去完成动作，⽼师每⼀步做什么，她就做什么；⼩绿觉得，⽼师是在和怪兽对抗，怪兽 做⼀个⾏为，⽼师会相应的做什么⾏为，我要学习这个。⼩⻩觉得，⽼师有很多招式，所谓招式，就是动作的序列 - ⼀个动作之后，下⼀个动作是什么，⼩⻩要学会⽼师的招式。

&emsp;&emsp;总的来说，“我是⼀个幼⼉园⽼师，我带着3个⼩朋友，带他们学习、练习，让他们⾃⼰去打败敌⼈”这个想象是主要意思和出发点；具体实现时，不过多追求算法的准确，把机器学习算法的特点和性格、学习⽅式联系起来，去尝试设计。

### 问题

&emsp;&emsp;这个想法有些不落地。  
&emsp;&emsp;在⼩红、⼩绿、⼩⻩举例时，我尝试尽量去落地，但其实例⼦不怎么好，⽐如“⼩红倾向于完全按照⽼师的时间顺序去完成动作”，不太机器学习，像是录像。  
&emsp;&emsp;把性格和算法⽐较好的结合，可能很难。我也需要更多地了解机器学习算法。  
&emsp;&emsp;不过，也许你们看完这段，能有些什么好的想法呢？

## 3. ⼈物间的配合

&emsp;&emsp;没有看到demo的时候，我觉得“配合”是编程游戏⾥⼀个很有搞头的事情。  
&emsp;&emsp;看了demo后，我看他们是在模仿，同时还没有互相之间的交互，我觉得搞配合可能不靠谱，成本太⾼。  
&emsp;&emsp;了解了⼀点机器学习的算法之后，我⼜觉得，好像做配合的成本不⾼，把⼀些条件加到training⾥就可以了。  
&emsp;&emsp;我的⼀个想法是，配合可以搞出⼀种迭代学习的感觉。  
&emsp;&emsp;我先训练A。  
&emsp;&emsp;然后训练B，在训练B的时候，A按照之前的训练成果去⾏动；训练B的过程中，B既有⾃⼰的特点，也会去配合A。  
&emsp;&emsp;训练完B之后，我可以再回来训练A，A再尝试去配合B。再训练B。  
&emsp;&emsp;如此反复，直到满意或过关。

&emsp;&emsp;⼀个不太好的例⼦（可能成本⽐较⾼，可⾏性低；但能说明我的意思）：  
&emsp;&emsp;⼀个⼸⼿和⼀个盾⼿。⼸⼿输出，盾⼿则是举盾保护2个⼈。  
&emsp;&emsp;但是，⼸⼿射箭的时候，盾⼿不能举盾，这样箭就射不去除了，会弹回来。  
&emsp;&emsp;训练⼸⼿，⼸⼿配合敌⼈的移动，移动和射箭。  
&emsp;&emsp;之后训练盾⼿，盾⼿需要保护⼸⼿，于是他需要配合⼸⼿移动、举盾。  
&emsp;&emsp;再训练⼸⼿（之前的⾏为还不够完善），有了盾⼿的保护，⼸⼿的射箭&emsp;&emsp;和移动⾏为也发⽣相应的变化，⽐如盾⼿有时没有保护好，⼸⼿就主动寻找盾⼿，或是在举起盾的时候，就不射箭了了。  
……

### 问题

&emsp;&emsp;这个想法也有落地的问题。  
&emsp;&emsp;不过我⾃⼰说起来，感觉好像挺有搞头的。

## 4.后续

### 反馈

* **1、加⼊更多连续的⾏为，代替⼀些离散的⾏为**  
&emsp;&emsp;学习连续⾏为可以⽤回归预测的算法来做到的，可以学习出（条件 → 数值）的计算逻辑，但是最终应⽤效果要我们做出 demo 来才判断得了，是可以考虑的。我们可以同时学习⽣成两个模型⼀个是（条件 → ⾏动），⼀个是特定动作下的（条件 → 数值）。
* **2、不同的性格**  
&emsp;&emsp;游戏做成笨笨的、可爱的⻛格，这个主意我有想过，因为 AI 学出来的⼀定是显得很⽐真⼈笨的。要不我们就纯把 AI 学习这块玩法拿出来做⼀个纯 AI 格⽃的⼩游戏，内容体量再做⼩⼀点出⼀个⼩型的游戏附加 AI ⽹络分享功能。
* **3、⼈物间的配合**  
&emsp;&emsp;这个主意也没问题，就是需要调试算法和看看表现。没做成可玩的 demo 我现在也没法判断是否能⾏。不过增加学习的变量会带来的问题是需要更多的训练数据记录才能通过算法总结出 AI 逻辑规则。更多的训练数据就需要玩家进⾏更多的重复游戏次数。

&emsp;&emsp;第2点再补充⼀点就是做成萌系的⻛格，游戏设定就可以做得更轻松随意⼀些，背景故事什么的就可以不⽤那么操⼼。只要游戏⻛格做得很可爱就没问题了。

### 训练时的数据采集

&emsp;&emsp;每次玩家按下按键动作执⾏成功都会采集⼀次数据。  
&emsp;&emsp;因为采集的是(条件 → 动作)的⼀组数据。每次动作发⽣都需要采集。  
&emsp;&emsp;但是玩家停⽌操作进⼊idle动作的数据不做采集。还有demo⾥没有采集⾏⾛动作的数据。因为在⾃动战⽃阶段，向敌⼈移动被做成了⼀个默认AI。
