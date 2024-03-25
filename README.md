# Travel Between Floors System Class Diagram

### Soru : Aşağıdaki problem ifadesine göre bir sınıf diyagramı tasarlayın.

Nesne Yönelimli Programlamanın ilkelerini ve sınıflar arası ilişki durumlarını kullanmaya çalışın. (Encapsulation, Inheritance, Polymorphism, Abstraction)

Kodluyoruz Sigorta Şirketi 12 katlı bir ofis binası inşa etmek ve onu en son asansör teknolojisi ile donatmak istiyor. Şirket, bina içindeki trafik akışı ihtiyaçlarını karşılayıp karşılamayacaklarını görmek için binanın asansörlerinin işlemlerini modelleyen bir yazılım simülatörü oluşturmanızı istiyor.

Binada, her biri binanın 12 katına çıkabilecek beş asansör bulunacaktır. Her asansörün yaklaşık altı yetişkin yolcu kapasitesi vardır. Asansörler enerji tasarruflu olacak şekilde tasarlanmıştır, bu nedenle yalnızca gerektiğinde hareket ederler. Her asansörün kendi kapısı, kat gösterge ışığı ve kontrol paneli vardır. Kontrol panelinde hedef düğmeleri, kapı açma ve kapama düğmeleri ve bir acil durum sinyal düğmesi bulunur.

Binadaki her katta, beş asansör boşluğunun her biri için bir kapı ve her kapı için bir varış zili vardır. Varış zili, asansörlerin bir kata vardığını gösterir. Her kapının üzerinde bulunan bir sinyal ışığı, asansörün gelişini ve asansörün hareket ettiği yönü gösterir. Her katta ayrıca üç set asansör çağrı düğmesi vardır.

Bir kişi uygun çağrı düğmesine (yukarı veya aşağı) basarak bir asansörü çağırır. Bir programlayıcı, aramanın başladığı kata gitmek için beş asansörden birini görevlendirir. Asansöre girdikten sonra, bir yolcu tipik olarak bir veya daha fazla hedef düğmesine basar. Asansör kattan kata hareket ederken, asansörün içindeki bir gösterge ışığı yolcuları asansörün konumu hakkında bilgilendirir. Bir asansörün bir kata varması, dış asansör kapısının üzerindeki gösterge lambasının yakılması ve kat zilinin çalmasıyla belirtilir. Bir asansör bir katta durduğunda, her iki kapı grubu da önceden belirlenmiş bir süre boyunca otomatik olarak açılarak yolcuların asansöre girip çıkmalarına izin verir.

Simülatör, gerçek zaman geçişini simüle etmek ve simülasyonda meydana gelen olayları zaman damgası ve günlüğe kaydetmek için bir "saat" kullanır. Simülatör tarafından yolcu oluşturmak ve her yolcu için kalkış ve varış katlarını belirlemek için rastgele bir sayı üreteci kullanılır.

Kodluyoruz Sigorta Şirketi Asansör Simülasyonu Sınıf Diyagramı

## Sınıflar :

* Asansör: Kapasite, kat numarası, durum (boş, dolu, hareket halinde), hedef katlar gibi özelliklere ve yukarı/aşağı gitme, kat değişimi, kapı açma/kapama gibi metotlara sahip bir sınıftır.
* Kat: Kat numarası, varış zili, asansör çağrı düğmeleri (yukarı/aşağı) gibi özelliklere sahip bir sınıftır.
* Yolcu: Kalkış katı, varış katı, asansör tercihi gibi özelliklere sahip bir sınıftır.
* Simülatör: Saat, rastgele sayı üreteci, asansörler, katlar ve yolcular gibi nesneleri içeren ve simülasyonu yürüten bir sınıftır.

## Sınıflar Arası İlişkiler : 

* Kalıtım: Asansör ve Kat sınıfları, temel fonksiyonelliği ve ortak özellikleri içeren bir BaseAsansör sınıfından miras alabilir.
* Birleşme: Asansör ve Kat sınıfları, asansör kapıları ve kat zili gibi ortak unsurları kapsayacak şekilde birleştirilebilir.
* Agregasyon: Simülatör sınıfı, Asansör, Kat ve Yolcu nesnelerini bir koleksiyon olarak içerir.
* Assosiasyon: Yolcu sınıfı, bir Asansör nesnesi ile ilişkilendirilebilir.
* Bağımlılık: Asansör ve Kat sınıfları, simülasyon zamanını ve rastgele sayı üretimini yönetmek için Simülatör sınıfına bağımlıdır.

## Diyagram :

```bash
+----------------+
| Simülatör      |
+----------------+
|   saat          |
|   rastgeleSayiUretici |
|   asansörler   |
|   katlar        |
|   yolcular      |
+----------------+

+----------------+
| Asansör        |
+----------------+
|   kapasite     |
|   katNumarası   |
|   durum        |
|   hedefKatlar   |
+----------------+
|   yukarıGit()   |
|   aşağıGit()   |
|   katDeğişimi() |
|   kapıAç()     |
|   kapıKapa()    |
+----------------+

+----------------+
| Kat             |
+----------------+
|   katNumarası   |
|   varışZili     |
|   çağrıDüğmeleri |
+----------------+

+----------------+
| Yolcu          |
+----------------+
|   kalkışKatı   |
|   varışKatı    |
|   asansörTercihi |
+----------------+
```

## Notlar :

* Bu diyagram, problem ifadesine dayalı bir öneridir ve özelleştirilebilir.
* Sınıflar ve ilişkiler, modelleme ve kodlama tercihlerine göre farklı şekilde tasarlanabilir.
* Diyagramda, bazı özellikler ve metoadlar gösterilmemiştir.

## Ekstra Özellikler:

* Asansör bekleme süresi
* Yolcu varış süresi
* Asansör enerji tüketimi
* Kat trafik yoğunluğu

## Ekstra Metoadlar:

* Asansör arıza simülasyonu
* Yoğun saatlerde asansör önceliklendirme
* Katlardaki yolcu sayısının takibi

## Uygulama Önerileri:

* Nesneye Dayalı Programlama (OOP) prensiplerini ve SOLID ilkelerini kullanın.
* Gerçekçi bir simülasyon için rastgelelik ve zaman gecikmelerini ekleyin.
* Kullanıcı dostu bir arayüz ve görselleştirme geliştirin.

Bu diyagram, Kodluyoruz Sigorta Şirketi asansör simülasyonu için sağlam bir temel oluşturacaktır.