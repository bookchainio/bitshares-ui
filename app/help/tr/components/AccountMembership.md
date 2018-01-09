[# lifetime]

### Ücretlerden {feesCashback}% Geri Ödeme Alın

Ömür boyu üyeler yaptıkları her işlemde ödedikleri tutarda {feesCashback}% oranında geri ödeme alırlar ve kayıt yaptırdıkları veya ağa başvururusu için referans oldukları kullanıcılardan referans geliri kazanmaya hak kazanırlar. Bir ömür boyu üyelik sadece {price}.

[# ücret-bölüm]

#### Ücret Bölümü

{account} her zaman işlem ücreti öder, bu ücret birkaç farklı hesap arasında bölünmektedir. Ağ {networkFee}% oranında bir kesinti alır ve {account} 'a referans olan Ömür Boyu Üye {lifetimeFee}% oranında bir kesinti alır.

The *registrar* is the account that paid the transaction fee to register {account} with the network. The registrar gets to decide how to divide the remaining {referrerTotalFee}% between themselves and their own *Affiliate Referrer* program.

{account}'s registrar chose to share {referrerFee}% of the total fee with the *Affiliate Referrer* and keep {registrarFee}% of the total fee for themselves.

#### Bekleyen Ücretler

Fees paid by {account} are divided among the network, referrers, and registrars once every maintenance interval ({maintenanceInterval} seconds). The next maintenance time is {nextMaintenanceTime}.

#### Katılım Ücretleri

Most fees are made available immediately, but fees over {vestingThreshold} (such as those paid to upgrade your membership or register a premium account name) must vest for a total of {vestingPeriod} days.