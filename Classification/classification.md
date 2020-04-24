*Denetimli Öğrenme Nedir?* | *Alt tipleri var mıdır?*| *Hangi matematiksel modeller ile yapılır?* | *Algoritmalarını nasıl kullanırım*


Verinizin feature ları ile hangi sonucu vermesi gerektiğini biliyorsanız yani hangi sınıfa atanacağını veya hangi değerleri alacağını biliyorsanız bu tarzda eğitilmiş veriler ile bir model oluşturuyorsanız bu eğitime denetimli öğrenme denilmektedir.

Örneğin verinizde 3 feature var bunlarda ayak sayısı, gaga, bıyık olsun ve her bir örneklem için bu değerler ve bu değerlerin sonucu olan hayvanın ne olduğunu biliyorsanız bu veri etiketli veridir ve model kurulurken hangi instance değerlerinin sınıfının ne olduğu bilinir.

Basit Örnek Gösterimi ->

Ayak Sayısı | Gaga | Bıyık | Hayvan
------------|------|-------|-------
4 | 0 | 1 | Kedi
4 | 0 | 0 | At
2 | 1 | 0 | Kuş
4 | 0 | 1 |Kedi

şeklinde bir veri setiniz olsun bu veri ile bir model oluşturup birazdan soracağım sorunun cevabını arayacaksınız işte bu veri seti eğitim veriseti (train data) olarak kullanıldığında denetimli öğrenme yapılmış olacaktır. 
Yine etiketli yani hangi hayvan olduğunu bildiğimiz bir veri seti ile de 

Ayak Sayısı | Gaga | Bıyık| Hayvan
4|0|1|Kedi
2|1|0|Kuş

öğrenmemizi test edebiliriz. Burda model Kedi ve Kuş u bilmeden 4 ayaklı 0 gaga ve 1 bıyık sahibi hayvanı tahminler sonuç test tablosundaki Hayvan ile kontrol edilir bu accuracy ve hata oranlarımızı tespit etmek için yapılmaktadır.

daha sonra modele 2 ayaklı 1 gagalı 0 bıyıklı verisini verdiğimizde model artık bizim için tahminlemeye başlamakta fakat 3 ayaklı 1 gaga ve 1 bıyıklı dersek ne olacak ? Cevabı kullanılan yönteme göre değişir bu yöntemlerin neler olduğuna bakacağız. 
Not: Yukarda bahsi geçen örnek denetimli sınıflandırma içindir.

![](images/supervisedlearning.png)


**Sınıflandırma Yöntemi (Classification Method)**

Sınıflandırma problemi için geliştirilen algoritmalar, adından da anlaşılacağı üzere verileri belli özelliklerine göre sınıflandırırlar.
Sınıflandırma yapısal (structure) veya yapısal olmayan (unstructure) veriler üzerinde yapılabilir.

Eğer sistem, hangi verinin, hangi koşullarda, hangi sınıfa ait olacağı bilgisi ile sınıflandırılarak eğitilirse, yeni veri setindeki veriyi de öğrendiklerine benzer biçimde sınıflandırabilir.

Sınıflandırma Yöntemleri de aşağıdaki gibi kategorilere ayrılır;

–Binary Classification (İkili Sınıflandırma): İki olası sonuç ile sınıflandırma. Örn: Cinsiyet sınıflandırması (Erkek / Kadın)

–Multi Class Classification (Çoklu Sınıf Sınıflandırma): İkiden fazla sınıfı sınıflandırma. Bir sınıfa ait birden fazla farklı veri varsa bu farklı veriler tespit edilir ve her biri tek bir etikete atanır. Örn: Bir hayvan sınıfında kedi ya da köpek olabilir ancak ikisi birlikte bir sınıfta olamaz kendi içinde sınıflara bölünmelidir.

–Multi Label Classification (Çoklu Etiket Sınıflandırma): Bir veri birden fazla sınıfla ilişkilendirilebilir. Örn: Bir makale hem sağlık hem spor hem de insan ile ilgili olabilir.

Sınıflandırma Yönteminde en çok kullanılan algoritmalar:

**Naive Bayes :** Verileri olasılık ilkeleri ile hasaplayarak sınıflandıran bir sınıflandırma algoritmasıdır. Basit bir ifadeyle, bir Naive Bayes sınıflandırıcı, bir sınıftaki belirli bir özelliğin varlığının başka herhangi bir özelliğin varlığına bağlı olmadığını varsayar. Örneğin, bir meyve kırmızı, yuvarlak ve çapı yaklaşık 3 inç ise bir elma olarak düşünülebilir. Bu özellikler birbirlerine veya diğer özelliklerin varlığına bağlı olsa bile, bu özelliklerin tümü, bu meyvenin bir elma olması olasılığına bağımsız olarak katkıda bulunur ve bu yüzden “Naif” olarak bilinir.
Eğitilmiş veriler üzerinde olasılık işlemleri yapılır ve sisteme sunular yeni verinin önceki olasılık değerine göre sınıflandırılması sağlanır. Başka bir örnek ile ifade edilecek olursa: binlerce makalenin hangi alanda yazıldıklarına göre kategorize etmek istiyorsunuz. (tıp, teknoloji, edebiyat) Bunun için belli makalelerde geçen belli kelimelerin olasılık değerlerinin, diğerlerine oranla fazla olması durumuna göre o makalenin hangi kategoriye ait olduğunu öğrenmek isterseniz(Sağlık kelimesinin çok geçtiği makale tıp ile ilgili bir makaledir gibi) bu algoritma işinize yarayabilir.

**K-Nearest Neighbours (En Yakın Komşu):** Bu tip sınıflandırma, her bir noktanın en yakın komşularının basit çoğunluk oyu ile hesaplanması ile elde edilen sınıflandırmadır. Veri hangi veriye en çok yakındır? mantığı ile dallanır.  
Bu algoritmanın uygulanması kolaydır, gürültülü eğitim verisine (noisy training data) dayanıklıdır ve eğitim verileri büyükse oldukça etkilidir.

**Decision Tree (Karar Ağacı):** Veriler, sınıfları ile birlikte bu algoritmaya verildiğinde, algoritma verileri sınıflandırmak için kullanılabilecek bir dizi kural üretir. Karar düğümleri(decision node) ve yaprak düğümleri(leaf node) olan bir ağaç yapısına sahiptir. Hem sınıflandırma hem de regresyon yönteminde kullanılabilir.

**Random Forest:**  Sınıflandırma işlemi sırasında birden fazla decision-tree kullanılarak sınıflandırma değerinin yükseltilmesi hedefleyen, sınıflama veya regresyon yönteminde kullanılabilen algoritmadır.

**Support Vector Machine (Destekçi Vektör Makinesi):** Veri setinde birbirine benzeyen gruplar arasına birbirinden en uzak olan noktalardan sınırlar çizmeye yarayan algoritmadır.