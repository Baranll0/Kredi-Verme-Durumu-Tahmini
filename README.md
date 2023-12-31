# Kredi Verme Durumu Tahmini
Bu uygulama, Doç. Dr. Emrah Aydemir'in "Uygulamalar ile Python ve Yapay Zekâ" kitabından verilen problemin örnek çözümüdür.

![Kredi Verme Durumu Tahmini](https://i.imgur.com/nrNgOXn.jpg)

Yapay Zeka tahminleri yapmak için işin en zor tarafı veriyi anlamanın yanı sıra veriyi birtakım filtrelerden geçirmek ve işe yaramayan kısımlarından arındırılarak hazır hale getirmektir. Bu zorluğa ön işleme aşaması denir.Belli aşamalardan sonra verinin içerisinde yer alan değerlerin kategorik mi yoksa sayısal  bir değer mi olduğu belirlenir. Yine aynı şekilde tahmin edilecek değerin de kategorik mi yoksa sayısal bir değer mi olduğu belirlenir. Buradaki çalışmada hazır verisetleri üzerinden testler yapılıyor.

## Verisetinin sütunları:
Bu veri seti _https://datahub.io/machine-learning/credit-g_ sitesinden alınarak kullanılmıştır.
- Mevcut hesabının durumu: Sıfır, 200'den az, 200'den fazla, hesap yok
- Süre: Kredinin süresi
- Kredi geçmişi: Kredi yok, daha önce ödenmiş kredi, daha önce ertelenmiş kredi, ödenmiş kredi, kritik kredi
- Amaç: Sıfır araç, ikinci el araç, ev eşyası, tadilat, eğitim, iş, diğer
- Kredi Miktarı: Bankadan istenen kredi miktarı
- Yatırım durumu: Banka hesaplarında yatırım amaçlı tuttuğu para miktarı
- Meslek süresi: İşsiz, 1 yıldan az, 1-4 yıl arası, 4-7 yıl arası, 7 yıldan fazla
- Gelirin taksite oranı: Harcamalarından artan gelirinin kredi taksitlerine oranı
- Medeni hali: Evli erkek, evli kadın, bekar erkek, bekar kadın, dul erkek, dul kadın
- Kefil durumu: kefil yok, eş başvuru, kefil var
- İkamet süresi: mevcut ikametinde ne zamandır oturduğu
- Önemli mallar: emlak, hayat sigortası, araba, bininen mülk yok
- Yaş: kaç yaşında olduğu
- Diğer ödemeler: Banka, mağaza, başka ödeme yok
- Ev durumu: Kira, sahibi, evsiz
- Var olan kredi miktarı: Ödemesi devam eden kredi miktarı
- Meslek: işsiz ya da vasıfsız işçi, vasıflı çalışan, serbest meslek, yüksek nitelikli çalışan
- Sorumlu kişiler: bakım sağlamaklı yükümlü kişi yüzdesi
- Telefon: Var, yok
- Yabancı Çalışan: Evet, hayır
- kredi verilmesi sonucu: İyi, Kötü

## Ön İşleme ve Veri Dönüşümü

Makine öğrenmesi ile verileri işleme tabi tutmak için tüm verileri sayısal değerlerden oluşmalıdır. Bu nedenle eğer kategorik metinsel değerler dosyada var ise bunların her birine bir sayı atanmalı ve dosya nihai olarak sadece sayılardan oluşmalıdır.

Eğitim verileri ile test verileri birbirinden ayrı dosyalar halinde programa verilmek istenirse _Egitim2Test1Parcala_ fonksiyonunun içinde verilerin rastgele 2/3'ünü eğitim ve 1/3'ü test için ayrılacaktır.

Sonrasında ise EğitimVerisi ve TestVerisi yazan iki farklı dosya çalışılan klasöre oluşturulacaktır. TÜm işlemler bittiği için artık makine öğrenmesi işlemlerine geçilebilir. Öncelikle hangi algoritmanın kullanacağına karar verilmelidir. Bu örnekte Random Forest ve Support Vector Machines kullanılmıştır. Bu işlem, *RandomForesttahminEt* ve *svm_tahmin_et* metotları içinde yazılmıştır.
