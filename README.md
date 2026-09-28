# chatbox yerel yardımcısı

[chatbox](https://chatbox.poetas.com.tr) için isteğe bağlı, ileri düzey bir
yardımcı program. Bu bilgisayarda arka planda çalışır; uygulama onun içinden,
kendi adresinde (`http://127.0.0.1:47810`) açılır.

- Belgeleriniz, sohbetleriniz ve ayarlarınız yardımcının klasöründe durur;
  tarayıcı verisini silmek onları etkilemez.
- OpenRouter anahtarınız işletim sisteminin anahtar zincirinde durur;
  elle girerken tarayıcıdan bir kez yardımcıya gönderilir; tarayıcıda saklanmaz.
- Klasörleriniz her tarayıcıda izlenir; değişince haber verir.

Şimdilik yalnız **macOS** (Apple Silicon ve Intel).

## Kurulum ve güncelleme

Kurulum komutunu yalnız **https://chatbox.poetas.com.tr/yardimci** sayfasından
alın. Komut sabit bir sürümü indirir ve kurulum betiğinin parmak izini
(SHA-256) o sayfadaki değerle karşılaştırır; tutmazsa hiçbir şey kurmaz.

Kurduktan sonra, yeni bir Terminal penceresinde:

```bash
chatbox-helper setup   # oturum açılınca kendiliğinden başlasın
chatbox-helper open    # uygulamayı aç
```

Arşivi tarayıcıyla indirip açmayın: imzasız olduğu için macOS engeller.

`chatbox-helper update` yeni sürüm olup olmadığını söyler; güncellemek için
sitedeki komutu yeniden çalıştırın, ardından `chatbox-helper setup`.

## Kaldırma

```bash
chatbox-helper uninstall               # verileriniz ve anahtarınız kalır
chatbox-helper uninstall --purge-data  # verileriniz ve anahtarınız da silinir (geri alınamaz)
```

## Gizlilik

Yardımcı yalnız `127.0.0.1`'i dinler. Kendisi dışarıya yalnız OpenRouter'a
(sohbet ve bulut yöntemiyle belge işleme; anahtarı yardımcı ekler) ve
GitHub'a (günde en çok bir kez sürüm denetimi) bağlanır; GitHub'a kullanıcı
verisi gitmez. Arayüz Hugging Face'ten herkese açık model dosyaları indirir:
"Bilgisayarımda" yönteminde belge işleme modelini (bir kez), "OpenRouter ile"
yönteminde yalnız parça ve ücret tahmini için belirteç dosyalarını; bunlara
kullanıcı verisi gitmez (ölçüm: spikes/privacy-audit/REPORT.md).

Lisans: Apache-2.0.

---

Bu depo yalnız **sürümleri** taşır (kurulum betiği ve macOS arşivleri). Kaynak
kod burada değildir. Hata ve öneriler için: chatbox@poetas.com.tr
