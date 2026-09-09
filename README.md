# 🛡️ Financial Fraud Detection & Risk Analytics Dashboard

## 📌 Proje Hakkında
Bu proje, finans sektöründe risk yönetimi ve veri analitiği süreçlerini modellemek amacıyla geliştirilmiş uçtan uca bir **Finansal Dolandırıcılık Tespit ve Erken Uyarı** çalışmasıdır. 6.3 milyon satırlık ham finansal işlem verisi; SQL tabanlı veri yönetimi, veri temizleme ve gelişmiş DAX metrikleri kullanılarak işlenmiş, ardından karar vericiler için profesyonel bir Power BI panosuna dönüştürülmüştür.

---

## 🔍 Çözülen Problem & Temel Bulgular
Geleneksel bankacılık sistemleri genellikle statik ve kural tabanlı algoritmalar kullanır. Bu projenin temel odak noktası, mevcut sistemlerin yetersizliklerini veriye dayalı olarak ifşa etmek ve suç anatomisini ortaya koymaktır:

* **Sistemin Kör Noktası:** Bankanın mevcut geleneksel güvenlik mekanizması (`isFlaggedFraud`), veri setindeki **8.213 gerçek dolandırıcılık vakasının yalnızca 16 tanesini** tespit edebilmiştir. Bu durum, kural tabanlı sistemlerin %99.8 oranında yetersiz kaldığını açıkça kanıtlamaktadır.
* **Suçun Anatomisi (İşlem Tipi Analizi):** Dolandırıcılık faaliyetlerinin rastgele olmadığını; **CASH_OUT (%50.12)** ve **TRANSFER (%49.88)** olmak üzere yalnızca iki temel işlem kanalında yoğunlaştığı tespit edilmiştir.
* **Hedef Profili (Bakiye Analizi):** Suçluların rastgele hesaplar yerine, normal operasyonel ortalamanın çok üzerinde (**1.5 Milyon+** ortalama bakiye) şişkin hesapları hedef seçtiği kanıtlanmıştır.

---

## 🛠️ Kullanılan Teknolojiler ve Araçlar
* **Veri İşleme & Yönetimi:** Python, SQL Server (Veritabanı Modelleme & İlişkisel Mimari)
* **İş Zekası & Veri Modelleme:** Power BI Desktop, DAX (Data Analysis Expressions)
* **Tasarım Yaklaşımı:** Kurumsal Dark Mode (Karanlık Tema) Veri Görselleştirme Standartları

---

## 📊 Öne Çıkan DAX Metrikleri
Projede kullanılan temel performans göstergeleri (KPI) ve iş zekası ölçüleri:
* `Toplam_Islem = COUNTROWS('Financial_Transactions')`
* `Toplam_Fraud = SUM('Financial_Transactions'[isFraud])`
* `Fraud_Orani = DIVIDE([Toplam_Fraud], [Toplam_Islem], 0)`
* `Toplam_Fraud_Tutar = CALCULATE(SUM('Financial_Transactions'[amount]), 'Financial_Transactions'[isFraud] = 1)`

---

## 🚀 Projenin İş Değeri (Business Impact)
Bu çalışma ile ham ve anlamsız milyonlarca satırlık veri yığını; kurumların zarar etmesine yol açan güvenlik açıklarını nokta atışı tespit eden, risk altındaki devasa finansal hacmi ($12.06$ milyar) tek ekrandan yönetmeyi sağlayan **proaktif bir karar destek mekanizmasına** dönüştürülmüştür.
