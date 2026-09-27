# chatbox yerel yardımcısı

[chatbox](https://chatbox.poetas.com.tr) için isteğe bağlı, ileri düzey bir
yardımcı program. Bu bilgisayarda arka planda çalışır; uygulama onun içinden,
kendi adresinde (`http://127.0.0.1:47810`) açılır.

- Belgeleriniz, sohbetleriniz ve ayarlarınız yardımcının klasöründe durur;
  tarayıcı verisini silmek onları etkilemez.
- OpenRouter anahtarınız işletim sisteminin anahtar zincirinde durur;
  tarayıcıya hiç girmez.
- Klasörleriniz her tarayıcıda izlenir; değişince haber verir.

Şimdilik yalnız **macOS** (Apple Silicon ve Intel).

## Kurulum

Terminal'de:

```bash
curl --proto '=https' --tlsv1.2 -LsSf https://github.com/arifemreahmetbeyzade-sudo/chatbox/releases/latest/download/chatbox-helper-installer.sh | sh
```

Yeni bir Terminal penceresinde:

```bash
chatbox-helper setup   # oturum açılınca kendiliğinden başlasın
chatbox-helper open    # uygulamayı aç
```

Arşivi tarayıcıyla indirip açmayın: imzasız olduğu için macOS engeller.
Yalnız yukarıdaki komutu kullanın.

## Güncelleme ve kaldırma

```bash
chatbox-helper update
chatbox-helper uninstall               # verileriniz ve anahtarınız kalır
chatbox-helper uninstall --purge-data  # verileriniz ve anahtarınız da silinir (geri alınamaz)
```

## Gizlilik

Yardımcı yalnız `127.0.0.1`'i dinler. Kendisi dışarıya yalnız OpenRouter'a
(sohbet ve bulut yöntemiyle belge işleme; anahtarı yardımcı ekler) ve
GitHub'a (günde en çok bir kez sürüm denetimi) bağlanır; GitHub'a kullanıcı
verisi gitmez. Arayüz, "Bilgisayarımda" yönteminde belge işleme modelini bir
kez Hugging Face'ten indirir.

Lisans: Apache-2.0.

---

Bu depo yalnız **sürümleri** taşır (kurulum betiği ve macOS arşivleri). Kaynak
kod burada değildir. Hata ve öneriler için: chatbox@poetas.com.tr
