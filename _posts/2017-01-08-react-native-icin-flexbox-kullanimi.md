---
layout: post
title: "React Native için Flexbox Kullanımı"
description: "Flexbox, CSS3 ile birlikte hayatımıza giren ve yerleşim düzeni bakımından pek çok kolaylığı da birlikte getiren bir yerleşim şekli. Bu sayede esnek boyutlarda sayfa planlamaları yapabilmek, hizalama ve pozisyonlama işlemlerini gerçekleştirmek çok daha kolay hale geliyor. React Native'de yerleşim planı olarak Flexbox kullanıyor. Bu yazı da React ile Flex'in nasıl kullanılacağını öğreneceğiz."
date: 2017-01-08
tags: [react, react native]
comments: true
share: true
---
Flexbox, CSS3 ile birlikte hayatımıza giren ve yerleşim düzeni bakımından pek çok kolaylığı da birlikte getiren bir yerleşim şekli. Bu sayede esnek boyutlarda sayfa planlamaları yapabilmek, hizalama ve pozisyonlama işlemlerini gerçekleştirmek çok daha kolay hale geliyor. React Native'de yerleşim planı olarak Flexbox kullanıyor. Bu yazı da React ile Flex'in nasıl kullanılacağını öğreneceğiz.
 
Flex'in CSS3 ile gelmiş olduğunu söylemiş olsakta React Flex'in CSS3 içerisindeki tüm özelliklerini kullanmaz. Kullanabileceğiniz özelliklere buradan ([https://facebook.github.io/react-native/docs/flexbox.html](https://facebook.github.io/react-native/docs/flexbox.html)) ulaşabilirsiniz. Daha detaylı incelemek isteyenler github üzerinden "LayoutPropTypes.js" ([https://github.com/facebook/react-native/blob/master/Libraries/StyleSheet/LayoutPropTypes.js](https://github.com/facebook/react-native/blob/master/Libraries/StyleSheet/LayoutPropTypes.js)) dosyasını inceleyebilirler. Biz yazı içerisinde temel parametrelerden öte, hizalamaya yönelik değerlerinin React ile nasıl kullanılacağını inceleyeceğiz. 
 
Haydi başlayalım!..
 
**Ajandamız**
 
1. flex
2. flexDirection
3. justifyContent
4. flexWrap
5. alignItems
6. alignSelf
 
## 1. flex:
 
Kapsayıcının tanımı "flex: sayı" şeklinde yapılır. Burada belirtilen “sayı”, esnekliğin orantısal olarak ne kadar olacağını belirler.
 
Aşağıdaki örneğimizde “half” ile belirtilen alan ekranın yarısı kapsıyorken, “quarter” ile belirtilen alanlar da geri kalanın yarısını iki parça halinde gönderilir. Buradaki değerler aynı zamanda (.5 ve .25 olarak ta belirleyebiliriz.)
 
```javascript
container: {
    flex: 1,
}
```
 
[Kaynak](https://facebook.github.io/react-native/docs/flexbox.html#flex)
 
```javascript
var flexwork1 = React.createClass({
  render: function() {
    return (
      <View style={styles.container}>
          <View style={styles.half} />
          <View style={styles.quarter} />
          <View style={[styles.quarter, {backgroundColor: '#333'}]} />
      </View>
        
    );
  }
});
 
var styles = StyleSheet.create({
    container: {
        flex: 1,
        flexDirection: 'column',
    },
    half: {
        flex: 2, // veya .5
        backgroundColor: '#FF44CC',
    },
    quarter: {
        flex: 1, // veya .25
        backgroundColor: '#CCC',
    },
});
```

![flex](/egemenmede.github.io/assets/images/flex.png){: .center-image}
 
## 2. flexDirection:
 
Kapsayıcı içerisinde bulunan elemanların yatay ve dikey olarak hizalanmalarını sağlayan özelliktir. "row" ve "column" olmak üzere iki değer alır ve belirtilmezse varsayılan olarak "column" olarak kullanılır.
 
[Kaynak](https://facebook.github.io/react-native/docs/flexbox.html#flexdirection)
 
```javascript
container: {
    flexDirection: 'row',
}
```
 
## 3. justifyContent:
 
Kapsayıcı içerisinde bulunan elemanların yatay eksen üzerinde (x ekseni) nasıl hizalanacağına dair değerleri alır. Bunlar;
 
**flex-start:** İçerisindeki elemanları kapsayıcının başından başlayarak sıralama yapar.
 
**flex-end:** İçerisindeki elemanları kapsayıcının sonundan başlayarak sıralama yapar.
 
**center:** İçerisindeki elemanları kapsayıcı içerisinde ortalayarak sıralama yapar.
 
**space-between:** İçerisindeki elemanları kapsayıcı içerisinde baştan ve sondan konumlandırarak sıralama yapar.
 
**space-around:** İçerisindeki elemanları kapsayıcı içerisinde sağ ve sol boşluklarını eşitleyerek sıralama yapar.
 
[Kaynak](https://facebook.github.io/react-native/docs/flexbox.html#justifycontent)
 
Görüntüleyeceğimiz kutuları aşağıdaki gibi düzenleyelim ve tüm justifyContent durumları için kontrol edelim.
 
```javascript
var flexwork1 = React.createClass({
  render: function() {
    return (
      <View style={styles.container}>
          <View style={styles.element}><Text>Egemen - 1</Text></View>
          <View style={styles.element}><Text>Egemen - 2</Text></View>
          <View style={styles.element}><Text>Egemen - 3</Text></View>
      </View>
    );
  }
});
 
var styles = StyleSheet.create({
    container: {
        flex: 1,
        flexDirection: 'row',
        justifyContent: 'flex-start',
        backgroundColor: '#F5FCFF',
        borderWidth: 1,
        marginTop: 44,
    },
    element: {
        margin: 5,
        borderWidth: 1,
        padding: 10,
        height: 50,
    },
});
```
![justifiyContent](/egemenmede.github.io/assets/images/justifyContent-center-column.png){: .center-image}
justifiyContent: center flexDirection: column

![justifiyContent](/egemenmede.github.io/assets/images/justifyContent-center-row.png){: .center-image}
justifiyContent: center flexDirection: row

![justifiyContent](/egemenmede.github.io/assets/images/justifyContent-flex-end-column.png){: .center-image}
justifiyContent: flex-end flexDirection: column

![justifiyContent](/egemenmede.github.io/assets/images/justifyContent-flex-end-row.png){: .center-image}
justifiyContent: flex-end flexDirection: row

![justifiyContent](/egemenmede.github.io/assets/images/justifyContent-flex-start-column.png){: .center-image}
justifiyContent: flex-start flexDirection: column

![justifiyContent](/egemenmede.github.io/assets/images/justifyContent-flex-start-row.png){: .center-image}
justifiyContent: flex-start flexDirection: row

![justifiyContent](/egemenmede.github.io/assets/images/justifyContent-space-around-column.png){: .center-image}
justifiyContent: space-around flexDirection: column

![justifiyContent](/egemenmede.github.io/assets/images/justifyContent-space-around-row.png){: .center-image}
justifiyContent: space-around flexDirection: row

![justifiyContent](/egemenmede.github.io/assets/images/justifyContent-space-between-column.png){: .center-image}
justifiyContent: space-between flexDirection: column

![justifiyContent](/egemenmede.github.io/assets/images/justifyContent-space-between-row.png){: .center-image}
justifiyContent: space-between flexDirection: row
 
## 4. flexWrap:
 
Kapsayıcı içerisindeki elemanların bulundukları satır içerisinde bir alt satıra geçip, geçmeyeceğini belirler. "wrap" ve "nowrap" olmak üzere iki değer alabilir. Varsayılan hali “nowrap” tır.
 
**nowrap:** Kapsayıcı genişliğinin aşıldığı durumda elemanlar aynı satırda devam ederler.
 
**wrap:** Kapsayıcı genişliğinin aşıldığı durumda elemanlar eleman ya da elemanlar bir alt satıra geçer.
 
[Kaynak](https://facebook.github.io/react-native/docs/flexbox.html#flexwrap)

```javascript
var flexwork1 = React.createClass({
  render: function() {
    return (
      <View style={styles.container}>
          <View style={styles.element}><Text>Egemen - 1</Text></View>
          <View style={styles.element}><Text>Egemen - 2</Text></View>
          <View style={styles.element}><Text>Egemen - 3</Text></View>
          <View style={styles.element}><Text>Egemen - 4</Text></View>
          <View style={styles.element}><Text>Egemen - 5</Text></View>
          <View style={styles.element}><Text>Egemen - 6</Text></View>
      </View>
    );
  }
});
 
var styles = StyleSheet.create({
    container: {
        flex: 1,
        flexDirection: 'row',
        flexWrap: 'nowrap',
        backgroundColor: '#F5FCFF',
        borderWidth: 1,
        marginTop: 44,
    },
    element: {
        margin: 5,
        borderWidth: 1,
        padding: 10,
        height: 50,
    },
});
```

![flexWrap](/egemenmede.github.io/assets/images/flexWrap-nowrap-row.png){: .center-image}
flexWrap: nowrap flexDirection: row

![flexWrap](/egemenmede.github.io/assets/images/flexWrap-wrap-row.png){: .center-image}
flexWrap: wrap flexDirection: row

## 5. alignItems:
 
justifyContent kapsayıcı içerisinde bulunan elemanların yatay eksen üzerinde (x ekseni) nasıl hizalanacağın belirlerken, alignItems kapsayıcı içerisinde bulunan elemanların dikey eksen üzerinde (y ekseni) nasıl hizalanacağına dair değerleri alır. Bunlar;
 
**flex-start:** İçerisindeki elemanları dikey eksende kapsayıcının başından başlayarak sıralama yapar.
 
**flex-end:** İçerisindeki elemanları dikey eksende kapsayıcının sonundan başlayarak sıralama yapar.
 
**center:** İçerisindeki elemanları dikey eksende kapsayıcı içerisinde ortalayarak sıralama yapar.
 
**stretch:** İçerisindeki elemanları dikey eksende kapsayıcı içerisinde baştan ve sona kapsayacak şekilde sıralama yapar.
 
[Kaynak](https://facebook.github.io/react-native/docs/flexbox.html#alignitems)

```javascript
var flexwork1 = React.createClass({
  render: function() {
    return (
      <View style={styles.container}>
          <View style={styles.element}><Text>Egemen - 1</Text></View>
          <View style={styles.element}><Text>Egemen - 2</Text></View>
          <View style={styles.element}><Text>Egemen - 3</Text></View>
      </View>
    );
  }
});
 
var styles = StyleSheet.create({
    container: {
        flex: 1,
        flexDirection: 'row',
        alignItems: 'stretch',
        backgroundColor: '#F5FCFF',
        borderWidth: 1,
        marginTop: 44,
    },
    element: {
        margin: 5,
        borderWidth: 1,
        padding: 10,
    },
});
```

![alignItems](/egemenmede.github.io/assets/images/alignItems-center-column.png){: .center-image}
alignItems: center flexDirection: column

![alignItems](/egemenmede.github.io/assets/images/alignItems-center-row.png){: .center-image}
alignItems: center flexDirection: row

![alignItems](/egemenmede.github.io/assets/images/alignItems-flex-end-column.png){: .center-image}
alignItems: flex-end flexDirection: column

![alignItems](/egemenmede.github.io/assets/images/alignItems-flex-end-row.png){: .center-image}
alignItems: flex-end flexDirection: row

![alignItems](/egemenmede.github.io/assets/images/alignItems-flex-start-column.png){: .center-image}
alignItems: flex-start flexDirection: column

![alignItems](/egemenmede.github.io/assets/images/alignItems-flex-start-row.png){: .center-image}
alignItems: flex-start flexDirection: row

![alignItems](/egemenmede.github.io/assets/images/alignItems-stretch-column.png){: .center-image}
alignItems: stretch flexDirection: column

![alignItems](/egemenmede.github.io/assets/images/alignItems-stretch-row.png){: .center-image}
alignItems: stretch flexDirection: row
 
## 6. alignSelf: 
 
Bu özellik elemana taşıcıya tanımlanan hizalama tanımının dışına çıkma olanağı sağlar. “alignItems” ile  tanımları ile aynı işleve sahiptir. Varsayılan değeri “auto” dur ve bu durumda taşıyıcının hizalama tanımı ile aynı şekilde hareket eder. Aldığı değerler şunlardır;
 
**flex-start:** İçerisindeki elemanları dikey eksende kapsayıcının başından başlayarak sıralama yapar.
 
**flex-end:** İçerisindeki elemanları dikey eksende kapsayıcının sonundan başlayarak sıralama yapar.
 
**center:** İçerisindeki elemanları dikey eksende kapsayıcı içerisinde ortalayarak sıralama yapar.
 
**stretch:** İçerisindeki elemanları dikey eksende kapsayıcı içerisinde baştan ve sona kapsayacak şekilde sıralama yapar.
 
**auto:** Taşıyıcının hizalama tanımı ile aynı şekilde hareket eder. Varsayılan değerdir.
 
[Kaynak](https://facebook.github.io/react-native/docs/flexbox.html#alignself)
 
```javascript
var flexwork1 = React.createClass({
  render: function() {
    return (
      <View style={styles.container}>
          <View style={styles.element}><Text>Egemen - 1</Text></View>
          <View style={styles.element}><Text>Egemen - 2</Text></View>
          <View style={styles.elementSpecial}><Text>Egemen - 3</Text></View>
      </View>
    );
  }
});
 
var styles = StyleSheet.create({
    container: {
        flex: 1,
        flexDirection: 'row',
        alignItems: 'flex-start',
        backgroundColor: '#F5FCFF',
        borderWidth: 1,
        marginTop: 44,
    },
    element: {
        margin: 5,
        borderWidth: 1,
        padding: 10,
    },
    elementSpecial: {
        margin: 5,
        alignSelf: 'flex-end',
        borderWidth: 1,
        padding: 10,
    },
});

```

![alignSelf](/egemenmede.github.io/assets/images/alignSelf-flex-start-row.png){: .center-image}
alignSelf: flex-start  flexDirection: row
 
Bitti..