---
layout: post
title: "React Native Api - ToastAndroid"
description: "React Native ile Toast kullanımı."
date: 2017-01-09
tags: [react, react native]
comments: true
share: true
---
Android kullanıcı ve geliştiricilerinin yakından tanıdığı ”**Toast**” mesajının **React Native**’deki karşılığıdır.
 
**show** ve **showWithGravity** olmak üzere 2 metodu bulunur. Kullanım şekli aşağıdaki gibidir.
 
```javascript
static show(message, duration) 
static showWithGravity(message, duration, gravity)
```

**message:** Bu bölümde Toast içerisinde görüntülenecek metni belirtir. 
**duration:** ToastAndroid.SHORT ve ToastAndroid.LONG olmak üzere iki değer alır. Biri kısa diğeri de uzun gösterim şeklidir.
**gravity:** Bu parametre showWithGravity metodu ile birlikte kullanılır. ToastAndroid.TOP, ToastAndroid.BOTTOM ve ToastAndroid.CENTER olmak üzere 3 değer alır.

![Ekran](/egemenmede.github.io/assets/images/ToastAndroid.png){: .center-image}