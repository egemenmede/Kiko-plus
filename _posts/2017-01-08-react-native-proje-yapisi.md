---
layout: post
title: "React Native Proje Yapısı"
description: "React Native CLI tarafından oluşturulan yeni bir uygulamanın dizinleri ve yapısı."
date: 2017-01-08
tags: [react, react native]
comments: true
share: true
---
React Native CLI tarafından oluşturulan yeni bir uygulamanın dizinleri ve yapısı aşağıdaki gibidir.

**React Native Projesi**

React Native CLI'nin oluşturduğu dosyalara bakarsanız, üç klasör olduğunu görebilirsiniz:

Bunlar;

**- android (Klasör)**

- ios (Klasör)
- node_modules (Klasör)
- index.android.js (Dosya)
- index.ios.js (Dosya)
- package.json (Dosya)
- android (Klasör)

Android projelerini içerir. Bunlar Android için standart projelerdir ve bunları sırasıyla Android Studio kullanarak çalıştırabilirsiniz.

**- ios (Klasör)**

iOS projelerini içerir. Bunlar ios için standart projelerdir ve bunları sırasıyla xCode kullanarak çalıştırabilirsiniz.

**- node_modules (Klasör)**

npm paketlerinin bulunduğu klasördür. Reakt Native de bir npm paketi ve burada uygulamanızın kullandığı diğer tüm npm kitaplıklarıyla birlikte bulunuyor.

**- package.json (Dosya)**

Bu dosya, sürüm, bağımlılıklar, komut dosyaları vb. gibi projenizle ilgili meta verileri içerir.

**- index.android.js (Dosya)**
**- index.ios.js (Dosya)**

Her iki dosya da başlangıçta aynıdır. Aynı olsa da, her platform için bir tane bulunması gerekir. Bunlar, React Native uygulamasının giriş noktalarıdır.

Örnek bir **index.android.js** dosyasının yapısı aşağıdaki gibidir;

![Proje Yapısı](/egemenmede.github.io/assets/images/ProjeYapisi.png){: .center-image}