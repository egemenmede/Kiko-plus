---
layout: post
title: "Facebook ve React"
description: "Facebookun hızla gelişen mobil ve web dunyası için ben de varım dediği teknolojilerden biri olan React, nasıl ortaya çıktı ve neler sunuyor?"
date: 2015-12-06
tags: [facebook, react, react native]
comments: true
share: true
---
Facebookun hızla gelişen mobil ve web dunyası için ben de varım dediği teknolojilerden biri olan React, nasıl ortaya çıktı ve neler sunuyor?

2015 Ocak ayındaki düzenlenen **React.js Conf**ta duyurulan **React Native**, neredeyse 1 yılını tamamlamak üzere. Getirmiş olduğunu yeni dinamiklerle ilerleyen dönemde şimdiden adından söz ettireceği ve önemli bir kitleye ulaşacağı kesin gibi.

Genelde teknolojik konularda öngörüde bulunmak zor olsa da, bu konuda **kesin gibi** bir ifade kullanmak **Facebook** için biraz daha kolay. Elbette bunun Facebook'un devasa bir kitleye ve maddi güce sahip olmasının yanında, dikkat edilmesi gereken asıl konunun **tecrübe etmek** olduğunu söyleyebiliriz. Bu yüzden biraz geriye dönüp bakalım ve Facebook React'a kadar neler geçirmiş bir göz atalım.

## Facebookun HTML5 ile imtihanı

**HTML5** tabanlı mobil geliştirmenin dünyaya hızla yayılmaya başladığı dönemde Facebook'ta bu rüzgar ile HTML5 frameworklere ciddi yatırımlarda bulunmuş, o günlerde kullanılmakta olan mobil uygulamasını da HTML5 tabanlı olarak çıkarmıştı. Ancak 2 yıl boyunca sürdürdüğü ve deneyimlediği bu sistemler, o dönem gerçek manada yeni doğum günlerinde olduğu için başarısız olarak kabul edildi ve native mobil uygulamaya geçiş yapıldı.

**Mark Zuckerberg**in We burned two years betting on mobile web vs. app sözleriyle o dönem kapatılmış oldu ve

>I think the biggest mistake that we made, as a company, is betting too much on HTML5 as opposed to native.. Because it just wasn’t there.. (Facebook, Eylül 2012) (Bizim şirket olarak en büyük hatamız HTML5'e nativeden çok daha fazla yatırım yapmamız oldu. Çünkü o seviyede değil..)

denilerek hata yaptıklarını belirttiler.

Ancak bu dönemde Facebook, uygulamasının doğru şekilde yapılandırılmadığı eleştirilerine maruz kaldı. Bu konudaki usulünce en sert eleştiri **Sencha Framework**ünün yapımcılarından geldi. **Sencha**dan **Lead Architech**i **Jacky Nguyen** ve **Engineering Manager**ı **Jamie Avins**in yayınladığı video o dönem efsane haline geldi.

[Sencha Fastbook](https://youtu.be/wCn3R3-XxBU)

Facebookun uygulamasını HTML5 ile geliştirip **Fastbook** ismiyle demosunu yapan Sencha, aslında Facebookun söylediği sebepler konusunda hiç de haklı olmadığını ispatlar gibiydi..

## Facebookun çalışma dönemleri..

Teknoloji sektörü şüphesiz dünyanın en hareketli sektörlerinden biri. Ancak geçmiş dönemlerden bugünlere baktığımızda genelde başarılı olanların yeni dinamikler ve yeni bakış açısı kazandıranlar olduğunu çok net bir şekilde görebiliyoruz. Aslında bu duruma günümüz popüler kelimesi ile inovasyon olarak tanımlanıyoruz.

## Geçmişe biraz göz atalım..

**JQuery** çıktığı dönemden itibaren web dünyasında kasıp kavurdu. Zira **Write less, do more** diyerek yeni dinamikler getirdi ve uzun kod satırları ile yaptığımız işlemleri çok daha kısa sürede ve çok daha az kod ile yapılabileceğini gösterdi. Günümüzün en popüler yazılım dillerinden olan **Java**nın ortaya çıkarttığı temel felsefesi **write once, run anywhere/bir kere yaz, her yerde çalıştır**, Javayı bugün bulunduğu konuma taşımış ve ortam bağımsız kavramı ile eş zamanlı olarak anılmaya başlanmıştır.

Bir diğer çarpıcı örnek **PhoneGap/Cordova**dır. Bugün akıllı telefon diye bahsettiğimiz cihazların bugünküne yakın ilk örneklerinin çıkmaya başladığı dönemde Kanadalı **Nitobi** firması, yeni bir düşünce tarzı ile geldi. Akıllı telefonların hepsi bir web tarayıcı çalıştırabiliyorsa, neden tüm cihazların mobil uygulamalarını bir tarayıcı üzerinden çalıştırmıyor ve maliyet, süre, öğrenim süresi, bakım kolaylığı gibi pek çok konuda fayda sağlamıyoruz diye düşündü ve ortaya PhoneGap çıktı. Yalnızca çıkmakla kalmayıp, konusunda çok kısa sürede hem ciddi bir destek hem de popülerlik kazanmış oldu. Bugün Apache, Apple, Microsoft, Adobe, IBM, SAP, Motorola gibi sektör devleri tarafından halen desteklenmekte ve özellikle kurumsal mobil uygulama geliştirme alanında büyümeye devam ediyor.

## Facebook ne yapıyor?

Facebook bir sosyal medya devi olmasının yanında aynı zamanda kendi kullandığı teknolojilere de ciddi şekilde odaklanan bir teknolji devi. **React** ile birlikte getirilmiş düşünceyi **Facebook** mühendislerinden **Tom Occhino**, farklı teknolojiler öğrenmeye gerek kalmadan farklı işletim sistemleri için uygulamalar geliştirmenin **learn once, write anywhere/bir kere öğren, her yere yaz** düşüncesinden ortaya çıkacağını belirtiyor.

Yukarıda özetlediğim bakış açısını Tom Occhino şu şekilde açıklıyor;

>What we really want is the user experience of the native mobile platforms, combined with the developer experience we have when building with React on the web.

>With a bit of work, we can make it so the exact same React thats on GitHub can power truly native mobile applications. The only difference in the mobile environment is that instead of running React in the browser and rendering to divs and spans, we run it an embedded instance of JavaScriptCore inside our apps and render to higher-level platform-specific components.

>Its worth noting that were not chasing “write once, run anywhere.” Different platforms have different looks, feels, and capabilities, and as such, we should still be developing discrete apps for each platform, but the same set of engineers should be able to build applications for whatever platform they choose, without needing to learn a fundamentally different set of technologies for each. We call this approach “learn once, write anywhere.

Facebookun HTML 5 ile imtihan ettiği dönemden bugüne ciddi bir çalışma dönemi geçirdiğini, bugün çok daha iyi idrak ediyor ve gelişimleri çok iyi takip ettiğini gayet iyi anlıyoruz. Zira o dönemden bugüne HTML5 frameworklerden edindiği izlenimleri, **Google**ın **AngularJS** ile web ve mobil ortamda aldığı yolu, PhoneGap/Cordova gibi teknolojilerin getirdiği kolaylıkları, native geliştirmenin sağladığı yüksek performans avantajını iyi analiz edip, **React**ın çıkışını buna göre hazırlamış durumda. Bu sebeple web teknolojileri için **ReactJS**, mobil dünya için ise **React Native**i geliştirmeye devam ediyor.

## React Native nedir?

Aslında Nedir? sorusundan önce Nerede? sorusunu cevaplamakta fayda var. Her ne kadar ismi React Native de olsa native diller ile yazılmıyor. Native dillerden kastımız şu; **Android** geliştiriyorsanız **Java**, **iOS** geliştiriyorsanız **Objective C** veya **Swift** kullanılmıyor. **JavaScript** kullanılarak geliştiriliyor. Bu yönüyle native olarak kabul edemeyeceğimiz gibi, hem PhoneGap/Cordova hem de **Titanium Appcelerator** ile aynı paralelde olduğunu söyleyebiliriz. Ancak PhoneGap/Cordova gibi bir native container üzerindeki bir WebView olarak değil, Titanium Appceleratorde olduğu gibi tamamıyla native çıktı oluşturduğunu söyleyebiliriz. Bu yönüyle de daha önce çeşitli platformlarda vermiş olduğum [PhoneGap/Cordova ile Mobil Uygulama Geliştirmeye Giriş](https://www.slideshare.net/egemenmede/phonegapcordova-ile-mobil-uygulamaya) seminerinde Cross Platform geliştirme yaklaşımlarından Runtimes (Çalışma Zamanı Uygulamaları) kategorisine eklenebilir.

Ancak Titanium, yalnızca mobil teknolojilere odaklanmış bir teknoloji olması ve tek kod tabanı ile birden fazla platforma geliştirme yapılması konusunda React'tan ayrılır. Zira React, her platforma özel yeniden o platforma özel UI bileşenleri ile yazılır. Bu noktada hem bir cross platform yaklaşımı olarak kabul edilebilir, hem de kabul edilmeyebilir. Zira React bu yönüyle yepyeni bir inovasyon getiriyor.

## Bitirirken..

Facebook dersine kesinlikle iyi çalışmış. Geliştirdiği teknoloji ile hem web hem de mobil dünyaya farklı bir soluk getireceği aşikar. Getirmiş olduğu yeni düşünce tarzı, başta developerlar için bir öğrenim süreci alacak olmasının yanında, hem web hem de mobil dünya için geliştirme yapmaya imkan tanıyacak olması, React'ı öne çıkaran en önemli sebeplerden biri olacak.