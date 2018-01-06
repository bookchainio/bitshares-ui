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
| 界值            | 51%      |

所有四位参与者都有33%的权重，可是界值被设为51%。所以，只要四人中的两位同样就可以让交易生效。

或者，为了形成一个3-4方案，我们可以把权重减小到17%或增加界值到99%。

## (Flat) 灵活的多重签名

有了界值和权重，我们现在对我们的资金有了更大的灵活性, 或者更确切地说, 我们有更多的 * 控制 *。 比如，我们可以为不同的人设置不同的权重。 让我们假设Alice希望她的资金更安全，以防止被多重签名方案盗取她的资金，所以她不希望让她的朋友有过多的控制。 因此，我们可以创建一个类似于下面内容的授权：

| 账号            | 权重       |
| ------------- | -------- |
| Alice         | 49%      |
| Bob           | 25%      |
| Charlie       | 25%      |
| Dennis        | 10%      |
| \---\---\---- | \---\--- |
| 界值：           | 51%      |

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