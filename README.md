# Algerian Forest Fires: FWI Tahmini

Bu proje, **Algerian Forest Fires Veri Seti** kullanılarak **Fire Weather Index (FWI)** özniteliğinin tahmin edilmesi üzerine geliştirilmiştir. Projede, farklı makine öğrenimi algoritmaları uygulanarak modeller oluşturulmuş ve bu modellerin performansları karşılaştırılmıştır.

## 📋 Veri Seti Hakkında

Algerian Forest Fires veri seti, Cezayir'in iki bölgesine ait 244 örneği içermektedir. Bu veri seti, her biri 122 örnekten oluşan iki farklı bölgedeki yangın verilerini içermektedir. **11 bağımsız değişken** ve **1 bağımlı değişken (FWI)** içeren veri seti, yangın hava indeksinin (FWI) tahmini için kullanılmıştır.

- **Bağımsız Değişkenler (X):**
  - Rain (Yağış)
  - Temperature (Sıcaklık)
  - Relative Humidity (Bağıl Nem)
  - Wind Speed (Rüzgar Hızı)
  - Fine Fuel Moisture Code (FFMC)
  - Duff Moisture Code (DMC)
  - Drought Code (DC)
  - Initial Spread Index (ISI)
  - Month (Ay)
  - Day (Gün)
- **Bağımlı Değişken (Y):**
  - Fire Weather Index (FWI)

Veri seti sınıf bilgisi hariç tutularak **FWI**'ın tahmini için düzenlenmiştir.

**Veri Setine Ulaşım:**  
[Algerian Forest Fires Dataset - UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/Algerian+Forest+Fires+Dataset)

---

## 🚀 Kullanılan Algoritmalar

Proje kapsamında aşağıdaki algoritmalar uygulanmıştır:

1. **Destek Vektör Regresyonu (SVR)**:
   - Doğrusal olmayan ilişkilere sahip veri setlerinde oldukça başarılı bir algoritmadır. Bu projede SVR modeli kullanılarak FWI tahmini yapılmıştır.
   - Kullanılan Çekirdek: `RBF (Radial Basis Function)`

2. **Polinom Regresyon (PR)**:
   - Veri setindeki doğrusal olmayan ilişkileri yakalamak için çoklu terimlere dayalı regresyon modeli uygulanmıştır.

3. **Rastgele Orman Regresyonu (RFR)**:
   - Rastgele ormanlar, karar ağaçlarının bir ensemble (topluluk) modeli olarak çalışır. Bu projede FWI tahmini için kullanılmıştır.

---

## ⚙️ Kurulum ve Çalıştırma

Projeyi çalıştırmak için aşağıdaki adımları izleyebilirsiniz:

### 1. Gerekli Kütüphanelerin Yüklenmesi
```bash
pip install pandas numpy scikit-learn matplotlib
```

### 2. Kodun Çalıştırılması
Python dosyasını çalıştırarak modellerin eğitimi ve test sonuçlarını görebilirsiniz:
```bash
python algerian_forest_fire.py
```

---

## 📊 Sonuçlar ve Performans Karşılaştırması

Her modelin performansı aşağıdaki değerlendirme metrikleri kullanılarak ölçülmüştür:
- **MAE (Mean Absolute Error):** Ortalama mutlak hata.
- **MSE (Mean Squared Error):** Ortalama kare hata.
- **R² (R-Squared):** Belirleme katsayısı.

### Performans Özeti:
| Model   | Eğitim MAE | Test MAE | Eğitim R² | Test R² |
|---------|------------|----------|-----------|---------|
| **SVR** | 0.034      | 0.040    | 0.972     | 0.965   |
| **PR**  | 0.048      | 0.052    | 0.948     | 0.940   |
| **RFR** | 0.027      | 0.032    | 0.985     | 0.980   |

- **RFR** en düşük hata oranı (MAE ve MSE) ve en yüksek R² skoruyla en iyi performansı göstermiştir.
- **SVR**, güçlü bir performans sergileyerek ikinci sırada yer almıştır.
- **PR**, diğer modellere kıyasla daha düşük performans sergilese de doğrusal olmayan ilişkileri modellemek için etkili bir yöntem olmuştur.

---

## 📈 Görselleştirme

Modellerin tahmin performanslarını karşılaştırmak için aşağıdaki görseller üretilmiştir:

1. **Gerçek ve Tahmini Değerlerin Dağılımı**:
   - Scatter plot ile her modelin tahmin değerleri ve gerçek değerleri karşılaştırılmıştır.
2. **MAE ve R² Karşılaştırması**:
   - Eğitim ve test setlerinin performans metriklerini kıyaslayan bar grafikleri.

---

## 🛠️ Gelecek Çalışmalar

1. Daha karmaşık modellerin (ör. Gradient Boosting, XGBoost) uygulanması.
2. Bölgesel bazda farklı modellerin performanslarının ayrı ayrı analiz edilmesi.
3. Veri setinde daha fazla özellik mühendisliği yapılarak model performanslarının artırılması.

