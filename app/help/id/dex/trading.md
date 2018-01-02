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

Jelas, apa yang ada di sisi penawaran pasangan USD: EUR akan berada di sisi permintaan pada pasangan EUR: USD. Tentu saja harga secara internal diwakili sebagai pecahan, dan dengan demikian menghasilkan kedua pasang itu identik.

## Trading

To place a trading order, it is required to fill the form on either the *ask* or the *bid* side (respectively, *buy* or *sell* side). You will need to define a *price* and an *amount* to sell/buy. Biaya untuk pesanan ini adalah dihitung secara otomatis. Perhatikan bahwa akan ada biaya tambahan yang diperlukan untuk benar-benar memesan.

Setelah pesanan terisi (yaitu seseorang menjual/membeli penawaran Anda), akun Anda akan dikreditkan oleh aset yang bersangkutan.

Perintah yang tidak terisi dapat dibatalkan setiap saat.