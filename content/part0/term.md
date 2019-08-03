---
title: "以太坊术语"
weight: 90002
---

在开始解读以太坊前，先了解以太坊中常见术语和名词。以便更好的学习后续内容。

## 专有名词

+ 外部账户：EOAs（External Owned Accounts），关联个人掌握的私钥。可以用于发送交易（转移以太币或发送消息），形同一张带数字ID的储蓄卡。

+ 合约账户：Contracts Accounts，可以在以太坊上存储合约代码与合约数据的账户，外部不能直接操作此账户。只能由外部账户直接或间接调用。

+ 账户状态： account state，表示一个账户在以太坊中的状态。账户状态在账户数据变化时变化。账户状态包含四项信息：nonce、余额、账户存储内容根哈希值、账户代码哈希值。状态数据不直接存储在区块上。

+ 账户 Nonce: 账户随机数，是账户的交易计数。以防止重放攻击。

+ 智能合约：Smart Contract，是以太坊成为区块链2.0的立足点。以太坊支持通过图灵完备的高级编程语言编写智能合约代码。部署在链上后，可以接受来自外部的交易请求和事件，以触发执行特定的合约代码逻辑，进一步生成新的交易和事件。甚至调用其他的智能合约。

+ 世界状态：state，管理账户地址到账户状态的映射关系。所有账户的状态构成整个区块链状态。

+ 交易：Transaction，是外部与以太坊交互的唯一途径，必须由外部账户签名，矿工执行交易，最终打包到区块中。

+ 交易收据：Receipt，是方便对交易进行零知识证明、索引和搜索，将交易执行过程中的一些特定信息编码为交易收据。


+ 区块：block，是由一组交易和一些辅助信息（简称区块头）、其他区块头哈希构成的数据块。其他区块头哈希表示父区块或者叔背区块。

+ 叔块：Uncle Block，不能成为主链一部分的孤儿区块，如果有幸被后来的区块收留进区块链就变成了叔块。收留了孤块的区块有额外的奖励。孤块一旦成为叔块，该区块统一可获得奖励。通过叔块奖励机制，来降低以太坊软分叉和平衡网速慢的矿工利益。

+ 随机数：nonce，记录在区块头中，努力工作的证明。

+ Gas：燃料是交易打包到区块时，在EVM运行所消耗的资源量的一种形象化概念，比喻需要燃料才能运行EVM。在以太坊中，将CPU资源、存储资源按内置的规则，统一使用 Gas 作为资源单位表达。每执行一次虚拟机指令，均消耗一定的Gas。

+ GasPrice: 燃料价格，任何交易都需要包含一个愿意支付的燃料单价，最终根据交易消耗的燃料量，计算手续费(usedGas*gasPrice)支付给矿工。

+ 价格预测：GPO(Gas Price Oracle)，Gas 价格预测，根据历史交易的GasPrice预测未来GasPrice走势。

## 技术术语

+ ZKP: Zero Knowledge Proof，零知识证明。

+ EVM：Ethereum Virtual Machine，以太坊虚拟机是执行交易的一个轻量级沙盒虚拟机。


+ Message：消息，是一个不能序列化的，并且只存在于以太坊运行环境中的虚拟对象，一条消息主要包括：消息的发送方、接收方、gasLimit等等；

+ 序列化：将数据使用RLP编码为一组字节数据，便于数据交换与存储。

+ RLP: 递归长度前缀编码，一种能够压缩数据的数据编码协议，在以太坊中常用于序列化数据。

+ MPT：默克尔压缩前缀树， Merkle Patricia Tree，是一种经过改良的、融合了默克尔树和前缀树两种树结构优点的数据结构，是以太坊中用来组织管理账户数据、生成交易集合哈希的重要数据结构。

+ Patricia Trie: 一种压缩前缀树，是一种更节省空间的树，对于 trie 的每个节点，如果该节点是其父节点唯一的儿子的话，就和父节点结合；

+ Merkle Tree: 默克尔树，也称为 Hash Tree，默克尔树叶子节点的value是数据项的内容，或者是数据项的哈希值；非叶子节点的value根据其孩子节点的信息，然后按照Hash算法计算而得出的。

+ Whisper：密语，是一种依托于P2P的通信协议，通过 Whisper 协议，节点可以将信息发送给某个特定节点，实现双节点私聊和按主题在多个节点上通信。主要用于大规模的点对点数据发现、信号协商、最小传输通信、完全隐私保护的 DApp 而设计的。

+ LES： Light Ethereum Subprotocol，以太坊客户端的轻量级的子协议，只需要下载区块头，其他详细信息可以按需获取；LES Wiki
 
+ Swarm： 蜂巢，是一个分布式存储平台和内容分发服务，是以太坊 web 3 技术栈的本地基础层服务;  

+ LLL，Sperpent、Mutan和Solidity：用于编写智能合约代码的的编程语言，能被编译成EVM代码。

+ ERC20: 可以理解成 Ethereum 的一个 Token 协议规范，所有基于 Ethereum 开发的 Token 合约都遵守这个规范。遵守 ERC20 协议规范的 Token 可以被各种 Ethereum 钱包支持。

+ ERC721: 是在ERC20标准上建立的Token协议规范，是针对不可互换Token(non-fungible tokens 简称NFTs)做的智能合约标准。