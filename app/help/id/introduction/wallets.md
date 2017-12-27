# Dompet

Seperti yang mungkin sudah Anda perhatikan, aplikasi ini adalah aplikasi web dan berjalan di browser. Sambungan dibuat ke simpul terpercaya di jaringan itu berfungsi sebagai pintu gerbang ke ekosistem lainnya.

## Dompet awan

Jika Anda terdaftar dengan nama pengguna dan kata sandi, Anda memiliki dompet awan. Meskipun tidak ada yang disimpan secara teknis di awan, kami pengguna istilah Wallet Dye karena Anda bisa menggunakan kredensial ini (username dan password) dari browser web manapun waktu untuk mendapatkan akses ke akun Anda. Dompet awan hanya memungkinkan untuk satu akun untuk diakses sekaligus. Ini umumnya pilihan yang tepat untuk pengguna baru. Meskipun memungkinkan untuk mengubah kata kunci yang dibuat secara otomatis, kami tidak menyarankan untuk melakukannya pada saat ini. Tim bekerja dengan cara yang bertanggung jawab untuk mengelola perubahan kata sandi yang tidak memerlukan pengetahuan teknis. Kami akan membuat pengumuman setelah dilepaskan.

## Dompet lokal

Dompet lokal menciptakan database di dalam browser Anda. Ini berarti akses untuk dana Anda itu terkait dengan **browser itu saja**. Jika Anda mencoba mengakses dompet lokal dari komputer lain, atau browser lainnya, itu akan gagal kecuali Anda secara aktif mengimpor file cadangan Anda dari file cadangan browser asli. Itu Prosesnya sebenarnya mudah. Lihat mengelola[cadangan](/help/introduction/backups).

## Keamanan

Yakinlah bahwa server kami tidak memiliki akses ke dana Anda karena tidak ada kunci pribadi Anda pernah meninggalkan browser Anda. Sebagai gantinya, mereka dienkripsi dengan passphrase dan disimpan di database browser lokal Anda. Dengan demikian, seharusnya pastikan untuk memiliki [Cadangan](../introduction/backups.md) yang tepat dalam acara tersebut sesuatu terjadi pada komputer atau browser Anda.

## Manajemen

Antarmuka pengguna mampu membawa dan mengakses beberapa dompet terpisah masing-masing berisi beberapa akun dan sesuai dana. Anda dapat membuat, mencadangkan, dan mengganti dompet yang ada di `Settings->Wallets`.