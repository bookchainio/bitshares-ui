# İzinler

Bitshares'de her bir hesap şunlara ayrılmıştır

* **Active Permission**: fonlar üzerinde kontrol ve
* **Owner Permission**: hesabı kontrol et.

Both can be defined in the `Permissions` tab of your account using so called *authorities* (see below) together with a so called *threshold* that has to be exceeded in order for a transaction to be valid.

## Yetkililer

BitShares'te bir *authority*, yetkili olan bir veya birden fazla varlıktan oluşan İşlemler, örneğin transferler veya işlemler.

Bir yetki, bir hesap adının bir veya birkaç çiftinden oluşur *weight*.

Geçerli bir işlem elde etmek için, imzalamadan gelen ağırlıkların toplamı tarafların izinlerde tanımlanan eşiği aşmaları gerekir.

# Örnekler

Kullanılan terminoloji ve bu terminolojiyi biraz aydınlatacak bazı örnekler üzerinde tartışalım -olayları kullanın. Etkin izinleriyle yeni bir hesap oluşturulduğunu varsayıyoruz aşağıda açıklandığı gibi ayarlayın. Aynı düzenin sahibi için de çalıştığını unutmayın. izinler!

## (Düz) Çoklu İmza

Düz çok imzalı bir şema, `N` varlıklarının bulunduğu `M` varlıklardan oluşur işlemin geçerli olabilmesi için imzalanması gerekir. Now, in BitShares, we have *weights* and a *threshold* instead of `M` and `N`. Hala bunu başarabiliriz aynı şeyi daha fazla esneklik ile şimdi göreceğimiz gibi.

Alice, Bob, Charlie ve Dennis'in ortak fonları olduğunu varsayalım. We want to be able to construct a valid transaction if only two of those agree. Hence a **2-of-4** (N-of-M) scheme can look as follows:

| Hesap         | Ağırlık  |
| ------------- | -------- |
| Alice         | 33%      |
| Bob           | 33%      |
| Charlie       | 33%      |
| Dennis        | 33%      |
| \---\---\---- | \---\--- |
| Eşik:         | 51%      |

Dört katılımcının da % 33 ağırlığı var, ancak eşik% 51 olarak belirlendi. Dolayısıyla dört ortakdan sadece ikisi işlemin geçerliliğini onaylamayı kabul etmelidir.

Alternatif olarak, 3'lük-4'lük bir şema oluşturabilmek için ağırlıkları 17'ye düşürebilir veya eşiği% 99'a yükseltebilirsiniz.

## (Düz) Esnek Çoklu İmza

Eşik ve ağırlıkları kullanarak artık fonlarımız üzerinde daha fazla esneklik sahibiyiz. Daha doğrusu, daha fazla sahibiz *control*. Farklı insanlar için ağırlıklar ayrı olabilir, örneğin. Alice, buraya para yatırmak istediğini varsayalım çok imzalı bir şemayla hırsızlığa karşı, ama aynı zamanda arkadaşlarına daha fazla kontrol teslim etmek istemiyor. Dolayısıyla, benzer bir otorite yaratırız:

| Hesap         | Ağırlık  |
| ------------- | -------- |
| Alice         | 49%      |
| Bob           | 25%      |
| Charlie       | 25%      |
| Dennis        | 10%      |
| \---\---\---- | \---\--- |
| Threshold:    | 51%      |

Artık fonlara Alice ve tek bir arkadaş tarafından erişilebilir ya da herkes tarafından erişilebilir. üç arkadaş birlikte.

## Çok Hiyerarşili Esnek Çoklu İmza

Şimdi basit çok hiyerarşik kurumsal hesap ayarlarına göz atalım. We are looking at a company that has a Chief of Financial Officer (CFO) and a some departments working for him, such as the Treasurer, Controller, Tax Manager, Accounting, etc. The company also has a CEO that wants to have spending privileges. Hence we construct an authority for the funds according to:

| Hesap         | Ağırlık  |
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
| Eşik:                     | 51%      |

Bu şema şunlara izin verir:

* para harcama CEO'su
* fon harcamaya Finans memuru şefi
* Hazine Müsteşarlığı ile birlikte Kontrolörle para harcamak
* Denetçi veya Sayman, Vergi Müdürü ve Muhasebe ile birlikte para harcamak.

Hence, a try of arbitrary depth can be spanned in order to construct a flexible authority to reflect mostly any business use-case.