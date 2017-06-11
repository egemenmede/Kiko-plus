---
layout: post
title: "React Native ile Stil Kullanımı"
description: "İlk React yazımız Facebook ve React'tan sonra React Native yazılarımıza devam ediyoruz. Bu yazımızda uygulamanın stil işlemlerinin nasıl tanımlandığını ve kullanıldığını inceleyeceğiz."
date: 2017-01-08
tags: [react, react native]
comments: true
share: true
---
İlk React yazımız “Facebook ve React” tan sonra React Native yazılarımıza devam ediyoruz. Bu yazımızda uygulamanın stil işlemlerinin nasıl tanımlandığını ve kullanıldığını inceleyeceğiz.

React Native stil işlemleri için "**css-layout**" ([https://github.com/facebook/css-layout](https://github.com/facebook/css-layout)) olarak isimlendirilen açık kaynak bir projeyi kullanıyor. Bu sistem, hem Android hem de iOS tarafından destekleniyor. Stilleri uygulamanın aynen web’te olduğu gibi farklı yolları bulunuyor.

Kullanacağımız metotların ajandasını da şu şekilde oluşturalım.

**Ajandamız: Stillerin tanımlanması**

1. Inline stil uygulama
2. Nesnelerle stil uygulama
3. Stylesheet.Create kullanmak
4. İki veya daha fazla stili bir arada kullanmak
5. Harici stil dosyası kullanmak

**Stillerin tanımlanması**

React Native'de stil işlemleri JavaScript kullanılarak yapılıyor ve tanımlanan stiller tırnak işaretleri arasına yazılıyor. Ancak bir rakam kullanıldıysa tırnak kullanılmadan yazılıyor ve React otomatik olarak bu değerleri 'px' piksel değeri olarak kabul ediyor. Aynı zamanda stil özelliklerinin tanımlamasında camelCase yöntemi kullanılıyor. Örneğin; CSS'te background rengi tanımlanırken "background-color" şeklinde tanımlanırken React içerisinde "backgroundColor" şeklinde tanımlanıyor.

**1. Inline stil uygulama**

Inline stiller stil tanımlamanın en basit yolu. Ama tabi ki en iyi yolu değil. Ancak React içerisinde de kullanımına izin veriliyor.

```javascript
var flexwork1 = React.createClass({
  render: function() {
    return (
      <Text style={{marginTop: 40}}>
      Buradaki yazı <Text style={{fontStyle: "italic"}}>italik</Text> olacak.
      Buradaki ise <Text style={{fontWeight: "bold"}}>bold</Text> olacak.
      </Text>
    );
  }
});
```

![Inline stil uygulama](/egemenmede.github.io/assets/images/Inline-stiller.png){: .center-image}

**2. Nesnelerle stil uygulama**
 
Web’te kullanılan class benzeri bir kullanıma sahiptir. React Native’te de kullanacağınız stilleri nesne haline getirerek kullanabilirsiniz.
 
```javascript
var bold = { 
    fontWeight: 'bold',
};
 
var italic = { 
    fontStyle: 'italic',
};
 
var marginTop = { 
    marginTop: 40,
};
 
var flexwork1 = React.createClass({
  render: function() {
    return (
      <Text style={marginTop}>
      Buradaki yazı <Text style={italic}>italik</Text> olacak.
      Buradaki ise <Text style={bold}>bold</Text> olacak.
      </Text>
    );
  }
});
```

![Nesnelerle stil uygulama](/egemenmede.github.io/assets/images/nesnelerle-stil.png){: .center-image}

**3. Stylesheet.Create kullanmak**
 
Nesnelerle stil uygulamanın bir başka şekli de "Stylesheet.Create" kullanmak. Ondan farklı olarak tüm tanımlamalar ana bir nesne üzerinden çağırılır. Bunun yanında önemli bir avantajı da vardır. Dosyanın sonuna koyularak uygulama içerisinde bir kez oluşturulur ve çalıştırılır, her seferinde render edilmez.

```javascript
var styles = StyleSheet.create({
    marginTop: {
        marginTop: 40,
    },
    bold: {
        fontWeight: 'bold',
    },
    italic: {
        fontStyle: 'italic',
    },
});
    
var flexwork1 = React.createClass({
  render: function() {
    return (
      <Text style={styles.marginTop}>
      Buradaki yazı <Text style={styles.italic}>italik</Text> olacak.
      Buradaki ise <Text style={styles.bold}>bold</Text> olacak.
      </Text>
    );
  }
});
```

![Stylesheet.Create kullanmak](/egemenmede.github.io/assets/images/stylesheet-create.png){: .center-image}

**4. İki veya daha fazla stili bir arada kullanmak**
 
Stil tanımlamalarını bir dizi haline getirip, birden fazla stil objesini kullanabilirsiniz.

```javascript
var styles = StyleSheet.create({
    marginTop: {
        marginTop: 40,
    },
    bold: {
        fontWeight: 'bold',
    },
    italic: {
        fontStyle: 'italic',
    },
});
    
var flexwork1 = React.createClass({
  render: function() {
    return (
      <Text style={styles.marginTop}>
      Buradaki yazı <Text style={[styles.bold, styles.italic]}>hem italik hem bold</Text> olacak.
      </Text>
    );
  }
});
```

![İki veya daha fazla stili bir arada kullanmak](/egemenmede.github.io/assets/images/birden-fazla-stil.png){: .center-image}

Ve bu dizi şeklinde stil tanımlamasının içerisinde inline satırlar da kullanabilirsiniz.

```javascript
var styles = StyleSheet.create({
    marginTop: {
        marginTop: 40,
    },
    bold: {
        fontWeight: 'bold',
    },
    italic: {
        fontStyle: 'italic',
    },
});
    
var flexwork1 = React.createClass({
  render: function() {
    return (
      <Text style={styles.marginTop}>
      Buradaki yazı <Text style={[styles.bold, styles.italic, {color: '#FF0000'}]}>hem italik hem bold hem de kırmızı</Text> olacak.
      </Text>
    );
  }
});
```

![İki veya daha fazla stili bir arada kullanmak](/egemenmede.github.io/assets/images/birden-fazla-stil-2.png){: .center-image}

**5. Harici stil dosyası kullanmak**
 
Kullanacağınız stil özelliklerini harici bir stil dosyası üzerinden kullanabilirsiniz. Bunun için gerekli stillerinizi oluşturup, istediğiniz isimle sonu “.js” olacak şekilde kaydedin. Daha sonra kullanacağımız “index” dosyasına ekleyin ve kullanılacak bileşenlerin içerisine “StyleSheet” tanımlamasını ekleyin.
 
**ex-styles.js**

```javascript
'use strict';
var React = require('react-native'); 
var {
      StyleSheet,
    } = React;
var styles = StyleSheet.create({
    marginTop: {
        marginTop: 40,
    },
    bold: {
        fontWeight: 'bold',
    },
    italic: {
        fontStyle: 'italic',
    },
});
module.exports = styles;
```
 
**index.ios.js**
 
```javascript
'use strict';
 
var React = require('react-native');
var styles = require('./ex-styles.js');
var {
  AppRegistry,
  StyleSheet,
  Text,
  View,
} = React;
    
var flexwork1 = React.createClass({
  render: function() {
    return (
      <Text style={styles.marginTop}>
      Buradaki yazı HARİCİ CSS <Text style={[styles.bold, styles.italic, {color: '#FF0000'}]}>hem italik hem bold hem de kırmızı</Text> olacak.
      </Text>
    );
  }
});
```

![Harici stil dosyası kullanmak](/egemenmede.github.io/assets/images/harici-stil.png){: .center-image}