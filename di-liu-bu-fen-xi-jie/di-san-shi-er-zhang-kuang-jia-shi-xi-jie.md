# 第三十二章 框架是细节

![](/assets/32/c32.png)

框架已经变得相当流行。一般来说，这是一件好事。有许多框架是免费的，强大的和有用的。但是，框架不是架构，虽然存在一些尝试。

## 框架作者

大多数框架作者免费提供他们的工作成果，因为他们想要对社区有所帮助。他们想要回报。这是值得称赞的。但是，不管他们是否有高尚的动机，这些作者的内心并不是最大化你的利益。他们做不到，因为他们不认识你，也不知道你的问题。

框架作者知道他们自己的问题，以及他们的同事和朋友的问题。他们编写框架来解决这些问题，而不是你的问题。

当然，你的问题很可能会与其他问题重叠。如果情况并非如此，框架也不会如此受欢迎。如果存在这种重叠，框架确实可能非常有用。

## 不对称的“婚姻”

你和框架作者之间的关系是非常不对称的。你必须对这个框架做出巨大的承诺，但框架的作者对你不作任何承诺。

仔细想想这一点。当你使用框架的时候，你可以阅读框架作者提供的文档。在该文档中，作者和该框架的其他用户向你建议如何将你的软件与框架集成。通常，这意味着围绕该框架包装你的架构。作者建议你从框架的基类中派生出来，然后将框架的工具导入到您的业务对象中。作者敦促你尽可能紧密地将你的应用程序连接到框架。

对于框架作者来说，耦合到他或她自己的框架并不是一个风险。作者想要结合这个框架，因为作者对这个框架有绝对的控制权。

更重要的是，作者希望你能够耦合到框架，因为一旦这样耦合，就很难脱离。对于一个框架作者来说，没有什么比一群愿意从作者的基类中不可避免地派生出来的用户更有效的验证了。

实际上，作者要求你嫁给这个框架，对这个框架做出巨大而长期的承诺。然而，在任何情况下，作者都不会对你做出相应的承诺。这是一个单向的婚姻。你承担所有的风险和负担;框架作者根本就没有承担。

## 风险

有什么风险？这里有几个供你考虑。

* 框架的架构往往不是很干净。框架往往违反他的依赖规则。他们要求你将自己的代码继承到你的业务对象——你的实体！他们希望他们的框架耦合到最内圈。一旦进入，该框架不会出来。结婚戒指在你的手指上;它会留在那里。
* 框架可以帮助你应用程序的一些早期功能。但是，随着产品的成熟，可能会超出框架的设施（facilities）。如果你戴上那枚结婚戒指，随着时间的推移，你会发现这个框架不断在打击你（the framework fighting you more and more）。
* 框架可能朝着一个你认为没有帮助的方向发展。你可能会卡住，不升级到对你毫无帮助的新版本。在新版本中，你甚至可以找到一些旧的特性，使用，删除或改变这些方式很难跟得上。
* 一个新的更好的框架可能会出现，你希望你可以切换到。

## 解决方案

解决方案是什么？

> 不要嫁给框架！

哦，你可以使用框架，只是不要耦合它。保持在疏远的距离（Keep it at arm’s length）。将框架视为属于体系结构外围的一个细节。不要让它进入内部圈子。

如果框架要你从它的基类派生你的业务对象，说不！代之以派生代理，并将这些代理保留在作为业务规则插件的组件中。

不要让框架进入你的核心代码。相反，按照依赖规则将它们集成到组件中，组件再插入（plug in）核心代码的。

例如，也许你喜欢Spring。Spring是一个很好的依赖注入框架。也许你用Spring来自动注入你的依赖关系。这很好，但是你不应该在整个业务对象中遍布@autowired注释。你的业务对象不应该知道Spring。

相反，你可以使用Spring将依赖项注入到Main组件中。Main可以了解Spring，因为Main是架构中最脏，最底层的组件。

## 我现在宣布你...

有一些框架，你只需要出嫁。例如，如果你使用C++，你可能不得不与STL结婚，这很难避免。如果你使用的是Java，那么你肯定得与标准库结婚。

这是正常的——但它应该仍然是一个决定。你必须明白，当你将框架结合到你的应用程序中时，你将在把应用程序的其余生命周期托付给该框架。无论好坏，无论疾病还是健康，无论富有还是贫穷，都不离不弃，你将使用这个框架。这不是一个轻言放弃的承诺。

## 小结

当面对一个框架时，尽量不要马上出嫁。看看有没有办法和它约会一段时间，然后再冒险。如果可能，尽可能长时间地将框架放在架构边界之后。也许你可以找到一种方法来买牛奶而不买牛（get the milk without buying the cow）。

