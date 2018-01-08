# 商业

这个页面将给您一个有关通过DEX以及交易呈现的术语的快速解说。

## 配对

在比特股中，几乎任何资产都可以与所有的其他的资产进行交易。 一旦我们有了选择两个资产，我们通常指的是一个*市场配对*。 例如，我们可以在美元：欧元配对中，用美元兑换欧元。

为了保持一致性，我们将使用一般术语* 基本*和* 报价* 如此配对将呈现为

    *报价* : *基本*
    

例如以*基础* 为美元 *报价* 为欧元，表示欧元：美元配对。

## 预定订单

订单由*询价*和*出价*两部分组成。 由于交易配对没有有一个指定的方向，而且它可被翻转，下表应给出 询价/出价的概述以及相应的买方/卖方操作：

| 方             | 卖         | 买         |
| ------------- | --------- | --------- |
| 问价            | *报价*      | *基础*      |
| 出价            | *基础*      | *报价*      |
| \---\---\---- | \---\---- | \---\---- |

很显然，美元兑欧元的出价方，会是欧元兑美元的询问方。 Of course prices are internally represented as fractions, and thus results in both pairs being identical.

## Trading

To place a trading order, it is required to fill the form on either the *ask* or the *bid* side (respectively, *buy* or *sell* side). You will need to define a *price* and an *amount* to sell/buy. The cost for this order will be calculated automatically. Note that there will be an additional fee required to actually place the order.

Once the order is filled (i.e. someone sold/bought your offer), your account will be credited by the corresponding asset.

Unfilled orders can be canceled at any time.