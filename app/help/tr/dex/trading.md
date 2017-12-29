# Ticari

Bu sayfada, DEX tarafından kullanılan terimlerin nasıl yorumlanacağı ve ticaret çiftlerinin nasıl sunulduğu hakkında çok hızlı bir giriş sunulacaktır.

## Çiftler

BitShares da hemen hemen her varlık, diğer tüm varlıklarla işlem görebilir. Once we have picked two assets, we usually refer to a *market pair*. For instance, we can trade USD against EUR in the USD:EUR pair.

Tutarlılık uğruna, çiftlerin aşağıdaki gibi temsil edileceği şekilde * taban </ 0> ve * alıntı </ 0> genelleştirilmiş terimlerini kullanacağız</p> 

    * alıntı *: * tabanı *
    

and for instance with *base* being USD and *quote* being EUR, denote the EUR:USD pair.

## Kitap Siparişi

The order book consists of an *ask* and a *bid* side. Alım satım çiftlerinin tercih edilen yönelimleri olmadığı ve tersine çevrilebileceği için, aşağıdaki tabloda, her iki tarafın sorma / teklif ve buna karşılık gelen satın alma / satma işlemleri hakkında genel bir bilgi verilmektedir:

| Yan           | Sat       | satın al  |
| ------------- | --------- | --------- |
| Ask           | *alıntı*  | *baz*     |
| teklif        | *baz*     | *alıntı*  |
| \---\---\---- | \---\---- | \---\---- |

Açıkçası, USD: EUR çiftinin teklif tarafındaki durum EUR: USD çifti için sorulacak taraf olacaktır. Elbette fiyatlar dahili ve kesir olarak gösterilir, bu nedenle her iki çift için de özdeş olur.

## Ticari

To place a trading order, it is required to fill the form on either the *ask* or the *bid* side (respectively, *buy* or *sell* side). You will need to define a *price* and an *amount* to sell/buy. Bu siparişin maliyeti otomatik olarak hesaplanacaktır. Aslında sipariş vermek için ek bir ücret gerekeceğini unutmayın.

Sipariş doldurulduğunda (diğer birisi teklifinizi sattı / satın aldı), hesabınız ilgili varlık tarafından gösterilir.

Doldurulmamış siparişler istediğiniz zaman iptal edilebilir.