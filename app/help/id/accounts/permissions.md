# Hak akses

Dalam BitShares, setiap akun dipisahkan menjadi

* **Izin Aktif**: kontrol atas dana dan
* **Izin Pemilik**: kontrol atas akun.

Keduanya dapat didefinisikan dalam tab `Permissions` akun Anda menggunakan disebut *otoritas* (Lihat di bawah) dengan disebut *ambang batas* yang melebihi batas dalam rangka untuk transaksi yang berlaku.

## Otoritas

Dalam BitShares sebuah *authority* terdiri dari satu atau banyak entitas yang memberi otorisasi tindakan, seperti transfer atau perdagangan.

Otoritas terdiri dari satu atau beberapa pasang nama akun dengan *berat*.

Untuk mendapatkan transaksi yang valid, jumlah bobot dari penandatanganan para pihak harus melebihi ambang batas sebagaimana didefinisikan dalam izin.

# Contoh

Mari kita bahas beberapa contoh untuk memberi penjelasan tentang terminologi yang digunakan dan use case. Kami berasumsi bahwa akun baru dibuat dengan izin aktifnya ditetapkan seperti yang dijelaskan di bawah ini. Perhatikan bahwa skema yang sama juga berlaku bagi pemiliknya izin!

## (Flat) Multi-Signature

Skema multi-tanda tangan datar terdiri dari entitas `M` entitas `N` harus masuk agar transaksi berlaku. Sekarang, di BitShares, kita punya *bobot* dan * ambang* daripada `M` dan `N`. Masih bisa kita capai Hal yang sama dengan fleksibilitas lebih seperti yang akan kita lihat sekarang.

Mari kita asumsikan, Alice, Bob, Charlie dan Dennis punya dana bersama. Kami ingin menjadi mampu membangun transaksi yang valid jika hanya dua yang setuju. Oleh karena itu a Skema**2-of-4** (N-of-M) dapat terlihat seperti berikut:

| Akun           | Berat    |
| -------------- | -------- |
| Alice          | 33%      |
| Bob            | 33%      |
| Charlie        | 33%      |
| Dennis         | 33%      |
| \---\---\----  | \---\--- |
| Batas minimum: | 51%      |

Keempat peserta tersebut memiliki bobot 33% namun ambang batasnya ditetapkan menjadi 51%. Makanya hanya dua dari empat kebutuhan untuk setuju memvalidasi transaksi.

Sebagai alternatif, untuk membangun skema 3-of-4, kita dapat menurunkan bobotnya untuk 17 atau meningkatkan ambang batas menjadi 99%.

## (Flat) Flexible Multi-Signature

Dengan ambang batas dan bobot, sekarang kita memiliki lebih banyak fleksibilitas atas dana kami, atau lebih tepatnya, kita memiliki lebih banyak*kontrol*. Misalnya, kita bisa terpisah bobot untuk orang yang berbeda. Mari asumsikan Alice ingin mengamankan dana di sini melawan pencurian dengan skema multi tanda tangan tapi dia juga tidak mau menyerahkannya banyak kontrol untuk teman-temannya. Oleh karena itu, kita menciptakan otoritas yang mirip dengan:

| Akun           | Berat    |
| -------------- | -------- |
| Alice          | 49%      |
| Bob            | 25%      |
| Charlie        | 25%      |
| Dennis         | 10%      |
| \---\---\----  | \---\--- |
| Batas minimum: | 51%      |

Sekarang dana bisa diakses oleh Alice dan satu teman atau oleh semua tiga teman bersama.

## Multi-Hierarchical Flexible Multi-Signature

Mari kita lihat persiapan akun korporat multi-hierarki yang sederhana. Kita sedang melihat perusahaan yang memiliki Chief Financial Officer (CFO) dan beberapa departemen yang bekerja untuknya, seperti Bendahara, Controller, Tax Manager, Akuntansi, dll. Perusahaan juga memiliki CEO yang ingin memiliki belanja hak istimewa. Oleh karena itu kami membangun kewenangan untuk dana sesuai dengan:

| Akun           | Berat    |
| -------------- | -------- |
| CEO.COMPANY    | 51%      |
| CFO.COMPANY    | 51%      |
| \---\---\----  | \---\--- |
| Batas minimum: | 51%      |

sedangkan CEO.COMPANY dan CFO.COMPANY memiliki otoritas sendiri. Contohnya, akun CFO.COMPANY bisa terlihat seperti:

| CFO.COMPANY               | Berat    |
| ------------------------- | -------- |
| Chief.COMPANY             | 51%      |
| Treasurer.COMPANY         | 33%      |
| Controller.COMPANY        | 33%      |
| Tax Manager.COMPANY       | 10%      |
| Accounting.COMPANY        | 10%      |
| \---\---\---\---\---\---- | \---\--- |
| Threshold:                | 51%      |

This scheme allows:

* the CEO to spend funds
* the Chief of Finance Officer to spend funds
* Treasurer together with Controller to spend funds
* Controller or Treasurer together with the Tax Manager and Accounting to spend funds.

Hence, a try of arbitrary depth can be spanned in order to construct a flexible authority to reflect mostly any business use-case.