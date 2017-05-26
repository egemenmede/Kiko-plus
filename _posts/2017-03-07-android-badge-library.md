---
layout: post
title: "Android Badge Plugini; EtiyaBadgeTab"
description: "EtiyaBadgeTab, Android için hazırlanmış bir Tab kütüphanesidir. Android'te kullanılan Tab kütüphanesine alternatif olarak badge desteği ve çeşitli özelleştirmeler sunmaktadır."
date: 2017-03-07
tags: [badge, plugin, android, library]
comments: true
share: true
---

EtiyaBadgeTab, Android için hazırlanmış bir Tab kütüphanesidir. Android'te kullanılan Tab kütüphanesine alternatif olarak **badge** desteği ve çeşitli özelleştirmeler sunmaktadır.

> **badge**: Kelime anlamı rozet olan badge'ı, tab üzerindeki küçük simgeler olarak tanımlayabiliriz.

### Örnek Ekran Görüntüsü

![EtiyaBadgeTab](/egemenmede.github.io/assets/images/etiyabadgetab.png){: .center-image}

### Kurulum

**Gradle**
```
compile 'com.etiya.etiyabadgetablib:etiyabadgetablib:0.0.3'
```

### Kullanım Şekli

```java
etiyaBadgeTab.selectEtiyaBadgeTab(0)
                .tabTitle("TAB 1")
                .tabTitleColor(R.color.tabTitleColor)
                .tabIcon(tabIcons[0])
                .tabIconToTitle(1)
                .tabIconColor(R.color.tabTitleColor)
                .tabIconDirection("LEFT")
                .tabBadge(true)
                .tabBadgeCount(18)
                .tabBadgeCountMore(true)
                .tabBadgeBgColor(R.color.orange)
                .tabBadgeTextColor(R.color.smoothwhite)
                .tabBadgeStroke(2, R.color.greyblue)
                .tabBadgeCornerRadius(18)
                .createEtiyaBadgeTab();
```

### Özellikler

> İkisi zorunlu olmak üzere 15 özelliğe sahiptir.

* **selectEtiyaBadgeTab:** İşlem yapılacak tab'ın seçilmesini sağlar. Integer bir değer alır ve ilk tab 0'dan başlar. **Kullanımı zorunludur.**

* **tabTitle:** Tab'ın metnini ayarlar. String bir değer alır. Kullanımı isteğe bağlıdır.

* **tabTitleColor:** Tab metni kullanıldığı durumlarda, Tab'ın metninin rengini ayarlar. Integer bir değer alır. Kullanımı isteğe bağlıdır.

* **tabIcon:** Tab ile kullanılacak ikonu gösterir. Integer ve Drawable olmak üzere iki kullanım türünü destekler. Kullanımı isteğe bağlıdır.

* **tabIconToTitle:** Tab ikonu kullanıldığı durumlarda, Tab ile ikon arasındaki boşluğun ne kadar olacağını belirler. Integer bir değer alır. Varsayılan değeri 1'dir. Kullanımı isteğe bağlıdır.

* **tabIconColor:** Tab ikonu kullanıldığı durumlarda, ikon rengini belirler. Integer bir değer alır. Kullanımı isteğe bağlıdır.

* **tabIconDirection:** Tab ikonu kullanıldığı durumlarda, ikonun konumunu belirler. Eğer belirtilmezse, varsayılan değeri "LEFT" tir. "LEFT" ve "RIGHT" olmak üzere 2 farklı String değer alır. Kullanımı isteğe bağlıdır.

* **tabBadge:** Tab içerisinde Badge gösterilmesi sağlar. true ve false olmak üzere iki değer alır. Varsayılan değeri false'tur. Kullanımı isteğe bağlıdır.

* **tabBadgeCount:** Badge kullanıldığı durumlarda, badge içerisindeki rakamı görüntülemek için kullanılır. Integer bir değer alır. Kullanımı isteğe bağlıdır.

* **tabBadgeCountMore:** Badge kullanıldığı durumlarda, badge içerisindeki gösterilecek rakamın görüntülenme şeklini belirler. true ve false olmak üzere iki değer alır. Varsayılan değeri false'tur. true ise 9'dan sonrası "9+", false durumunda sayının tamamı gösterilir. Kullanımı isteğe bağlıdır.

* **tabBadgeBgColor:** Badge kullanıldığı durumlarda, badge'in arkaplan rengini belirler. Integer bir değer alır. Kullanımı isteğe bağlıdır.

* **tabBadgeTextColor:** Badge kullanıldığı durumlarda, badge'in metin rengini belirler. Integer bir değer alır. Kullanımı isteğe bağlıdır.

* **tabBadgeStroke:** Badge kullanıldığı durumlarda, badge'in çerçeve kalınlığını ve rengini belirler. Integer olarak iki parametre alır. İlk parametre çerçeve kalınlığını, ikinci parametre çerçeve rengini belirler. Kullanımı isteğe bağlıdır.

* **tabBadgeCornerRadius:** Badge kullanıldığı durumlarda, badge'in köşelerindeki ovallik miktarını belirler. Integer bir değer alır. Kullanımı isteğe bağlıdır.

* **createEtiyaBadgeTab:** selectEtiyaBadgeTab ile seçilen tab'ın, belirtilen parametrelerle oluşturulmasını sağlar. **Kullanımı zorunludur.**

### En Kısa Kullanım Şekli

```java
etiyaBadgeTab.selectEtiyaBadgeTab(0)
                .createEtiyaBadgeTab();
```