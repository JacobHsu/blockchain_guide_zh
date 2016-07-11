## 简介

根据以太坊官方的宣称，以太坊目标是打造成一个运行智能合约的去中心化平台（Platform for Smart Contract），平台上的应用按程序设定运行，不存在停机、审查、欺诈、第三方人为干预的可能。以太坊平台由 Golang、C++、Python 等多种编程语言实现。

当然，为了打造这个平台，以太坊提供了一条公开的区块链，并制定了面向智能合约的一套编程语言。智能合约开发者可以在其上使用官方提供的工具来开发支持以太坊区块链协议的应用（即所谓的 DAPP）。

### 历史与规划

2014 年，以太坊项目开始众筹计划。

2015 年 7 月，众筹完成，筹到价值 1800 万美金的比特币，第一阶段 Frontier 发布，以太坊区块链网络正式上线。

2016 年 3 月，第二阶段 Homestead 开始运行（区块数 1150000），主要改善了安全性。

2016 年 3Q，发布 Metropolis；

2017 年 1Q，发布 Serenity，发布区块链的 PoS 股权证明(Casper)版本。


### 特点

以太坊区块链的特点主要包括：

* 单独为智能合约指定编程语言 Solidity；
* 使用了内存需求较高的哈希函数：避免出现算力矿机；
* uncle 块激励机制：降低矿池的优势，减少区块产生间隔为 15 秒；
* 难度调整算法：一定的自动反馈机制；
* gas 限制调整算法：限制代码执行指令数，避免循环攻击；
* 记录当前状态的哈希树的根哈希值到区块：某些情形下实现轻量级客户端；
* 为执行智能合约而设计的简化的虚拟机 EVM。