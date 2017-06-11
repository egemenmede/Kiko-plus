---
layout: post
title: "React Native Component - ListView-3"
description: "React Native ListView kullanımı."
date: 2017-01-09
tags: [react, react native]
comments: true
share: true
---
**ListView-2** yazımızda gerçek bir veri kaynağından **JSON** verilerini çekerek ekranda göstermiştik.
 
Bu yazıda önceki örneğimizi biraz daha gerçekçi bir hale getirip, yükleme öncesinde bir “**Loading..**” mesajı gösterip, veri servisten çekildikten sonra ekrana bastıracağız.
 
Örneğimizde **React.createClass** kullanacağız ve önceki yazımızda öğrendiğimiz gibi bileşenin başlangıç hali için **getInitialState** yöntemini kullanacağız. Bu sebeple tanımladığımız “**isLoading**” değişkenine ilk değeri de bu durumda “**true**” olarak, yani “**Loading..**” mesajını göstererek başlatıyoruz.
 
Bu mesajı iptal edip, servisten çekeceğimiz veriyi göstereceğimiz durumda da “**isLoading**” değişkenine “**false**” değerini atamamız gerekiyor. Bu işlemi de servisten veri çekmenin sorunsuz olarak tamamlandığı “**loadJSONData**” fonksiyonu içerisinde tanımlıyoruz.

![Ekran](/egemenmede.github.io/assets/images/ListView_3.png){: .center-image}

Yapacağımız son işlem ise **render** fonksiyonu içerisinde olacak. Bunun içinde **state** içerisindeki isLoading durumunu kontrol ediyor ve eğer **isLoading true** durumundaysa “**Loading..**” mesajını göstermeye devam edip, **false** durumunda ise verilerimizi ekranda göstermiş olacağız.