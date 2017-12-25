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

Jaringan BitShares mampu memberi margin pada posisi yang tidak memiliki cukup jaminan untuk mendukung bitAssets pinjaman mereka. Sebuah margin call akan terjadi kapan pun tawaran tertinggi kurang dari harga panggilan * * dan lebih besar dari * SQP *. Posisi margin akan dipaksa untuk menjual agunannya kapanpun yang tertinggi Penawaran untuk membeli agunan kurang dari harga panggilan (x / BTS).

    SQP = harga penyelesaian / MSQR
    call price = DEBT / COLLATERAL * MCR
    

Margin call akan mengambil agunan, membeli saham bitAsset yang dipinjam di harga pasar sampai ke SQP dan tutup posisinya. Sisa BTS dari agunan dikembalikan ke pelanggan.

### Penyelesaian

Pemegang bitAsset manapun dapat meminta penyelesaian pada harga *yang wajar* kapan saja. Penyelesaian menutup posisi pinjam / short dengan rasio agunan terendah dan menjual agunan untuk penyelesaian.

## Penjualan

After borrowing bitAssets, they can be sold free at any of the corresponding markets at any price a buyer is willing to pay. With this step, the short-selling is now complete and you are short that particular bitAsset.

## Updating Collateral Ratio

At any time, the holder of a borrow/short position can modify the collateral ratio in order to flexibly adjust to market behavior. If the collateral ratio is increase, an additional amount of BTS is locked as collateral, while reducing the collateral ratio will require an amount of the corresponding BitAsset to be payed back to the network.

## Covering

To close a borrow/short position, one must hold the borrowed amount of that particular bitAsset to hand it over to the BitShares network. After that, the BitAssets are reduced from the corresponding supply and the collateral is released and given back to its owner.