---
layout: post
title: "React Native Mac Kurulumu"
description: "React Native geliştirme ortamının Mac üzerinde kurulumu."
date: 2017-01-08
tags: [react, react native]
comments: true
share: true
---
React Native geliştirme ortamının Mac üzerinde kurulumu.

**1.** "**Homebrew**" i kurun. (Homebrew; uygulama mağazasında bulunmayan uygulamaları OSX'e yüklemek için kullanışlı bir araçtır. Windows muadili Chocolatey(https://chocolatey.org/))

**2.** "**Watchman**" i kurun. (Watchman, dosya değişikliklerini izleyen ve bu değişikliklere dayalı eylemleri tetikleyen bir hizmettir. Reakt Native ekibi, değişiklikleri anında kodda göstermek için önerir. Windows desteği şimdilik Alpha seviyesindedir.)

**3.** "**Flow**" u kur. (Flow, JavaScript'i daha kararlı hale getirmeye yardımcı olacak statik bir tür denetleyicisidir. Windows desteği şimdilik Alpha seviyesindedir. (static type checker: [https://en.wikipedia.org/wiki/Type_system](https://en.wikipedia.org/wiki/Type_system)))

**4.** Önceki **Node** kurulumlarını kaldırın.

```javascript
rm -rf /usr/local/lib/node_modules
brew uninstall node
```

**5.** Mac OS için **NVM** kur

```javascript
curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.30.2/install.sh | bash
```

**6.** "**Node**" u kur. (NVM (Node Version Manager)'iniz varsa ya da Node 4+ kurulduysa bu adımı atlayabilirsiniz.)

```javascript
nvm install node && nvm alias default node
```

**7.** "**React Native**" i kur.

```javascript
npm install -g react-native-cli
```

**8.** "**XCode**" u kur (iOS için İsteğe bağlı)

[https://itunes.apple.com/us/app/xcode/id497799835?ls=1&mt=12](https://itunes.apple.com/us/app/xcode/id497799835?ls=1&mt=12)

**9.** "**Java Developer Kit**" ve "**Android SDK**" yı kur (Android için İsteğe bağlı)

[http://www.oracle.com/technetwork/java/javase/downloads/index.html](http://www.oracle.com/technetwork/java/javase/downloads/index.html)
[https://developer.android.com/studio/index.html](https://developer.android.com/studio/index.html)

**10.** Mac OS için **ANDROID_PATH** tanımlayın.

```javascript
touch ~/.bash_profile
open ~/.bash_profile

export ANDROID_HOME=~/android-sdk-mac/sdk
export PATH=${PATH}:${ANDROID_HOME}/tools
export PATH=${PATH}:${ANDROID_HOME}/platform-tools
```

**11.** Bir React Native Projesi Oluşturun

```javascript
react-native init projectname
```

**12.** React Native Projesini Çalıştırın

```javascript
react-native run-android | run-ios
```