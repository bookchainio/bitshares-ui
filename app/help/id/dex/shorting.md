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

Setelah meminjam bitAssets, mereka bisa dijual bebas di salah satu yang sesuai pasar dengan harga berapa pun pembeli bersedia membayar. Dengan langkah ini, short-selling sekarang lengkap dan Anda pendek yang bitAsset tertentu.

## Memperbarui jaminan Ratio

Setiap saat, pemegang pinjaman / posisi pendek dapat memodifikasi agunan rasio agar fleksibel menyesuaikan diri dengan perilaku pasar. Jika rasio agunannya adalah meningkat, sejumlah tambahan BTS terkunci sebagai jaminan, sekaligus mengurangi rasio agunan akan memerlukan jumlah BitAsset yang sesuai dibayar kembali ke jaringan.

## Penutup

Untuk menutup posisi meminjam / short, seseorang harus memegang jumlah pinjaman itu bitAsset khusus untuk menyerahkannya ke jaringan BitShares. Setelah itu, BitAssets dikurangi dari suplai yang sesuai dan agunannya dilepaskan dan diserahkan kembali kepada pemiliknya.