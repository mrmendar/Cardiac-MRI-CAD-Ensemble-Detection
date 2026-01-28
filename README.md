Cardiac MRI CAD Ensemble Detection with EfficientNetB0 🩺
💻Bu proje, kardiyak MRI görüntülerinden Koroner Arter Hastalığı (CAD) teşhisi için geliştirilmiş, yüksek başarımlı bir karar destek sistemidir. Manuel analiz süreçlerindeki zaman kaybını ve uzmanlar arası yorum farklarını minimize etmeyi amaçlar.🚀
Proje Özeti (Project Abstract)Araştırma kapsamında, Kaggle üzerinde yer alan 63.425 görüntülük CAD Cardiac MRI Dataset kullanılmıştır. Veri seti %59,2 Normal ve %40,8 Hasta sınıfından oluşan dengeli bir yapıya sahiptir. Sistemin temel mimarisi olarak EfficientNetB0 seçilmiş ve 3-Fold Cross-Validation stratejisiyle eğitilen bir topluluk (ensemble) yapısı benimsenmiştir.
🏗️ Teknik Mimari (System Architecture)Proje, tek bir modelin önyargılarından arındırılmış, çoklu uzman görüşüne dayanan bir hiyerarşik yapı sunar:EfficientNetB0 Backbone: Ağ derinliği, genişliği ve çözünürlüğünü dengeli ölçeklendiren Compound Scaling teknolojisini kullanır.
MBConv Blokları: Mobile Inverted Bottleneck yapısı ile yüksek parametre verimliliği sağlar.
Squeeze-and-Excitation (SE): Patolojik bulgu taşıyan koroner dokulara odaklanan "dikkat" mekanizması sağlar.+2Ensemble Stratejisi: 3 farklı bağımsız modelin tahminleri, Weighted Soft Voting (Ağırlıklı Yumuşak Oylama) algoritması ile sentezlenerek nihai sonuca ulaşılır.
🛠️ Veri Ön İşleme (Preprocessing)Boyutlandırma: Görüntüler Bicubic Interpolation ile $224 \times 224$ piksel boyutuna getirilmiştir.
Transfer Learning: ImageNet üzerinde önceden eğitilmiş ağırlıklar kullanılarak Transfer Öğrenme avantajı sağlanmıştır.+1Normalizasyon: Piksel değerleri gradyan inişini stabilize etmek için $[0, 1]$ aralığına normalize edilmiştir.
📊 Performans Metrikleri (Performance)Test veri setinde elde edilen teknik başarılar şu şekildedir:+1MetrikDeğerKlinik AnlamıDoğruluk (Accuracy)%96,02Sistemin genel başarım oranı.+
Hassasiyet (Precision)%95,80Hasta teşhisindeki doğruluk payı.
Duyarlılık (Recall)%96,25Gerçek hastaları yakalama başarısı.+2F1-Skoru%96,02Dengeli performans ölçümü.+1Kritik Bulgular: Tıbbi açıdan en riskli hata olan "hastaya sağlıklı deme" (Yanlış Negatif) oranı minimize edilerek klinik güvenilirlik en üst düzeye çıkarılmıştır.
🖥️ Kullanıcı Arayüzü (GUI)Hekimlerin kullanımı için PyQt6 tabanlı geliştirilen arayüz şunları içerir:+2Gerçek Zamanlı Analiz: MRI kesitlerinin anlık teşhisi.+1Güven Skoru (Confidence Score): Teşhisin matematiksel olasılığının sunulması.+1Uzman Paneli: 3 bağımsız modelin bireysel tahminlerinin izlenmesi.
Kurulum:
# Depoyu klonlayın
git clone https://github.com/mrmendar/Cardiac-MRI-CAD-Ensemble-Detection.git

# Gerekli kütüphaneleri kurun
pip install -r requirements.txt

# Uygulamayı çalıştırın
python src/main.py

📬 İletişim (Contact)
Tuna KARAKÖSE 📧 tuna.karakose2001@gmail.com

🎓 Gazi Üniversitesi - Bilgisayar Mühendisliği 
