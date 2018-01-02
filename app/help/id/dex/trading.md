# Perdagangan

Halaman ini akan memberikan pengenalan yang sangat cepat tentang cara untuk menafsirkan istilah yang digunakan oleh DEX dan bagaimana perdagangan pasangan yang disajikan.

## Pairs

Di BitShares, hampir semua aset bisa diperdagangkan dengan semua aset lainnya. Once we have picked two assets, we usually refer to a *market pair*. For instance, we can trade USD against EUR in the USD:EUR pair.

Untuk kepentingan konsistensi, kami akan menggunakan istilah umum *dasar* dan *kutipan* sedemikian rupa sehingga pasang direpresentasikan sebagai

    *quote* : *base*
    

and for instance with *base* being USD and *quote* being EUR, denote the EUR:USD pair.

## Order Books

The order book consists of an *ask* and a *bid* side. Karena pasangan perdagangan tidak memiliki orientasi yang diinginkan, dan dapat dibalik, tabel berikut harus diberikan ikhtisar permintaan / penawaran dan operasi pembelian/penjualan yang sesuai untuk masing-masing pihak:

| Sisi          | Jual      | Buy       |
| ------------- | --------- | --------- |
| Ask           | *quote*   | *base*    |
| Bid           | *base*    | *quote*   |
| \---\---\---- | \---\---- | \---\---- |

Obviously, what is on the bid side of the USD:EUR pair will be on the ask side on the EUR:USD pair. Tentu saja harga secara internal diwakili sebagai pecahan, dan dengan demikian menghasilkan kedua pasang itu identik.

## Trading

To place a trading order, it is required to fill the form on either the *ask* or the *bid* side (respectively, *buy* or *sell* side). You will need to define a *price* and an *amount* to sell/buy. The cost for this order will be calculated automatically. Note that there will be an additional fee required to actually place the order.

Once the order is filled (i.e. someone sold/bought your offer), your account will be credited by the corresponding asset.

Perintah yang tidak terisi dapat dibatalkan setiap saat.