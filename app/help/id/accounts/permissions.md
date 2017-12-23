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

Let's assume, Alice, Bob, Charlie and Dennis have common funds. We want to be able to construct a valid transaction if only two of those agree. Hence a **2-of-4** (N-of-M) scheme can look as follows:

| Account       | Weight   |
| ------------- | -------- |
| Alice         | 33%      |
| Bob           | 33%      |
| Charlie       | 33%      |
| Dennis        | 33%      |
| \---\---\---- | \---\--- |
| Threshold:    | 51%      |

All four participants have a weight of 33% but the threshold is set to 51%. Hence only two out of the four need to agree to validate the transaction.

Alternatively, to construct a 3-of-4 scheme, we can either decrease the weights to 17 or increase the threshold to 99%.

## (Flat) Flexible Multi-Signature

With the threshold and weights, we now have more flexibility over our funds, or more precisely, we have more *control*. For instance, we can have separate weights for different people. Let's assume Alice wants to secure here funds against theft by a multi-signature scheme but she does not want to hand over too much control to her friends. Hence, we create an authority similar to:

| Account       | Weight   |
| ------------- | -------- |
| Alice         | 49%      |
| Bob           | 25%      |
| Charlie       | 25%      |
| Dennis        | 10%      |
| \---\---\---- | \---\--- |
| Threshold:    | 51%      |

Now the funds can either be accessed by Alice and a single friend or by all three friends together.

## Multi-Hierarchical Flexible Multi-Signature

Let's take a look at a simple multi-hierarchical corporate account setup. We are looking at a company that has a Chief of Financial Officer (CFO) and a some departments working for him, such as the Treasurer, Controller, Tax Manager, Accounting, etc. The company also has a CEO that wants to have spending privileges. Hence we construct an authority for the funds according to:

| Account       | Weight   |
| ------------- | -------- |
| CEO.COMPANY   | 51%      |
| CFO.COMPANY   | 51%      |
| \---\---\---- | \---\--- |
| Threshold:    | 51%      |

whereas CEO.COMPANY and CFO.COMPANY have their own authorities. For instance, the CFO.COMPANY account could look like:

| CFO.COMPANY               | Weight   |
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