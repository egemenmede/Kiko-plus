---
layout: post
title: "React Native ile Asenkron Operasyonlar"
description: "React Native, ağ işlemleri için Fetch API'yi sunar. Daha önce XMLHttpRequest veya başka ağ API'leri kullandıysanız bu işlem size oldukça tanıdık gelecektir."
date: 2017-01-09
tags: [react, react native]
comments: true
share: true
---
**React Native**, ağ işlemleri için **Fetch API**'yi sunar. Daha önce **XMLHttpRequest** veya başka ağ API'leri kullandıysanız bu işlem size oldukça tanıdık gelecektir.
 
En basit kullanımı aşağıdaki gibidir.

```javascript
fetch('https://facebook.github.io/react-native/movies.json')
```
 
Ancak her ne kadar isteğimizi bu şekilde yapıyor olsak da servisin vereceği cevabın handle edilmesi gerekir. Bunun için "**fetch**" promise değerleri döndürür ve servisin bize döndüreceği cevaplar bunlar ile kontrol edilir.
 
Bir React Native uygulamasında hem klasik fonksiyonel yöntem hem de React Native tarafından önerilen **ES2017 async/await** sözdizimini kullanabilirsiniz.
 
Klasik fonksiyonel yöntemle fetch kullanarak çağrı aşağıdaki gibi yapılır.

```javascript
function loadJSONData() {
	return fetch('https://facebook.github.io/react-native/movies.json')
		.then((response) => response.json())
		.then((responseJson) => {
			return responseJson.movies;
	})
	.catch((error) => {
		console.error(error);
	});
}
```
 
**ES2017 async/await** sözdizimini kullanarak aynı işlem aşağıdaki gibi yapılır.

```javascript
async loadJSONData() {
	try {
		let response = await fetch('https://facebook.github.io/react-native/movies.json');
		let responseJson = await response.json();
		return responseJson.movies;
	} catch(error) {
		console.error(error);
	}
}
```
 
Bunların yanında XMLHttpRequest API ile React Native'deki tüm asenkron işlemler gerçekleştirilebilir.