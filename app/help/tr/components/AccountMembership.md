[# lifetime]

### Ücretlerden {feesCashback}% Geri Ödeme Alın

Ömür boyu üyeler yaptıkları her işlemde ödedikleri tutarda {feesCashback}% oranında geri ödeme alırlar ve kayıt yaptırdıkları veya ağa başvururusu için referans oldukları kullanıcılardan referans geliri kazanmaya hak kazanırlar. Bir ömür boyu üyelik sadece {price}.

[# ücret-bölüm]

#### Ücret Bölümü

{account} her zaman işlem ücreti öder, bu ücret birkaç farklı hesap arasında bölünmektedir. Ağ {networkFee}% oranında bir kesinti alır ve {account} 'a referans olan Ömür Boyu Üye {lifetimeFee}% oranında bir kesinti alır.

*kayıt memuru*, {account} 'ı ağa kaydetmek için işlem ücretini ödeyen hesaptır. Kayıt memuru, kalan {referrerTotalFee}% oranının kendileri ile kendi *İştirakçi Referansı* arasında nasıl pay edileceğine karar verir.

{account}'nın kayıt memuru toplam ücretin {referrerFee}%'sini *İştirakçi Referansı* ile paylaşmayı ve toplam ücretin {registrarFee}%'sini kendileri için tutmayı tercih eder.

#### Bekleyen Ücretler

{account} tarafından ödene ücretler her bakım aralığında ({maintenanceInterval} zamanı) ağ, referanslar ve kayıt memurları arasında bölünür. Bir sonraki bakım zamanı {nextMaintenanceTime}.

#### Katılım Ücretleri

Çoğu ücretler hemen kullanılabilir hale getirilir, fakat {vestingThreshold} üzerindeki ücretler (üyeliğinizi yükseltmek veya bir premium hesap adı kaydetmek için ödenenler gibi) toplam {vestingPeriod} gün için hak edilmelidir.