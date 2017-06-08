---
layout: post
title: "Android için APK Split Kullanımı"
description: "Android uygulamaları geliştirirken oluşturduğumuz APK dosyaları bazen oldukça büyük boyutlara ulaşabilir. Bunlar çoklu ekranları ya da tüm işlemci mimarilerinin desteklemek, gereksiz dosyaları APK içerisinde bulundurmak gibi pek çok sebepten gerçekleşmiş olabilir. Bunları küçültmenin pek çok yolu bulunuyor."
date: 2017-06-08
tags: [android, multiple apk]
comments: true
share: true
---
Android uygulamaları geliştirirken oluşturduğumuz APK dosyaları bazen oldukça büyük boyutlara ulaşabilir. Bunlar çoklu ekranları ya da tüm işlemci mimarilerinin desteklemek, gereksiz dosyaları APK içerisinde bulundurmak gibi pek çok sebepten gerçekleşmiş olabilir. Bunları küçültmenin pek çok yolu bulunuyor.

APK dosyanızın neden büyük boyutlarda olduğunu öğrenmek için [Android Studio ile APK Analyzer Kullanımı](https://egemenmede.github.io/2017-06-04/apk-analyzer/) isimli yazımda bahsettiğim APK Analyzer'ı kullanmanızı tavsiye ederim. İncelediğinizde göreceksiniz ki APK dosyalarının içeriği META-INF, assets, res, lib, resources.arsc, classes.dex, AndroidManifest.xml gibi dosya ve klasörlerden oluşur. Buradaki dosyaların boyutlarına göre APK büyüklüğünün nereden kaynaklandığını öğrenebilirsiniz.

APK dosyalarını küçültmenin yollarından biri de bu yazımızın konusu olan split kavramı. APK Split ile Application Binary Interfaces (ABIs)'ye özgü kod ve kaynakları içeren ayrı APK'lar oluşturabilir, dağıtımlarınızı bu şekilde yapabilirsiniz. Yani oluşturacağınız APK'ları Android'in desteklediği [farklı işlemci mimarilerine](https://developer.android.com/ndk/guides/abis.html#sa) göre oluşturabilirsiniz.

Bunun için Gradle dosyanızı aşağıdaki gibi [düzenlemeniz](https://developer.android.com/studio/build/configure-apk-splits.html) gerekiyor.

```java
android {
  ...
  splits {

    // Birden fazla APK'yi ABI'ya göre yapılandırır.
    abi {

      // ABI başına birden fazla APK oluşturmayı etkinleştirir.
      enable true

      // Varsayılan olarak tüm ABI'lar dahil edilmiştir. Bu yüzden "reset()" kullanın ve yalnızca x86, armeabi-v7a ve mips için APK oluşturmak istediğinizi belirtmek için ekleyin.

      // ABI'ların listesini sıfırlar.
      reset()

      // Gradle'ın hangi ABI'lere ait APK'ların oluşturması gerektiğinin bir listesini belirtir.
      include "x86", "armeabi-v7a", "mips"

      // Tüm ABI'ları içeren bir evrensel APK da oluşturmak istemediğimizi belirtir. Bu aynı zaman split işlemi yapılmadan default oluşturulan APK'yı belirtir.
      universalApk false
    }
  }
}
```