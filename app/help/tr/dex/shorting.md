# Kısa Satış BitAssests

In order to increase your exposure to BTS and offer liquidity to BitAssets, such as USD, EUR, GOLD, etc., you can go *borrow* this bitAsset from the network and *sell it short*. Burada prosedür kısaca açıklanmıştır.

## Borçlanma

BitShares ağı, herhangi bir BitAsset'i, yeterli teminat verilmiş katılımcılara borç verebilmektedir.

- *settlement price*: Harici borsalarda işlem gören 1 BTS fiyatı.
- *maintenance collateral ratio*(MCR): Tanıkların minimum asgari teminat oranı olarak tanımladıkları oran
- *maximum short squeeze ratio* (MSQR): A ratio defined by the witnesses as to how far shorts are protected against short squeezes
- *short squeeze protection* (SQP): Bir marj pozisyonunu karşılamak için ödenecek en fazla tutarı tanımlar 
- *call price* (CP): Kısa / borçlanma pozisyonlarının marjı olarak adlandırılan fiyat

### Teminat Çağrısı

BitShares ağı, ödünç alınan bitAsset'leri geri yüklemek için yeterli teminat sahibi olmayan pozisyonları artırabilir. En yüksek teklifin *call price* daha az olması ve daha büyük bir teklif fiyatı olması durumunda, bir teminat çağrısı gerçekleşir *SQP*. Teminatı satın almak için verilen en yüksek teklif çağrı fiyatından (x / BTS) daha düşük olduğunda, teminat pozisyonu teminatını satmaya zorlanacaktır.

    SQP = settlement price / MSQR
    call price = DEBT / COLLATERAL * MCR
    

The margin call will take the collateral, buy shares of borrowed bitAsset at market rates up to the SQP and close the position. The remaining BTS of the collateral are returned to the customer.

### Settlement

Holders of any bitAsset can request a settlement at a *fair price* at any time. The settlement closes the borrow/short positions with lowest collateral ratio and sells the collateral for the settlement.

## Selling

After borrowing bitAssets, they can be sold free at any of the corresponding markets at any price a buyer is willing to pay. With this step, the short-selling is now complete and you are short that particular bitAsset.

## Updating Collateral Ratio

At any time, the holder of a borrow/short position can modify the collateral ratio in order to flexibly adjust to market behavior. If the collateral ratio is increase, an additional amount of BTS is locked as collateral, while reducing the collateral ratio will require an amount of the corresponding BitAsset to be payed back to the network.

## Covering

To close a borrow/short position, one must hold the borrowed amount of that particular bitAsset to hand it over to the BitShares network. After that, the BitAssets are reduced from the corresponding supply and the collateral is released and given back to its owner.