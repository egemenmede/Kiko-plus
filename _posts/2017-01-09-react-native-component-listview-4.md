---
layout: post
title: "React Native Component - ListView-4"
description: "React Native ListView kullanımı."
date: 2017-01-09
tags: [react, react native]
comments: true
share: true
---
**ListView-2** yazımızda başladığımız örneğimizi **ListView-3** ile “**Loading**” eklemiştik. Bu örneğimizde ise bir ek özellik daha ekleyeceğiz.

**ListView** içerisinde listelediğimiz kayıtları **Seperator** adını verdiğimiz ayraçlar ile nasıl ayırabileceğimizi öğreneceğiz. Bunun için öğreneceğimiz ListView özelliği **renderSeparator** olacak. renderSeparator, kullanıldığında her satırın altında ayırıcı (separator) oluşturulur.

Bunun için ise kodumuzu şu şekilde revize edilmesi gerekiyor.

![Ekran](/egemenmede.github.io/assets/images/ListView_4.png){: .center-image}

Bunun sonucunda uygulamamızın ekran görüntüsü aşağıdaki gibi oluşacaktır.

![Ekran](/egemenmede.github.io/assets/images/ListView_4_mobile.png){: .center-image}

ListView renderSeparator kullanımı ile ilgili teknik detaylara kaynak kod içerisinden göz atabilirsiniz.

[renderSeparator](https://github.com/facebook/react-native/blob/master/Libraries/CustomComponents/ListView/ListView.js#L143)