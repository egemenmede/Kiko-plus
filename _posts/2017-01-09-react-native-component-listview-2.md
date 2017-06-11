---
layout: post
title: "React Native Component - ListView-2"
description: "React Native ListView kullanımı."
date: 2017-01-09
tags: [react, react native]
comments: true
share: true
---
React Native Component - ListView-2

ListView bileşeni ile yapmış olduğumuz ilk örneğimizde statik bir dataSource kaynağından verileri almış ve ekranda göstermiştik.

Bu örneğimizde hem class’ın oluşturulma şeklini değiştireceğiz hem de gerçek bir veri kaynağından JSON verilerini çekerek ekranda göstereceğiz.

İlk ListView-1 örneğimizde "**constructor**" yapısını kullanmıştık. Ancak bu örneğimizde dikkat ettiyseniz "**getInitialState**" kullandık.

Peki bu iki kullanım arasındaki fark ne? Yaptıkları işe baktığımızda göreceksiniz ki, ikisi de bileşenin başlangıç halini (initial state) kontrol etmek amacıyla kullanılıyor. Ancak iki yaklaşımın da birbirlerinin yerine geçemeyeceğini belirtelim. Temel olarak **ES6** sınıfları kullanılırken **state** bir **constructor**'da başlatılmalı, ancak **React.createClass**'ı kullanırken **getInitialState** yöntemini tanımlamalısınız. Dolayısı ile hangi yöntemi kullanıyorsanız uygun olanı tercih etmeniz yeterlidir.

Bu örneğimizin sonraki varyasyonlarında iki kullanım şeklini de kullanacağız.

Daha detaylı teknik bilgi için React Native dokümantasyonuna göz atabilirsiniz.

[https://facebook.github.io/react/docs/components-and-props.html](https://facebook.github.io/react/docs/components-and-props.html)

ListView’i doldurmak için aşağıdaki servisi kullanacağız.

[https://facebook.github.io/react-native/movies.json](https://facebook.github.io/react-native/movies.json)

Bu servisin bize dönüşü de aşağıdaki gibi olacaktır. Biz bunun içerisinde “movies” dizisini alacak ve “title” larını listemiz içerisinde göstereceğiz.

```javascript
{
  "title": "The Basics - Networking",
  "description": "Your app fetched this from a remote endpoint!",
  "movies": [
    { "title": "Star Wars", "releaseYear": "1977"},
    { "title": "Back to the Future", "releaseYear": "1985"},
    { "title": "The Matrix", "releaseYear": "1999"},
    { "title": "Inception", "releaseYear": "2010"},
    { "title": "Interstellar", "releaseYear": "2014"}
  ]
}
```

![Ekran](/egemenmede.github.io/assets/images/ListView_2.png){: .center-image}

Bu örneğimizde öğreneceğimiz yeni fonksiyonlardan biri de “**componentDidMount**“ olacak.

Native Android ile geliştirme yapanlar hatırlayacaktır, nasıl bir "**Activity Lifecycle**" ı varsa vebu yaşam döngüsü içerisinde pek çok olay gerçekleşiyorsa, aynı durum React Native'e ait olan componentlerin lifecycle’larında da yaşanıyor. Temel olarak bir React componentinin geçtiği 3 aşama bulunur. Bunlar "**Mounting**" , "**Updating**" ve "**Unmounting**" tir.

**componentDidMount**’ta bir mounting işlemidir. Buradaki işlevi, ekranda gösterilecek verinin render işleminden önce hazır hale gelmesini sağlamaktır. Bu ve diğer component lifecycle’larını daha sonra detaylı olarak inceleyeceğiz.

Bu örneğimizde dikkatimizi çeken bir diğer unsur da web servisinden veri çektiğimiz asenkron network işlemi. Bunun da detaylarına ve kullanım farklılıklarına başka bir makalemizde göz atacağız. Şimdilik yalnızca bir servisten veri çekme işlemini gerçekleştirmemiz olarak göz atabilirsiniz.

ListView Dokümantasyon sayfası;

[ListView](https://facebook.github.io/react-native/docs/listview.html)