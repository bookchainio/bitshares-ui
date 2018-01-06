# 权限

在 BitShares中，每个账号都被分成

* **活动权限**: 控制其资金并
* **所有者权限**: 控制账户。

两者皆可由`权限`定义，它在您的账号的*授权*(如下所示) 里，为了让一个交易有效*界值*必须被超过。

## 授权

在 BitShares 里，一个*授权* 包括一个或多个实体授权一个操作，如转账或交易。

一个授权由一对或多对具有 * 权重 * 的帐户名组成。

为实现一个有效的交易, 签署各方的权重的总和必须超过权限中定义的界值。

# 示例

让我们讨论一些例子，来阐明使用的术语和用户实例。 我们假定有一个新建的帐户, 它的活动权限设置如下。 请注意相同的模式同样适用于所有者权限!

## (Flat) 多重签名

一个简单的多重签名方案，包括`M` 实体且 `N` 为了交易生效，实体必须签名。 现在，在 BitShares，我们有 *权重* 和一个 *界值* 代替 `M` 和 `N`。 可以看到，我们仍然可达到相同的结果，甚至更灵活。

让我们假定 Alice, Bob, Charlie 和 Dennis 有共同的基金。 只要其中两者同意，我们希望可以形成一个有效的交易。 所以一个 **2-到-4** (N-of-M) 的方案可以看到如下：

| 账号            | 权重       |
| ------------- | -------- |
| Alice         | 33%      |
| Bob           | 33%      |
| Charlie       | 33%      |
| Dennis        | 33%      |
| \---\---\---- | \---\--- |
| Threshold:    | 51%      |

All four participants have a weight of 33% but the threshold is set to 51%. Hence only two out of the four need to agree to validate the transaction.

Alternatively, to construct a 3-of-4 scheme, we can either decrease the weights to 17 or increase the threshold to 99%.

## (Flat) Flexible Multi-Signature

With the threshold and weights, we now have more flexibility over our funds, or more precisely, we have more *control*. For instance, we can have separate weights for different people. Let's assume Alice wants to secure here funds against theft by a multi-signature scheme but she does not want to hand over too much control to her friends. Hence, we create an authority similar to:

| Account       | Weight   |
| ------------- | -------- |
| Alice         | 49%      |
| Bob           | 25%      |
| Charlie       | 25%      |
| Dennis        | 10%      |
| \---\---\---- | \---\--- |
| Threshold:    | 51%      |

Now the funds can either be accessed by Alice and a single friend or by all three friends together.

## Multi-Hierarchical Flexible Multi-Signature

Let's take a look at a simple multi-hierarchical corporate account setup. We are looking at a company that has a Chief of Financial Officer (CFO) and a some departments working for him, such as the Treasurer, Controller, Tax Manager, Accounting, etc. The company also has a CEO that wants to have spending privileges. Hence we construct an authority for the funds according to:

| Account       | Weight   |
| ------------- | -------- |
| CEO.COMPANY   | 51%      |
| CFO.COMPANY   | 51%      |
| \---\---\---- | \---\--- |
| Threshold:    | 51%      |

whereas CEO.COMPANY and CFO.COMPANY have their own authorities. For instance, the CFO.COMPANY account could look like:

| CFO.COMPANY               | Weight   |
| ------------------------- | -------- |
| Chief.COMPANY             | 51%      |
| Treasurer.COMPANY         | 33%      |
| Controller.COMPANY        | 33%      |
| Tax Manager.COMPANY       | 10%      |
| Accounting.COMPANY        | 10%      |
| \---\---\---\---\---\---- | \---\--- |
| Threshold:                | 51%      |

This scheme allows:

* the CEO to spend funds
* the Chief of Finance Officer to spend funds
* Treasurer together with Controller to spend funds
* Controller or Treasurer together with the Tax Manager and Accounting to spend funds.

Hence, a try of arbitrary depth can be spanned in order to construct a flexible authority to reflect mostly any business use-case.