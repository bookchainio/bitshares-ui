# BitAssets Menjual Pendek

Untuk meningkatkan eksposur Anda terhadap BTS dan menawarkan likuiditas kepada BitAssets, semacam itu seperti USD, EUR, GOLD, dll, Anda bisa pergi *meminjam* bitAsset ini dari jaringan dan *jual pendek*. Disini kita akan menjelaskan secara singkat prosedurnya.

## Peminjaman

Jaringan BitShares mampu mengeluarkan sejumlah BitAsset dan pinjaman apapun Bagi peserta diberi cukup jaminan.

- *harga penyelesaian*: Harga untuk 1 BTS seperti yang diperdagangkan di bursa eksternal.
- *rasio jaminan perawatan* (MCR): Rasio yang ditentukan oleh saksi sebagai rasio jaminan minimum yang dipersyaratkan
- *rasio pemerasan pendek maksimum* (MSQR): Rasio yang ditentukan oleh para saksi mengenai sejauh mana celana pendek terlindungi dari tekanan pendek
- *proteksi jepret pendek* (SQP): Mendefinisikan yang paling bahwa posisi margin akan dipaksa untuk membayar untuk menutupi 
- *harga panggilan* (CP): Harga di mana posisi short / borrow disebut margin

### Margin Call

Jaringan BitShares mampu memberi margin pada posisi yang tidak memiliki cukup jaminan untuk mendukung bitAssets pinjaman mereka. A margin call will occur any time the highest bid is less than the *call price* and greater than *SQP*. The margin position will be forced to sell its collateral anytime the highest offer to buy the collateral is less than the call price (x/BTS).

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