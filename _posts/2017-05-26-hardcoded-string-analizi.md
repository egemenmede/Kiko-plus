---
layout: post
title: "Hardcoded String Analizi"
description: "Hardcoded olarak kullanılmış, yani kod içerisinde direkt metin olarak yazılmış alanlar best practicies olarak doğru bir kullanım şekli değildir. Bu sebeple Android geliştirirken Hardcoded olarak kullanılmış metinlerin Java dosyaları içerisinden de  xml’ ler içerisinden de temizlenmesi gerekir."
date: 2017-05-26
tags: [string, xml, android, hardcoded]
comments: true
share: true
---
Hardcoded olarak kullanılmış, yani kod içerisinde direkt metin olarak yazılmış alanlar best practicies olarak doğru bir kullanım şekli değildir. Bu sebeple Android geliştirirken Hardcoded olarak kullanılmış metinlerin Java dosyaları içerisinden de  xml’ ler içerisinden de temizlenmesi gerekir.

Bunun için tabi ki tüm dosyaları teker teker taramasını yapmayacağız.  Android Studio’ nun “Analyze” menüsünü kullanacağız.

### ADIM-1:

“Analyze” menüsünden “Run Inspection by Name...” menüsünü seçelim.

![Hardcoded String Analizi Adım-1](/egemenmede.github.io/assets/images/hardcoded_adim1.png){: .center-image}

### ADIM-2:

![Hardcoded String Analizi Adım-2](/egemenmede.github.io/assets/images/hardcoded_adim2.png){: .center-image}

Açılan arama kutusunda 2 metni kullanarak işlemimizi gerçekleştireceğiz. 

Birincisi; eğer xml’ler üzerindeki hardcoded stringleri düzeltecek isek “Hardcoded Text” diye aratarak, 
İkincisi; eğer Java dosyaları üzerindeki hardcoded stringleri düzeltecek isek “Hardcoded String” diye aratarak yapabiliriz.

### ADIM-3:

![Hardcoded String Analizi Adım-3](/egemenmede.github.io/assets/images/hardcoded_adim3.png){: .center-image}

Açılacak olan arama ekranında, hangi bölümde arama yapmak istiyorsanız gerekli özellikleri seçebilirsiniz. “OK” butonuna bastığınızda ise aşağıdaki gibi hardcoded olarak yazılmış stringler dosya dosya listelenecektir.

### ADIM-4:

![Hardcoded String Analizi Adım-4](/egemenmede.github.io/assets/images/hardcoded_adim4.png){: .center-image}

Gerekli düzeltmeleri bu arama sonucu üzerinden toplu halde takip edebilir ve hardcoded stringleri düzeltebilirsiniz.