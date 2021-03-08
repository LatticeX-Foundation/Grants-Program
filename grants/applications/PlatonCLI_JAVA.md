# Grant技术类项目申请

**项目名称：platoncli-java** 

## 1. 项目简介  
### ***项目介绍***   
> 为了方便节点和普通用户，开发一套基于java的cli工具。

### ***项目特点***  
> - 代码简单，工具易用；
> - 功能完善，互相独立；
> - 易于维护，便于扩展；
> - 兼容性强，兼容多网；

### ***对Alaya或者PlatON生态的益处***  
> 可以提供更好地批量交易的功能，能够更高效的发送交易，方便节点和普通用户使用。

### ***详细说明***

> API设计：本软件分为8个模块：交易模块、质押模块、委托模块、治理模块、钱包管理模块、锁仓模块、链基本信息模块和帮助。

#### **交易模块**

> |命令名称| 功能描述|
> |----|----|
> |tx_getTransactionReceipt|根据交易hash查询交易信息|
> |tx_getTransaction|根据交易hash查询交易|
> |tx_sendOffline|发送已签名交易数据|
> |tx_transfer|发送交易|


#### **质押模块**

> 命令名称| 功能描述
> ---|---
> staking_create|创建验证人
> staking_update|修改质押信息
> staking_increase|增持质押
> staking_unStaking|退出验证人
> staking_getValidatorList|查询当前共识周期的验证人列表
> staking_getVerifierList|查询当前结算周期的验证人列表
> staking_getCandidateList|查询所有实时候选人列表
> staking_getCandidateInfo|根据nodeId查询节点质押信息
> staking_getStakingReward|查询当前结算周期的质押奖励

#### **委托模块**

> 命令名称| 功能描述
> ---|---
> delegate_new|委托
> delegate_getDelegateReward|查询账户在各节点未提取委托奖励
> delegate_getRelatedListByDelAddr|查询当前账户地址所委托的节点的NodeId和质押Id
> delegate_unDelegate|减持/撤销委托
> delegate_withdrawDelegateReward|提取委托奖励

#### **治理模块**

> 命令名称| 功能描述
> ---|---
> government_checkDoubleSign|查询节点是否已被举报过多签
> government_declareVersion|版本声明
> government_getAccuVerifiersCount|查询提案的累计可投票人数
> government_getActiveVersion|查询节点的链生效版本
> government_getGovernParamValue|查询最新的治理参数值
> government_getProposal|根据提案id查询提案信息
> government_getTallyResult|查询提案结果
> government_listGovernParam|查询治理参数列表
> government_listProposal|查询提案列表
> government_reportDoubleSign|举报双签
> government_submitProposal|提交参数/升级/取消提案
> government_vote|提案投票

#### **钱包管理模块**
> 命令名称| 功能描述
> ---|---
> account_new|创建钱包
> account_check|查看本地钱包
> account_delete|删除钱包
> account_backups|钱包备份
> account_recovery|恢复私钥
> account_modify|修改钱包密码
> account_sign|离线签名
> account_getBalance|查询钱包余额

#### **锁仓模块**
> 命令名称| 功能描述
> ---|---
> hedge_createRestrictingPlan|创建锁仓计划
> hedge_GetRestrictingInfo|获取锁仓计划

#### **链基本信息模块**

> 命令名称| 功能描述
> ---|---
> query_blockNumber|查询当前最高块高查询当前最高块高
> query_getAvgPackTime|查询打包区块的平均时间
> query_getBlockByHash|根据区块hash查询区块信息
> query_getBlockByNumber|根据区块块高查询区块信息
> query_getPackageReward|查询当前结算周期的区块奖励

#### **帮助**
> 在命令之后添加`--help`或者`-help`，可以查询得到命令的帮助信息。


### ***技术介绍***
> platoncli-java使用的依赖库主要包括两大部分，分别为外部依赖库和内部依赖库，其中外部依赖库主要包括命令行处理库*jcommander*和日志处理库*slf4j*，内部依赖库为基于*alaya*网络的*java sdk*；
> - **jcommander**
    - 注解驱动：它的核心功能命令行参数定义是基于注解的，这也是我选择用它的主要原因。我们可以轻松做到命令行参数与属性的映射，属性除了是String类型，还可以是Integer、boolean，甚至是File、集合类型。
    - 功能丰富：它同时支持文章开头的两种命令行风格，并且提供了输出帮助文档的能力(usage())，还提供了国际化的支持。
    - 高度扩展：基于java的jcommander可以轻易实现扩展性功能。
> - **slf4j**
    - 可自定义日志级别，日志格式等；
    - 简单易用；
> - **java sdk**
    - 基于alaya网络的alaya-core。主要用于钱包的创建，rpc命令的调用，交易的签名等，通过代码重构，实现同时兼容platon和alaya等不同hrp的网络；

### ***部署说明***

> 以windows环境为例，在powershell中执行如下命令。在`platoncli-java/target`文件夹下将会生成可执行文件`platoncli-java-jar-with-dependencies.jar`
> ```shell
> cd platoncli-java
> mvn package
> ```

### ***项目优势***  
> 解决当前其他cli工具的痛点：支持不同hrp的网络；支持批量快速交易功能；能够自定义gas手续费；安装方便，只需要配置好java和maven环境即可。

### ***项目GitHub仓库***  
> https://github.com/aviland/platoncli-java

## 2. 团队介绍
### ***团队名称***  
> ```
> AVILAND
> ```
### ***团队成员***

> |  团队成员名字  | GitHub代码库 
> |  ----  | ---- 
> | haypo  | https://github.com/aviland和https://gitee.com/HAYPO

### ***联系方式***
* **联系人全名:任晖** 

### ***团队背景及经验***
> 曾参与若干物联网和社区项目开发，具有多年java开发经验。对于区块链领域非常关注。

## 3. 项目规划

### ***概述***

> 项目分为两期共4个月。其中第一期为2021.1-2021.2，第二期2021.3-2021.4。
在每个阶段完成时，将提供`功能测试报告`、`操作手册`、`软件安装使用说明`、`设计文档`等文件。
> * **预计总工时: 4个月** 
> * **全职人员数量: 1**  

### ***里程碑1***
> * **预计工时:** 2个月  
> * **全职人员数量:**  1人   

交付计划  
> 1. 交付时间：2021.2.28
> 2. 交付物：
>    1. 交易模块：1.1-1.10  
>    2. 质押模块：1.11-1.24  
>    3. 委托模块：1.25-2.7  
>    4. 治理模块：2.8-2.21
> 3. 测试时间：2.22-2.27

交付物清单

> | 交付物编号编号 | 交付物 | 说明 |
> | ------------- | ------------- | ------------- |
> | 0a. | 开源协议 | Apache 2.0 |
> | 0b. | 文档 | 我们将提供操作手册、软件安装使用说明、设计文档等方便用户快速上手 |
> | 0c. | 功能测试报告 | 为确保功能完整和系统的健壮，我们提供功能测试报告| 
> | 1. | 交易模块 | 参见`交易模块` |  
> | 2. | 质押模块 | 参见`质押模块` |  
> | 3. | 委托模块 | 参见`委托模块` |  
> | 4. | 治理模块 |参见`治理模块`  |  

### 里程碑2
* **预计工时:** 2个月
* **全职人员数量:**  1人  

交付计划 
> 1. 交付时间：2021.4.30
> 2. 交付模块：
>     1. 钱包管理模块：3.1-3.10
>     2. 链基本信息模块：3.11-3.24
>     3. 锁仓模块；3.25-4.7
>     4. 帮助：4.8-4.21
> 3. 测试时间：4.22-4.29

交付物清单

> | 交付物编号编号 | 交付物 | 说明 |
> | ------------- | ------------- | ------------- |
> | 0a. | 开源协议 | Apache 2.0 |
> | 0b. | 文档 | 我们将提供操作手册、软件安装使用说明、设计文档等方便用户快速上手 |
> | 0c. | 功能测试报告 | 为确保功能完整和系统的健壮，我们提供功能测试报告| 
> | 1. | 钱包管理模块 | 参见`钱包管理模块` |  
> | 2. | 链基本信息模块 | 参见`链基本信息模块` |  
> | 3. | 锁仓模块 | 参见`锁仓模块` |  
> | 4. | 帮助 |参见`帮助`  |  

## 未来计划
> 考虑图形化platon周边软件开发，如基于java fx的桌面版platon。
> 考虑其他语言和框架开发platon周边软件，如基于c#的sdk，基于wpf的桌面钱包软件等。

## 其他信息  
> * 目前已完成里程碑1的任务，开始里程碑2的开发。
> * platoncli-java的设计文档参考了基于python的platoncli。
> * 关于未来计划，正在研究中。
