<div align="center">
<img src="https://user-images.githubusercontent.com/33163650/234251275-3ec9372b-4fcd-4c19-bc8d-4f0668cbd88f.png" width="160" height="160">
</div>

<h1 align="center"> INTELLIUM Label Text Classification </h1>


*  [:fire: Geliştiriciler](#fire-geliştiriciler)
*  [:hash: Amaç](#hash-amaç)
*  [:hash: Çalışma Mantığı Nedir?](#hash-çalışma-mantığı-nedir)
*  [:hash: Veri Çoğaltma İşlemi](#hash-veri-cogaltma-islemi)
*  [:hash: Veri Temizleme İşlemi](#hash-veri-temizleme-islemi)


# :fire: Geliştiriciler
| İsim Soyisim | 
| :--- | 
| [Esra ÇELİK](https://github.com/esra71) | 
| [Burak ÖZDEMİRTAŞ](https://github.com/burakozdemirtas) |
| [Hussein M. ÇAKIR](https://github.com/husseincakir) |

# :hash: Amaç
<p align="justify">
Ticket verilerini text classification ile kategorize etmenin amacı, büyük veri setleri içindeki karmaşık verileri anlamak ve analiz etmek için bir yöntem sağlamaktır. Bu tür veriler, örneğin bir destek merkezinde müşteri şikayetleri gibi, genellikle manuel olarak sınıflandırılması zor ve zaman alıcı olabilir. Text classification, belirli kategorilere ayrılmış verileri kullanarak, makine öğrenimi tekniklerini kullanarak bu verileri otomatik olarak sınıflandırır. Bu sayede, şirketlerin müşteri memnuniyeti hizmetlerini geliştirmeleri ve zamanında müdahale edebilmeleri için verileri daha hızlı ve etkili bir şekilde analiz etmelerine yardımcı olabilir.
  </p>
</br>
</br>
 
# :hash: Çalışma Mantığı Nedir?
<p align="justify">
Bu kod, bir metin sınıflandırma modeli oluşturmak için kullanılır. Öncelikle, veri seti Pandas kütüphanesi kullanılarak yüklenir ve eğitim ve test verileri oluşturmak için train_test_split fonksiyonu kullanılır. Daha sonra, verilerin tokenize edilmesi ve yinelemeler arasında düşük bir oranda rastgele bırakarak overfitting'i önlemek için SpatialDropout1D kullanılarak bir LSTM modeli oluşturulur. Bu model, belirtilen sayıda epoch boyunca eğitilir ve ardından test verileriyle değerlendirilir. Son olarak, bir tahmin fonksiyonu oluşturulur ve belirli bir metin verildiğinde, bu fonksiyon, tahmin edilen sınıfı belirleyerek metnin hangi kategoriye ait olduğunu belirler. Bu örnekte, sınıflandırma kategorileri şunlardır: 'Report a BUG', 'Suggest a new future', 'Suggest Improvement' ve 'Technical Support'.
  </p>

# :hash: Veri Çoğaltma İşlemi
<p align="justify">
Bu Python kodu, bir CSV dosyasındaki verileri işleyerek metin verilerinin içeriğindeki Türkçe stopwords'leri çıkarır ve ardından bu verileri belirli bir sayıda kopyalar ve karıştırır. Bu işlemler, veri kümesini artırmak ve text classification modellerinin daha iyi eğitilmesine yardımcı olmak için yapılır.

Kod önce, Türkçe stopwords listesini indirir ve daha sonra verileri işlemek için bir CSV dosyasını açar. Verilerin her satırındaki metinleri küçük harflere dönüştürür ve stopwords'leri çıkarır. Ardından, her satırı belirli bir sayıda kopyalar ve bu kopyaları orijinal verilerle birlikte bir listeye ekler. Listeye eklenen kopyalar rastgele karıştırılır ve son olarak tüm veriler tekrar bir CSV dosyasına yazdırılır.
  </p>
  

# :hash: Veri Temizleme İşlemi
<p align="justify">
Veri temizleme işlemi, veritemizleme.ipynb dosyasında açıklamalar ile belirtilmiştir. Veri temizleme işlemi aşağıdaki adımlar ile yapılmıştır: </br></br>
1- Exceldeki kullanılacak Title, Description, Values Değerleri ayrı excele çekildi.</br>
2- Exceldeki bütün textler küçük metinlere dönüştürüldü. (Büyük metin olunca küçük büyük harf duyarlılığı oluyordu)</br>
3- Exceldeki values sütunundaki kategorideki yazıları rakama çeviriyor. (report a bug=0 , suggest a new future=1 , suggest improvement=2 , technical support=3)</br>
4- Exceldeki values sütunundaki kategorilerin (0-1-2-3) değerlerinin kaç adet barındırdığı gösterildi. (0=330 , 1=54 , 2=353 , 3=33)</br>
5- Exceldeki tekrar eden satırlar silindi. (19 adet tekrar eden satır bulunmaktaydı)</br>
6- Exceldeki sütunlarda boş satır kontrolü yapıldı.</br>
7- Excelde sütunlardaki rakam ve karakterlerin yeri boşlukla değiştirildi. (Virgüller boşlukla değiştirilmeyip kaldırılınca 2 kelime tek kelimeye dönüşüyordu.)</br>
8- Excelde Title ve Descriptiondaki Türkçe STOPWORDSLER kaldırıldı.</br>
9- Title da en çok geçen top 10 kelime [('hk', 510), ('yetki', 53), ('hatası', 52), ('ve', 52), ('kullanıcı', 51), ('giderleri', 51), ('eklenmesi', 50), ('bütçe', 48), ('hak', 47), ('yeni', 46)]</br>
10- Description da en çok geçen top 10 kelime [('ve', 400), ('merhaba', 328),  ('için', 220), ('bütçe', 203), ('ederiz', 200), ('cognos', 179), ('çalışmalar', 170), ('olarak', 166)]</br>
11- Description da gereksiz kelimeler kaldırıldı.
12- Title da gereksiz kelimeler kaldırıldı.
13- Excel dosyası CSV dosyasına çevirildi.
14- CSV dosyasındaki gereksiz boşluklar kaldırıldı.
  </p>
