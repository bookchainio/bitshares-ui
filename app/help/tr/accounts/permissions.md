# İzinler

Bitshares'de her bir hesap şunlara ayrılmıştır

* **Active Permission**: fonlar üzerinde kontrol ve
* **Owner Permission**: Hesap Kontrolü.

Both can be defined in the `Permissions` tab of your account using so called *authorities* (see below) together with a so called *threshold* that has to be exceeded in order for a transaction to be valid.

## Yetkililer

BitShares'te bir *authority*, yetkili olan bir veya birden fazla varlıktan oluşan İşlemler, örneğin transferler veya ticaretler.

Bir yetki, bir hesap adının bir veya birkaç çiftinden oluşur *weight*.

Geçerli bir işlem elde etmek için, imzaların ağırlıklarının toplamı tarafların izinlerinde tanımlanan barajı aşmaları gerekir.

# Örnekler

Kullanılan terminoloji ve bu terminolojiyi biraz aydınlatacak bazı örnekler üzerinde tartışalım -olayları kullanın. Etkin izinlerle yeni bir hesap oluşturulduğunu varsayıyoruz aşağıda açıklandığı gibi ayarlayın. Mal sahibi içinde aynı düzenin çalıştığını unutmayın!

## (Düz) Çoklu İmza

Çok imzalı basit bir şema, işlemin geçerli olması için `N`' lerin imzalaması gereken `M` kavramlardan oluşur. Now, in BitShares, we have *weights* and a *threshold* instead of `M` and `N`. Hala bunu başarabiliriz aynı şeyi daha fazla esneklik ile şimdi göreceğimiz gibi.

Alice, Bob, Charlie ve Dennis'in ortak fonları olduğunu varsayalım. Ortaklardan yalnızca ikisi katılıyorsa, geçerli bir işlem oluşturabilmek istiyoruz. Hence a **2-of-4** (N-of-M) scheme can look as follows:

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

Şimdi basit çok hiyerarşik kurumsal hesap ayarlarına göz atalım. Bir Mali İşler Sorumlusu (CFO) ve bazıları Sayıştay, Kontrolör, Vergi Müdürü, Muhasebe gibi kendisi için çalışan departmanlar. The company also has a CEO that wants to have spending privileges. Dolayısıyla fonlara aşağıdakilere göre bir otorite oluşturuyoruz:

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