# Kazakça Veri Seti Üzerinde Sentiment Analiz

Bu proje, Kazakça veri seti kullanarak Python ile sentiment analiz yapmayı amaçlamaktadır. Projede kullanılan kütüphaneler arasında NLTK, Keras, TensorFlow, Numpy ve Pandas bulunmaktadır.

## Proje İçeriği

- **Veri Ön İşleme**: NLTK ve Pandas kullanılarak metin verisinin temizlenmesi ve hazırlanması.
- **Model Eğitimi**: Keras ve TensorFlow kullanılarak derin öğrenme modellerinin eğitimi.
- **Sonuçların Analizi**: Model performansının değerlendirilmesi ve sonuçların görselleştirilmesi.

## Kullanılan Teknolojiler

- **Python**: Ana programlama dili
- **NLTK**: Doğal dil işleme kütüphanesi
- **Keras**: Derin öğrenme API'si
- **TensorFlow**: Makine öğrenimi kütüphanesi
- **Numpy**: Sayısal hesaplama kütüphanesi
- **Pandas**: Veri işleme ve analiz kütüphanesi

## Kurulum

Projeyi çalıştırmak için aşağıdaki adımları izleyin:
1. Depoyu klonlayın:

git clone https://github.com/SeAkbs/Sentiment-Analysis.git

2.Gerekli kurulumları yapın

 Anaconda (https://www.anaconda.com/download/)
 Tensorflow GPU için;
 Tensorflow kurarken iki seçeneğiniz var. CPU veya GPU. Eğer uygun ekran kartınız varsa kesinlikle GPU için kurulum yapın, CPU'ya göre daha hızlı eğitim gerçekleşecek. Nvidia'dan farklı bir ekran kartınız varsa CPU için kurulum yapmanız gerekiyor. Sadece Nvidia ekran kartları destekleniyor. Ekran kartınızda CUDA compute capability 3.5'den büyükse Tensorflow'u GPU için kurabilirsiniz. Aşağıdaki linkten ekran kartınız uygun mu kontrol edebilirsiniz.

ÖNEMLİ NOT: Kursu sorunsuz takip edebilmek için Tensorflow'un 1.14 sürümünü kurmanızı tavsiye ederim. Aşağıdaki kurulumların tamamı 1.14 sürümü içindir.

https://developer.nvidia.com/cuda-gpus

1. Tensorflow CPU

Komut penceresini açın. (Windows+R ile çalıştırı açıp cmd yazabilirsiniz)

Açılan komut penceresinde aşağıdaki pip install'u çalıştırın 

C:\> pip install --upgrade tensorflow==1.14

CPU için kurulum bu kadar. Komut penceresinde "python" yazıp aşağıdaki kod ile test edebilirsiniz:

>>> import tensorflow as tf>>> hello = tf.constant('Hello, TensorFlow!')>>> sess = tf.Session()>>> print(sess.run(hello))

Not: import tensorflow as tf yazdıktan sonra FutureWarning alabilirsiniz. Bu bir hata değil sadece numpy ile ilgili bir uyarı. Kodlarınız sorunsuz çalışacaktır.

Sonuç olarak "Hello, Tensorflow!" göreceksiniz.

2. Tensorflow GPU

Tensorflow'u GPU için kurmak istiyorsanız öncesinde CUDA ve CuDNN kurmanız gerekiyor.

2a.CUDA

https://developer.nvidia.com/cuda-downloads

CUDA 10.0 indirip kurun. Farklı bir sürüm kurmayın diğer sürümlerde çalışmaz.

Kurulum bittikten sonra bilgisayara sağ tıklayıp özellikleri seçin.

Gelişmiş sistem ayarları/ortam değişkenleri

Açılan pencerede sistem değişkenleri bölümünden Path'i seçip düzenleye tıklayın.

Aşağıdaki adresleri Yeni'ye tıklayarak tek tek ekleyin (Kurulumu farklı bir yere yaptıysanız o adresi verin)

NVIDIA Installer failed / NVIDIA kurulum programı başarısız hatası alırsanız çözümü aşağıdadır.

C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.0\bin
C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.0\libnvvp
C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.0\extras\CUPTI\libx64

2b. CuDNN

https://developer.nvidia.com/rdp/cudnn-archive

İndirmek için üyelik almanız gerekiyor.

CUDNN 7.4.2 for CUDA tool kit 10.0'ı seçip işletim sisteminize göre indirin.

İnen zip dosyasında bin klasörüne gidip  cudnn64_7.dll dosyasını kopyalayın.

Bu dosyayı Program Files'da CUDA'nın içerisindeki bin dosyasına yapıştırın.

Bu adres default olarak aşağıdaki gibi olacaktır.

C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.0\bin

2c. GPU Güncelleme

http://www.nvidia.com.tr/drivers

Ekran kartı sürücünüzü güncelleyin.

2d. Tensorflow GPU

Komut penceresini açın. (Windows+R ile çalıştırı açıp cmd yazabilirsiniz)

Açılan komut penceresinde aşağıdaki pip install'u çalıştırın (bu komut 1.14 sürümünü kuracaktır):

C:\> pip install --upgrade tensorflow-gpu==1.14

3. Gerekli kütüphaneleri yükleyin:
   ```bash
   pip install tensorflow (CPU)
   pip install tensorflow-gpu
   pip install nltk
   pip install gensim
   
