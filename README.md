# BVRS

BUGX.IO Vulnerability Review Standard

Author  : BUGX.IO 审核团队

Version : 1.0

Update  : 20181122

目前，BUGX.IO 审核奖励计算逐步实现自动，使用程序式计算，从而减少人为主观因素的影响。以下为我们的奖励参考维度，目前状态为`开源`，力求公正，与白帽子共同进步。

后续我们会开源审核标准的其它文档。

[BUGX.IO漏洞审核奖励表](https://github.com/bugxio/BVRS/blob/master/奖励表.png)

[厂商信息(排名、级别等)](https://github.com/bugxio/BVRS/blob/master/exchange/2018_12_16.csv)

## 漏洞奖励参考维度

### 1. 厂商类别

厂商类别分为`A`、`B`、`C`、`D`、`E`五个级别，其中

- `A`、`B`、`C`厂商需要：

    1. [收录交易所](https://github.com/bugxio/BVRS/blob/master/exchange/2018_12_16.csv)列表中
    2. `24h交易量`满足最低值,`$10,000`

- `D`类厂商
    1. 在非小号上搜不到
    2. 不在收录范围内
    3. 交易量低于`$10,000`

### 备注
1. D类厂商将选择性接收
2. 每天`18`点前的漏洞日清，`18`点后的漏洞纳入第二天审核，交易所厂商信息以第二天的为准。（即，`1`号`18`时前的漏洞以`1`号的厂商信息为标准，`1`号`18`时至`2`号`18`时漏洞，以`2`号的厂商信息为标准。


#### 1.2 厂商种类

厂商包括：交易所、公链、代币、数字钱包、矿池、智能合约等直接相关的厂商
其余不在该范围内的厂商算作，区块链非直接相关厂商

注：

1. 公链漏洞：指底层区块链技术的漏洞，如共识算法、P2P网络等。
2. 代币漏洞：指的是ICO或token存在一定市值的合约的漏洞。
3. 数字钱包漏洞：钱包客户端指代的是，安卓钱包、IOS钱包、Web钱包、硬件钱包等。
4. 其他相关厂商包括，资讯类网站（媒体类网站，论坛网站）、矿机售卖网站、厂商核心产品的宣传网站等

### 2. 厂商排位

厂商排位指，该厂商在其所在类中的排名位置。举例，假设某类厂商有`100`所，其中一个厂商在该类厂商中排`23`名，那么厂商排位为`1 - 23/100`

### 3. 漏洞分数

漏洞分数用来衡量一个漏洞的危害程度：`漏洞分数 = f(呈现危害, 利用难度, 漏洞威胁)`

#### 3.1 呈现危害

即白帽子的POC所体现出来的危害级别，有`严重`、`高危`, `中危`, `低危`四个级别

#### 3.2 利用难度

`利用难度 = g(攻击途径, 攻击复杂度)`

1. 攻击途径，包括`远程攻击`、`需绕过的远程攻击`、`本地攻击`
2. 攻击复杂度，包括`容易`，`中等`，`困难`，该维度主要用于衡量攻击的成本，需要的专业技术水平等

#### 3.3 漏洞威胁

漏洞威胁指，该漏洞的可能利用手段。该维度主要用来衡量一个漏洞可能存在的危害、影响。
例如，`xss`存在`用户身份劫持`、`钓鱼`、`控制用户浏览器行为`、`蠕虫`等。因此，漏洞的利用手段越多，该维度分值越高。
如果，白帽子的`POC`中存在我们暂未收录的可能攻击手段，则该白帽子该漏洞的`漏洞威胁`为满分

### 最终奖励

`最终奖励 = h(厂商排位, 最高奖励, 漏洞分数)`
其中`最终奖励 ≥ (λ * 最高奖励)`，`λ`的值与厂商的级别有关，越高级别的厂商`λ`越大


