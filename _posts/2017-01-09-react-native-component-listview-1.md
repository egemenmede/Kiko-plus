---
layout: post
title: "React Native Component - ListView-1"
description: "React Native ListView kullanımı."
date: 2017-01-09
tags: [react, react native]
comments: true
share: true
---
ListView bileşeni, değişen ancak benzer şekilde yapılandırılmış verilerin dikey olarak kaydırılan bir listesini görüntüler.

ListView bileşeni iki özellik gerektirir. Bunlar **dataSource** ve **renderRow**'dur. **DataSource**, oluşturulacak liste için veri kaynağını belirtir. **RenderRow** ise kaynaktan bir öğe alır ve biçimlendirilmiş şekilde bileşeni geri döndürür. Bunun yanında ListView kullanmak için bir **rowHasChanged** işlevi gereklidir. Burada, üzerinde bulunduğumuz sıra bir önceki satırla aynı değilse bir satırın değiştiğinin belirtilmesi gerekir.

Şimdi bunun için en basit haliyle bir ListView örneği yapalım.

![Ekran](/egemenmede.github.io/assets/images/ListView_1.png){: .center-image}

Daha fazla bilgi için kaynak kodlarına göz atın.

[ListView.js](https://github.com/facebook/react-native/blob/master/Libraries/CustomComponents/ListView/ListView.js)

[ListViewDataSource.js](https://github.com/facebook/react-native/blob/master/Libraries/CustomComponents/ListView/ListViewDataSource.js)