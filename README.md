# Eğitsel Oyun Mekaniği Analiz Sistemi (Python)

Bu depo, önceki içeriğin yerine **etik ve güvenli** bir öğrenme çerçevesi sunar.
Amaç; FPS türü oyun mekaniklerini **oyun belleğine müdahale etmeden** ve anti-cheat atlatma girişimi olmadan analiz etmektir.

## Önerilen İstek (Prompt)

Aşağıdaki metni bir yapay zekâ modeline ileterek modüler bir yol haritası isteyebilirsin:

```text
Python kullanarak, FPS oyunlarındaki temel mekanikleri teknik olarak analiz eden eğitsel bir simülasyon projesi geliştirmek istiyorum.
Proje tamamen akademik ve öğrenme amaçlı; gerçek oyuna bellek erişimi, hile, exploit veya anti-cheat atlatma içermemelidir.

Lütfen aşağıdaki başlıklar için adım adım rehber, örnek kod ve mantıksal açıklama hazırla:

1) Veri Modelleme ve Analiz Katmanı
- Replay/log/telemetry dosyalarından oyuncu pozisyonu, can, takım ve olay verisi nasıl okunur?
- Ham veriler nasıl normalize edilip analiz edilebilir hale getirilir?

2) World-to-Screen Matematiği (Simülasyon)
- 3B koordinatların 2B ekran düzlemine projeksiyonu nasıl çalışır?
- View/Projection matrisi kavramlarını örnek numpy kodlarıyla açıkla.

3) Nişan Geometrisi (Eğitsel)
- İki nokta arasındaki yaw/pitch açısı trigonometriyle nasıl hesaplanır?
- Hedef takipte yumuşatma (smoothing) ve filtreleme (ör. EMA) nasıl uygulanır?

4) Harici 2B Radar Görselleştirmesi
- tkinter veya pygame ile mini-map/radar paneli nasıl hazırlanır?
- Dünya koordinatlarını 2B radar koordinatına dönüştürme ve ikon çizimi nasıl yapılır?

5) Güvenlik ve Etik
- Anti-cheat sistemleri genel olarak hangi davranışları riskli görür?
- Projeyi güvenli tutmak için hangi sınırlar uygulanmalı (sadece offline/simülasyon verisi, belleğe erişim yok vb.)?

6) Proje Mimarisi
- Modüler klasör yapısı, test stratejisi ve küçük bir örnek uygulama iskeleti oluştur.
```

## Kapsam ve Sınırlar

- Gerçek oyun süreçlerine bağlanma yok.
- Bellek okuma/yazma yok.
- DLL injection, otomasyon veya hile mekanikleri yok.
- Sadece simülasyon, replay ve sentetik veri üzerinden analiz.

## Başlangıç Planı

1. `data/` altında örnek telemetry CSV/JSON oluştur.
2. `core/math3d.py` içinde vektör, matris, projeksiyon fonksiyonlarını yaz.
3. `analysis/aim_metrics.py` içinde açı, mesafe ve smoothing hesaplarını ekle.
4. `ui/radar.py` ile 2B radar ekranı üret.
5. `tests/` altında temel doğrulama testlerini yaz.
