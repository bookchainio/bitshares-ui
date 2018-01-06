# Kısa Satış BitAssests

BTS'ye olan riskinizi artırmak ve USD, EUR, GOLD vb. Gibi BitAssets'e likidite sağlamak için ağdan bu bitAsset'i ödünç alabilir *borrow* ve satabilirsiniz *sell it short*. Burada prosedür kısaca açıklanmıştır.

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
    

Teminat çağrısı teminatı alacak, ödünç alınan bedAsset hisselerini SQP'ye kadar piyasa fiyatlarında satın alacak ve pozisyonunu kapatacaktır. Teminatın kalan BTS'si müşteriye iade edilir.

### Ödeme

BitAsset sahipleri istediği bir fiyattan, istediği zaman *fair price* bir uzlaşma talep edebilir. Yerleşim, en düşük teminat oranına sahip borç / kısa pozisyonları kapatır ve ödeme için teminatı satar.

## Satış

BitAssets'i ödünç alındıktan sonra, alıcıların ödemeyi düşündüğü herhangi bir fiyata karşılık gelen pazarlardan herhangi birinde ücretsiz olarak satılabilirler. With this step, the short-selling is now complete and you are short that particular bitAsset.

## Teminat Oranı Güncellemesi

Borç / kısa pozisyon sahibi, herhangi bir zamanda, piyasa davranışını esnek bir şekilde ayarlamak için teminat oranını değiştirebilir. Teminat oranı artarsa, ek BTS miktarı teminat olarak kilitlenirken, teminat oranının düşürülmesine karşılık gelen BitAsset'in şebekeye geri ödenmesini gerektirir.

## Kapsam

Bir borçlanma / açık pozisyonunu kapatmak için, BitShares ağına aktarmak için ödünç alınan belirli bitAsset tutarını tutmalısınız. Bundan sonra, BitAsset'lere karşılık gelen arzdan azaltılır, teminat serbest bırakılır ve sahibine geri verilir.