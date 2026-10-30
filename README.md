# Safety 4.0 Bootcamp – Mergen MPL.II.AUTO Otomatik Vakum Membran Pres Makinesi

**Öğrenci:** Muhammed Tarık Mengüç – 235541114  
**Bölüm:** Yazılım Mühendisliği  
**Makine:** Mergen Mekatronik Makina – MPL.II.AUTO Otomatik Vakum Membran Pres Makinesi (TWM Portal)

Bu repo, ilk 4 haftanın laboratuvar föylerinin seçilen makineye uygulanmış **kör test cevaplarını** içerir.

## İçerik

| Hafta | Laboratuvar | Çıktı | Evidence Pack |
|---|---|---|---|
| 1 | [Safety Architecture](labs/lab1-safety-architecture.md) | Safety Function Map | EP 03 |
| 2 | [IEC 62443 Mini Workshop](labs/lab2-iec62443.md) | Zone / Conduit Diagram | EP 05 |
| 3 | [Threat & Risk + Risk Matrix](labs/lab3-risk-matrix.md) | Risk Register | EP 04 |
| 4 | [Secure Remote Access](labs/lab4-secure-remote-access.md) | Secure Architecture | EP 02 + EP 06 |

## Makine Özeti

Makine; ahşap kapak, MDF ve mobilya sektöründe panellerin üzerine PVC, PP ve termoform folyoların yüksek sıcaklık (rezistans) ve vakum altında preslenerek yapıştırılmasını ve şekillendirilmesini sağlar.

- **Çalışma modu:** Otomatik / Manuel (hareketli kalıp sistemi)
- **Kontrol:** Delta PLC + Delta 7'' dokunmatik operatör paneli (HMI)
- **Tabla ve Tahrik:** 1400x3100 mm / 1400x2400 mm metal tabla; 20x20xMOD2 kramiyer & pinyon dişli sistemi; 0.37 kW 1400 d/d (R:1/10 S:40) redüktörlü motor tahriki
- **Vakum Sistemi:** 111 m³/saat yağlı vakum pompası (VPS) + 1'' aktüatörlü vakum açma/kapama vanası
- **Isıtma ve Sıcaklık:** 620 mm 190V 600W rezistans grubu + Kızılötesi (IR) temassız sıcaklık ölçüm sensörü
- **İkaz Sistemi:** Sesli ve görsel arıza / alarm ikazı

**Tehlikeli hareketler ve fiziksel tehlikeler:**
- Kramiyer-pinyon ile hareket eden ağır metal tablanın içeri/dışarı hareketi (uzuv ezilmesi, sıkışma, mekanik darbe).
- Yüksek çalışma sıcaklığına sahip rezistans grubu (ciddi termal yanık ve aşırı ısınmada yangın riski).
- 111 m³/saat kapasiteli vakum sistemi ve pres baskı haznesinin kapanması (vakum altında uzuv kapılması, giyotin tarzı sıkışma).

## Varsayımlar

Üretici kataloğunda emniyet ve ağ altyapısı ayrıntılı verilmediği için laboratuvar senaryoları kapsamında aşağıdakiler varsayılmıştır:

1. Makine tabla giriş/çıkış hatlarında optik ışık perdeleri (muting özellikli), pres kapağında mekanik/manyetik emniyet kilitleri ve operatör paneli ile tabla çevresinde Acil Stop (E-stop) butonları mevcuttur.
2. Emniyet zinciri: Işık perdesi + Kapak kilidi + E-stop + Rezistans aşırı sıcaklık limit termostatı → Safety PLC / Güvenlik Rölesi → Sürücü STO (Safe Torque Off) / Motor Ana Kontaktörü / Isıtıcı Ana Kontaktörü / Vakum acil tahliye valfi.
3. Delta PLC ve HMI sistemine uzaktan reçete optimizasyonu ve servis müdahalesi için fabrikada internete doğrudan açık bir **endüstriyel uzak bakım modülü (IoT Gateway)** sonradan eklenmiştir.

## Kaynaklar

- [TWM – Mergen MPL.II.AUTO İlan & Ürün Sayfası](https://twm.com.tr/tr/ilan/mpliiauto)
- [Mergen Machinery – Vakum Membran Pres Sistemleri](https://mergenmachinery.com)
- [AİMSAD – Ağaç İşleme Makine Sanayicileri Derneği](https://aimsaddergisi.com)

> Bu bir eğitim çıktısıdır, resmî denetim değildir.

