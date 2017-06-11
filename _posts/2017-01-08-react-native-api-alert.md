---
layout: post
title: "React Native Api - Alert"
description: "React Native Alert kullanımı."
date: 2017-01-08
tags: [react, react native]
comments: true
share: true
---
React Native Alert kullanımı.
 
Belirtilen başlık ve mesajla bir uyarı diyaloğu başlatır. Varsayılan olarak, tek düğme bir 'Tamam' düğmesi olacaktır. Bu, hem iOS hem de Android'de çalışan ve statik uyarıları gösterebilen bir component'tir.

## Alert Temel Yapısı ve Destekleri

```javascript
// Android ve iOS için
Alert.alert(
 	'Alert Title',
 	'My Alert Msg',
 	[
 		{text: 'Ask me later', onPress: () => console.log('Ask me later pressed')},
 		{text: 'Cancel', onPress: () => console.log('Cancel Pressed'), style: 'cancel'},
 		{text: 'OK', onPress: () => console.log('OK Pressed')},
 	],
	{ cancelable: false }
)
```

**iOS için;**

İstediğiniz sayıda buton belirtebilirsiniz. Her buton isteğe bağlı olarak "**default**", "**cancel**" ve "**destructive**" olarak belirtilebilir.

**Android için;**

Android için ise 3 buton belirtilebilir. Bunlar "**neutral**", "**negative**", "**positive**" dir.

- Eğer bir buton belirtmezseniz "positive" bir buton oluşur. ("OK" gibi.)
- İki buton, "negatif", "pozitif" anlamına gelir. ("İptal", "Tamam" gibi.)
- Üç buton, "neutral", "negatif", "pozitif" anlamına gelir. ("Daha Sonra", "İptal", "Tamam" gibi.)

Varsayınlan olarak Android'teki alert mesajları uyarı kutusunun dışına tıklatılarak kapatılabilir. Bu davranışın engellenmesi isteniyorsa, bu durumda isteğe bağlı olarak "**options**" parametresinde "**{cancelable: false}**" tanımlaması yapılır.

En basit haliyle şu şekilde kullanılabilir.

```javascript
Alert.alert("Button'a tıklandı!");
```

"**Alert**" e ait detaylı bilgiye buradan ulaşabilirsiniz.

[https://github.com/facebook/react-native/blob/master/Libraries/Alert/Alert.js](https://github.com/facebook/react-native/blob/master/Libraries/Alert/Alert.js)

![Alert-1](/egemenmede.github.io/assets/images/alert1.png){: .center-image}
![Alert-2](/egemenmede.github.io/assets/images/alert2.png){: .center-image}