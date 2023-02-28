## 项目描述
Remix 项目是一个丰富的工具集，可用于任何知识水平的用户的整个合约开发过程，并可作为以太坊教学和实验的学习实验室。该项目由以太坊基金会资助。

#### 网站
- [在线IDE](https://remix.ethereum.org/)：Remix Online IDE 是一个无需设置、开箱即用且自带图形界面的智能合约开发环境。[以太坊 github 主页](https://github.com/ethereum)置顶的五个仓库中其中一个就是 [Remix Online IDE 的仓库](https://github.com/ethereum/remix-project)，足见其在以太坊生态中的重要性。
- [开发文档](https://remix-ide.readthedocs.io/en/latest/index.html)：这是 Remix IDE 的使用文档。这里面非常详细的介绍了每个功能模块的使用方法。
- [官方网站](https://remix-project.org/)：这是 Remix 项目官网，里面介绍了 IDE、插件、开发库，还有 Remix 团队的介绍，还有他们举办过的一些活动等等。

#### 自媒体
- [Twitter](https://twitter.com/EthereumRemix)：更新 Remix 项目的动态
- [YouTube](https://www.youtube.com/channel/UCjTUPyFEr2xDGN6Cg8nKDaA)：都是些两三分钟的短视频。每个视频会介绍 Remix IDE 上的一个小功能点。
- [Medium](https://medium.com/remix-ide)：Remix 团队的博客。大概每个月会更新一篇。


#### 交流群
- [ethereum/remix](https://app.gitter.im/#/room/#ethereum_remix:gitter.im)：通用交流群。使用 Remix 碰到什么问题都可以在这个群里问。
- [ethereum/remix-dev](https://app.gitter.im/#/room/#ethereum_remix-dev:gitter.im)：开发交流群。给 Remix 项目贡献代码的人，如果有什么开发相关的问题会在这里问。
- [ethereum/remix-workshop](https://app.gitter.im/#/room/#ethereum_remix-workshop:gitter.im)：专门用来交流 workshop 相关的一些事情
- [ethereum/remix-dev-plugin](https://app.gitter.im/#/room/#ethereum_remix-dev-plugin:gitter.im)：交流插件开发的一些事情

Remix 项目的网站在外网上，访问速度比较慢，有时候还会被墙。至于自媒体和交流群，那是完全被墙。在国内没有小飞机的情况下用 Remix 是很难受的。而且就算用了小飞机，那也是一个全英文的使用环境，对国人来说还是很不友好。

Remix China 项目就是为了帮助中文用户更好的使用 Remix 。目前这个项目由普朗克社区提供资金和人力的支持。

我们会对 Remix 项目进行全面的中文化，并且在国内部署镜像站。我们还会组建中文的自媒体和交流群。只要是对中文用户使用 Remix 有帮助的事，我们都会去做。


## 开发工作

#### i18n feature

这个就是把网页上的文案用 i18n 组件替换掉。只有先做了这一步，接下来才能把文案翻译成中文。

开发范围：

1. Remix IDE
2. Remix IDE 插件
3. Remix IDE 官网

#### Remix Fork

要在国内部署 Remix 的镜像站的话，不是说直接把网站的静态文件往国内服务器上一放就可以了的。因为 Remix 代码中有些静态文件是直接通过链接的形式引用的。其中就有 google、github、cloudflare 的链接。这些都有被墙的风险。所以需要开发并维护一个国内的分支，保证所有静态文件都从国内的服务器上获取。

开发范围：

1. Remix IDE
2. Remix IDE desktop
3. Remix IDE 官网

至于 Remix IDE 插件具体要怎么处理，我还没想好。插件目前是30个。按照开发团队分可以分俩类

1. 官方插件，也就是 Remix 团队开发的
2. 第三方插件，也就是第三方开发的

按照集成方式分也可以分成两类

1. 内部集成，就是直接写在 Remix 代码库里的，这些都是官方插件
2. iframe 集成，就是有独立的代码库，独立的服务地址，这些插件既有官方的，也有第三方的

Remix 自己有一个 IPFS 网关，他们把自己开发的 iframe 插件都放在 IPFS 上面，然后通过自己的 IPFS 网关来访问。这个网关我试了下国内能访问，但同样有被墙的风险。所以我在考虑要不要在国内搞一个 IPFS 节点和网关。但我不清楚这会不会被封。

至于那些第三方插件，基本都用的国外的服务器，同样有被墙的风险，是否需要为这些插件都在国内部署镜像。这个我也还没想好。



## 翻译工作

#### 文案

这部分工作我之前都是和 i18n 放一起的。因为就我一个人，我开发了 i18n ，顺手就把文案给翻译了。但要社区协作的话肯定不能这么干了。我会先开发 i18n ，然后把英文文案放到 crowdin 上。crowdin 是一个多人协作的翻译平台。每个人都可以提交自己的翻译，也可以审核别人的翻译。

翻译范围：

1. Remix IDE
2. Remix IDE 插件
3. Remix IDE 官网

#### 文档

这个就是 Remix IDE 的文档，也在 crowdin 上。我之前翻译了几个核心模块，估计有个一小半吧。

#### 文章

就是 Remix 团队发布在 Medium 上的文章

## 短视频制作

Remix 团队有一个 YouTube 账号，上面都是两三分钟的短视频。每个视频都会介绍 Remix IDE 上的一个小功能点。我的想法是我们在国内自己做视频，然后发布到国内的平台上。而且我还想再进一步，把英文视频的活也给揽过来。因为我感觉 Remix 团队似乎安排不出人手来做这个事。之前 Remix 团队就有和我商量过，问我能不能帮他们做视频，用中文讲也没关系，他们自己会去做英文配音。现在他们 YouTube 上有一个视频就是我做的，然后是 Remix 团队中的 Rob 配的音。就是下面这个链接。

https://www.youtube.com/watch?v=2OAx2UoLYEI

我在想我们社区里有没有英文比较好的小伙伴能把这个英文配音的事儿给做了。我们也能顺势多要点钱。



## 自媒体与交流社区

这些主要就是一些运营的活。微信公众号、微博、B站、西瓜视频之类的。最好有运营的小伙伴支持一下。还有就是微信群，帮忙解答一些非技术类问题，碰到技术类问题的话，就帮忙 @ 一下开发人员。

## WebContainer 技术调研

我这里放一个介绍WebContainer的链接，感兴趣的小伙伴可以先点进去看看

https://juejin.cn/post/7201464975722332216

简单来说就是，WebContainer 就是一个可以运行在浏览器页面中的微型操作系统。如果 Remix IDE 能结合这项技术，那整个使用体验能再上升一个 level 。

目前国内智能合约 IDE 领域做得最好的就是纯白矩阵的 ChainIDE 。我用过 ChainIDE ，使用体验完全不如 Remix 。但是 ChainIDE 有一个 Remix 没有的优点，就是可以提供 linux 环境，这样在 ChainIDE 上就可以用 truffle、hardhat、ganache 了。不过 ChainIDE 的实现方案非常笨重，是在服务器上起一个 linux 虚拟机，然后通过 websocket 跟前端通信。这种中心化的方案成本很高的，用户量稍微大一点，服务器估计就扛不住了。

如果 Remix 能结合 WebContainer 的话，我估计能把 ChainIDE 秒成渣渣。


