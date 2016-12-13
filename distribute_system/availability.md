## 可靠性指标

很多领域一般都喜欢谈服务可靠性，用几个 9 来说事。这几个 9 其实是粗略代表了概率意义上系统能提供服务的可靠性指标，最初是电信领域提出的概念。

下表给出不同指标下，每年允许服务出现不可用时间的参考值。

指标  | 概率可靠性  | 每年允许不可用时间 | 典型场景
----- | --------: | ------------- :| -------
一个九 | 90%       | 1.2 个月        | 不可用
二个九 | 99%       | 3.6 天          | 普通单点
三个九 | 99.9%     | 8.6 小时        | 普通企业
四个九 | 99.99%    | 51.6 分钟       | 高可用
五个九 | 99.999%   | 5 分钟          | 电信级
六个九 | 99.9999%    | 31 秒         | 极高要求
七个九 | 99.99999%    | 3 秒         | N/A
八个九 | 99.999999%    | 0.3 秒      | N/A
九个九 | 99.9999999%    | 30 毫秒     | N/A

一般来说，单点的服务器系统至少应能满足两个九；普通企业信息系统三个九就肯定足够了（大家可以统计下自己企业内因系统维护每年要停多少时间），系统能达到四个九已经是业界领先水平了（参考 AWS）。电信级的应用一般号称能达到五个九，这已经很厉害了，一年里面最多允许五分钟的服务停用。六个九和以上的系统，就更加少见了，要实现往往意味着极高的代价。

那么，该如何提升可靠性呢？有两个思路：一是让系统中的单点变得更可靠；二是消灭单点。

IT 从业人员大都有类似的经验，运行某软系统的机器，基本上是过几天就要重启下的；而运行 Linux 系统的服务器，则可能几年时间都不出问题。另外，普通的家用计算机，跟专用服务器相比，长时间运行更容易出现故障。这些都是单点可靠性不同的例子。可以通过替换单点的软硬件来改善可靠性。

然而，依靠单点实现的可靠性毕竟是有限的，要想进一步的提升，那就只好消灭单点，通过主从、多活等模式让多个节点集体完成原先单点的工作。这可以从概率意义上改善服务的可靠性，也是分布式系统的一个重要用途。