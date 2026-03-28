English Dictionary

Türkçe–İngilizce kelime sözlüğü ve çeviri arayüzü içeren küçük bir proje. Kelimeler yerel bir JSON dosyasında saklanır; web arayüzü ise Google Translate’un herkese açık uç noktası üzerinden canlı çeviri yapar.

Özellikler

- Komut satırı sözlük (`core.py`): Kelime ekleme, silme, arama, çeviri ve harfe göre listeleme. Veriler `data.json` içinde tutulur.
- Masaüstü arayüz (`gui.py`): Tkinter ile basit bir pencere; `core.py` ile aynı veri dosyasını kullanır.
- Web çeviri sayfası (`translate.html`): Tek sayfalık, koyu temalı arayüz. Tarayıcıda açılır; internet gerekir.

Gereksinimler

- Python 3 (CLI ve GUI için)
- Standart kütüphaneler: `json`, `tkinter` (GUI için; Windows’ta genelde Python ile birlikte gelir)

 Proje yapısı

| Dosya | Açıklama |
|--------|-----------|
| `core.py` | `EnglishDictionary` sınıfı ve CLI menüsü |
| `gui.py` | Tkinter tabanlı arayüz |
| `data.json` | İngilizce → Türkçe eşleşmeleri (JSON) |
| `translate.html` | “Translate with Denis” web arayüzü |
| `core.spec` / `build/` | PyInstaller ile paketleme çıktıları (varsa) |

 Çalıştırma

 Komut satırı sözlük

Proje klasöründe:

```bash
python core.py
```

Menüden seçenekleri kullanarak kelime ekleyebilir, silebilir ve arayabilirsiniz.

 Masaüstü (GUI)

```bash
python gui.py
```

 Web çeviri sayfası

`translate.html` dosyasını çift tıklayarak veya tarayıcıya sürükleyerek açın. Yerel dosya (`file://`) ile açıldığında çeviri isteği tarayıcıdan Google’a gider; bazı ortamlarda CORS veya güvenlik ayarları etkileyebilir—gerekirse basit bir yerel sunucu kullanın:

```bash
 Örnek (Python 3)
python -m http.server 8080
```

Sonra tarayıcıda `http://localhost:8080/translate.html` adresine gidin.

 `translate.html` kısayolları ve notlar

- Dilleri değiştir (⇄): `Ctrl` tuşuna kısa süre içinde iki kez basın (çift tıklama benzeri). Arada başka tuşa basılırsa sıfırlanır (ör. `Ctrl+C` ile karışmaması için).
- Çeviri, yazmayı bıraktıktan yaklaşık 1 saniye sonra otomatik tetiklenebilir; Çevir ile de manuel çalıştırılır.
- Metin uzunluğu üst sınırı: 500 karakter (sayfadaki sayaçla gösterilir).

 Veri dosyası

- `data.json` yoksa veya bozuksa program boş sözlük ile başlar.
- Yedekleme için dosyayı düzenli olarak kopyalayın.

 Lisans ve harici servisler

- `translate.html` içindeki çeviri istekleri Google Translate ile uyumlu herkese açık bir URL üzerinden yapılır; kullanım koşulları Google’a aittir.
- Bu depo kişisel/öğrenme amaçlıdır; üretim kullanımı için resmi çeviri API’leri değerlendirilmelidir.

---

**Translate with Denis** — `translate.html` içindeki başlık ve logo bu web arayüzüne aittir.
