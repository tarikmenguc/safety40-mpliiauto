# Lab 3 – Threat & Risk + Risk Matrix

**Makine:** Mergen MPL.II.AUTO Otomatik Vakum Membran Pres · **Çıktı:** Risk Register → EP 04 Risk Assessment

Skor = L × S × E (her biri 1–3) · Kritik 18–27 · Yüksek 9–17 · Orta 4–8 · Düşük 1–3  
**Kural:** S=3 (Ağır yaralanma / can kaybı riski) ise skor düşük olsa bile senaryo öne alınır.

## Risk Register

| # | Senaryo (kim → kapı → ne yapar → zincir → fiziksel sonuç) | L | S | E | Skor | Öncelik |
|---|---|---|---|---|---|---|
| 1 | Dış saldırgan → İnternete açık uzak bakım modülü (IoT Gateway) → Delta PLC / Safety lojiğine müdahale edip ışık perdesi muting fonksiyonunu sürekli açık bırakır ve tabla motorunu tetikler → Operatör folyoyu düzeltirken 1400x3100 mm kramiyer-pinyon tabla içeri sürülür → **Kalıcı kol/gövde ezilmesi ve kemik kırığı** | 2 | 3 | 3 | 18 Kritik | 1 |
| 2 | Ofis çalışanı → Oltalama (phishing) e-postası → Fidye yazılımı Delta HMI'ı kilitler ve IR sensör PID kontrolünü devre dışı bırakır → Rezistanslar kontrolsüz ısınarak folyoyu ve ahşap tablasını tutuşturur → **Yangın, zehirli duman soluma ve 2. derece termal yanık** | 3 | 2 | 2 | 12 Yüksek | 3 |
| 3 | Bakım personeli / Taşeron → Kilitsiz PLC USB/seri portu → Kramiyer-pinyon strok limit parametresini veya vakum presi kapanma güvenlik gecikmesini değiştirir → Bakım/temizlik sırasında pres kapağı ve tabla kontrolsüz kapanır → **Uzuv kopması / ölümcül ezilme** | 1 | 3 | 1 | 3 Düşük | 2 |

## Sorular

**1. En yüksek öncelikli senaryonuz hangisi? Neden?**
Senaryo 1 (Skor 18 – Kritik). Çünkü saldırgan doğrudan internet üzerinden güvenlik katmanını (optik ışık perdesi muting mekanizmasını) devre dışı bırakabilmekte ve operatörün en savunmasız olduğu anda (folyo hazırlığı ve kalıp hizalama esnasında) kramiyer tahrikli ağır tablayı hareket ettirerek doğrudan kalıcı fiziksel uzuv kaybına yol açabilmektedir.

**2. S=3 olup skoru düşük kalan senaryonuz var mı? Nasıl görünür kılacaksınız?**
Evet, Senaryo 3 (Skor 3). Gerçekleşme olasılığı (L=1) ve maruz kalma sıklığı (E=1) düşük olduğu için matematiksel skoru düşük kalmaktadır; ancak şiddet puanı $S=3$ (ölümcül ezilme / uzuv kopması) seviyesindedir. Kural gereği Senaryo 2'nin önüne alınarak 2. önceliğe taşınmıştır. Bu senaryoyu yönetilebilir ve görünür kılmak için:
- Delta PLC panosu fiziksel kilit altına alınacak ve anahtar yalnızca tesis emniyet mühendisinde bulunacaktır.
- Kullanılmayan USB ve Ethernet mühendislik portlarına fiziksel port kilitleri (port blocker) takılacaktır.
- PLC lojik ve parametre değişiklikleri firmware checksum doğrulamasına tabi tutulacak ve periyodik denetim takvimine bağlanacaktır.
