# Perdagangan

Halaman ini akan memberikan pengenalan yang sangat cepat tentang cara untuk menafsirkan istilah yang digunakan oleh DEX dan bagaimana perdagangan pasangan yang disajikan.

## Pairs

In BitShares, almost any asset can be traded with all other assets. Once we have picked two assets, we usually refer to a*market pair*. For instance, we can trade USD against EUR in the USD: EUR pair.

Untuk kepentingan konsistensi, kami akan menggunakan istilah umum *dasar* dan *kutipan* sedemikian rupa sehingga pasang direpresentasikan sebagai

    *quote*: *base*
    

and for instance with * base * being USD and * quote * being EUR, denote the EUR: USD pair.

## Order Books

The order book consists of an * ask * and a * bid * side. Since trading pairs do not have a preferred orientation, and can be flipped, the following table shall give an overview of ask / bid and the corresponding buy / sell operations for each side:

| Sisi          | Jual      | Beli      |
| ------------- | --------- | --------- |
| Ask           | *quote*   | *base*    |
| Tawaran       | *base*    | *quote*   |
| \---\---\---- | \---\---- | \---\---- |

Jelas, apa yang ada di sisi penawaran dari pasangan USD: EUR akan berada di sisi permintaan pada pasangan EUR: USD. Tentu saja harga secara internal diwakili sebagai pecahan, dan dengan demikian menghasilkan kedua pasang itu identik.

## Perdagangan

Untuk menempatkan order perdagangan, Anda harus mengisi formulir di * ask * atau sisi * bid * (masing-masing, * beli </ 0> atau * jual * samping). Anda perlu mendefinisikannya harga * * dan * jumlah * untuk menjual/membeli. Biaya untuk pesanan ini adalah dihitung secara otomatis. Perhatikan bahwa akan ada biaya tambahan yang diperlukan untuk benar-benar memesan.</p> 

Setelah pesanan terisi (yaitu seseorang menjual/membeli penawaran Anda), akun Anda akan dikreditkan oleh aset yang bersangkutan.

Perintah yang tidak terisi dapat dibatalkan setiap saat.