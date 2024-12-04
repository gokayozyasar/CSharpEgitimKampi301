C# EĞİTİM KAMPI

Bu repo, Murat Yücedağ'ın eğitmenliğinde gerçekleştirilen C# Eğitim Kampı'nın 3. Case çalışması kapsamında oluşturulmuştur. Bu süreçte, Entity Framework yöntemlerini kullanarak Entity Layer, Data Access Layer, Business Layer ve Presentation Layer katmanlarını oluşturulmuştur.

Projenin devamında, bir Seyahat Acentesi uygulaması geliştirilmiştir. Bu uygulama için SQL veritabanında oluşturulan bir veri tabanı kullanılarak, LINQ sorguları aracılığıyla 12 farklı sorgu gerçekleştirilmiştir. Bu sayede, LINQ sorgularının kullanımı ve işleyişi pekiştirilmiştir.

Bu repo, hem katmanlı mimari tasarımı hem de LINQ sorgularının pratikteki uygulamasını anlamak ve geliştirmek isteyenler için çalışmaları içermektedir.

Form Eran Görüntüsü ;
![case3screen](https://github.com/user-attachments/assets/3f2ec6e4-fc92-4ea7-8295-88625bc54672)


NOT: Ortalama kapasite hesaplamasında, Murat Yücedağ'ın oluşturduğu C# Eğitim Kampı'nın 17. dersi olan Entity Framework Metotları ve LINQ Sorguları videosunda ödev olarak verilen Ortalama Kapasite sorgusunda, virgülden sonraki ondalık değerlerin iki basamağa indirgenmesi ve binlik ayıracı kullanımıyla ilgili bir çözüm sunulmuştur.

Başlangıçta, aşağıdaki kod düşünülmüş ancak SQL tarafında Price alanının decimal olarak tanımlanması ve decimal türünün null değer içerebilmesi nedeniyle bu kodda hata oluştuğu tespit edilmiştir:

** lblAvgLocationPrice.Text = db.Location.Average(x => x.Price).Value.ToString("F2") + " TL";

Bu durumu çözmek için kod şu şekilde güncellenmiştir:

** lblAvgLocationPrice.Text = db.Location.Average(x => x.Price).GetValueOrDefault().ToString("F2") + " TL";

Ayrıca, binlik ayıracın daha estetik bir görünüm sağlaması isteniyorsa, .ToString("F2") ifadesi .ToString("N2") olarak değiştirilmelidir. Bu güncelleme, çıktının hem iki ondalık basamaklı hem de binlik ayıracı içerecek şekilde formatlanmasını sağlayacaktır.

Bu şekilde yapılan düzenleme, hem daha okunabilir bir sonuç elde edilmesini hem de olası hataların önüne geçilmesini sağlamaktadır.
