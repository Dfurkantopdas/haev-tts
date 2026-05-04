# haev-tts — Prerendered TTS audio for HAEV İbadet

Bu repo, [HAEV İbadet](https://github.com/Dfurkantopdas/) uygulamasının
**Türkçe meal seslendirmesi** için önceden üretilmiş `.mp3` dosyalarını
barındırır. Uygulama, kullanıcının Ayarlar → "TTS Sesi" altından bir ses
seçtiğinde, ayet ayet bu repodan dosyaları çeker (per-ayet tek dosya).

> **Üretici**: `tool/prepare_tts.py` (ElevenLabs API).
> **Şema, üretim akışı, lisans**: bkz. [`docs/TTS_REPO.md`](https://github.com/Dfurkantopdas/haev-reader/blob/main/haev/docs/TTS_REPO.md).

## Klasör yapısı

```
tts/
├── manifest.json                          # opsiyonel global özet
└── <voice_id>/                            # örn. el_ian_cartwell
    └── <meal_id>/                         # örn. diyanet
        ├── manifest.json                  # voice + meal kombosu özeti
        └── <surah_id>/                    # 1..114
            ├── manifest.json              # ayet listesi + sha256
            ├── 1.mp3
            ├── 2.mp3
            └── ...
```

## Mevcut sürümler

| Voice | Meal | Render durumu |
|-------|------|----------------|
| `el_ian_cartwell` (ElevenLabs Ian Cartwell, multilingual_v2) | `diyanet` (Diyanet Vakfı meali) | _Smoke (Fatiha + İhlâs + Felak + Nâs + Kevser)_ |

## Lisans

- **Ses dosyaları**: ElevenLabs Terms of Service. Sesler ücretli ElevenLabs
  hesabı ile üretilmiştir; HAEV İbadet uygulaması içinde dağıtım için
  kullanılır.
- **Meal metni (girdi)**: Diyanet Vakfı meali (alquran.cloud `tr.vakfi`,
  Tanzil arşivi). Detaylar için meal repo'sunun lisans bölümüne bakın.
