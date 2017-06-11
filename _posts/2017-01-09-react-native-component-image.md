---
layout: post
title: "React Native Component - Image"
description: "React Native Image kullanımı."
date: 2017-01-09
tags: [react, react native]
comments: true
share: true
---
Image ile hem lokal saklama alanındaki hem de uzak sunucudaki resimlerin gösterilmesi için kullanılır.
 
Lokaldeki gösterimi şu şekildedir.

```javascript
<Image
style={styles.base}
source={require('./img/logo_og.png')}
/>
```
 
Uzak sunucu üzerinden kullanılan resimler de şu şekilde gösterilir.

```javascript
<Image
	style={styles.base}
	source={{uri: 'http://facebook.github.io/react/img/logo_og.png'}}
/>
```
 
**Image** componenti için önemli bazı özellikler şunlardır;
 
**source:** Lokal ve uzak sunucu üzerinden alınacak resmin adresini belirtir.
 
**resizeMode:** Çerçeve resim boyutlarıyla eşleşmediğinde görüntünün nasıl yeniden boyutlandırılacağını belirler. Değer olarak cover, contain, stretch ve repeat (yalnızca iOS) değerlerini alır.
 
Diğer özellikler için örneğimiz ile devam edelim.

![Ekran](/egemenmede.github.io/assets/images/image_1.png){: .center-image}
![Ekran](/egemenmede.github.io/assets/images/image_2.png){: .center-image}
![Ekran](/egemenmede.github.io/assets/images/image_3.png){: .center-image}

Detaylı bilgi için;
[http://facebook.github.io/react-native/releases/0.40/docs/image.html](http://facebook.github.io/react-native/releases/0.40/docs/image.html)
[https://github.com/facebook/react-native/blob/master/Libraries/Image/Image.android.js](https://github.com/facebook/react-native/blob/master/Libraries/Image/Image.android.js)

## Mobil Ekran Görüntüleri

![Ekran](/egemenmede.github.io/assets/images/image_1_mobile.png){: .center-image}
![Ekran](/egemenmede.github.io/assets/images/image_2_mobile.png){: .center-image}
![Ekran](/egemenmede.github.io/assets/images/image_3_mobile.png){: .center-image}