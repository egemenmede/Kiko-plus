---
layout: post
title: "React Native Component - Button"
description: "React Native Button kullanımı."
date: 2017-01-08
tags: [react, react native]
comments: true
share: true
---
React Native Button kullanımı.
 
## Button Temel Yapısı ve Destekleri

```javascript
<Button
 	onPress={onPressLearnMore}
 	title="Learn More"
 	color="#841584"
 	accessibilityLabel="Learn more about this purple button" />
```
 
## Destekler

**accessibilityLabel (string):**
Erişilebilirlik özellikleri için görüntülenecek metindir. Zorunludur.
 
**color (color) (Renkler):** 
[https://facebook.github.io/react-native/docs/colors.html](https://facebook.github.io/react-native/docs/colors.html)
iOS için metnin rengi veya Android için butonun arka plan rengidir. Opsiyoneldir.
 
**disabled (bool):**
Eğer true ise, bu bileşen için tüm etkileşimleri devre dışı bırakır. Opsiyoneldir.
 
**onPress (function):**
Kullanıcı butona bastığında çağrılacak işleyici fonksiyonu belirtir. Zorunludur.
 
**title (string):**
Buton içinde görüntülenecek metindir. Zorunludur.
 
"**Button**" a ait detaylı bilgiye buradan ulaşabilirsiniz.
 
[https://github.com/facebook/react-native/blob/master/Libraries/Components/Button.js](https://github.com/facebook/react-native/blob/master/Libraries/Components/Button.js)
 
Zorunlu olarak belirtilmiş özellikleri belirtmediğinizde de uygulamanız çalışır.
 
**Örnek:**

![Ekran-1](/egemenmede.github.io/assets/images/buton1.png){: .center-image}

Ancak bunu yaptığınız da aşağıdaki gibi bir uyarı görüntülenir.

![Ekran-2](/egemenmede.github.io/assets/images/buton2.png){: .center-image}

Uyarıya tıkladığınızda detaylı açıklamayı aşağıdaki gibi görüntüleyebilirsiniz.

![Ekran-3](/egemenmede.github.io/assets/images/ss1.png){: .center-image}

Bunun için aşağıdaki gibi onPress fonksiyonunu eklemelisiniz.

![Ekran-4](/egemenmede.github.io/assets/images/ss2.png){: .center-image}

Bu durumda uyarı ortadan kalkacaktır.

![Ekran-5](/egemenmede.github.io/assets/images/ss3.png){: .center-image}