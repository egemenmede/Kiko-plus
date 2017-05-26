---
layout: post
title: "String.xml içerisinde dinamik veri görüntüleme"
description: "String.xml içerisinde statik olarak tanımladığımız metinleri, dinamik olarak kullanımı."
date: 2017-05-26
tags: [string, xml, android]
comments: true
share: true
---

## Tek parametre için;

### String.xml üzerinde tanımlama

```xml
<string name="time_ago_invoices_day">Overdue by %1$d day(s)</string>
<string name="time_ago_invoices_month">Overdue by %1$d month(s)</string>
<string name="time_ago_invoices_year">Overdue by %1$d year(s)</string>
```

### Kullanımı

```java
String.format(context.getString(R.string.time_ago_invoices_day), 3);
```

### Kod Çıktısı

```java
Overdue by 3 day(s)
```

## Birden fazla parametre için;

### String.xml üzerinde tanımlama

```xml
<string name="time_ago_invoices_day">%2$d Overdue by %1$d day(s)</string>
```

### Kullanımı

```java
String strDayFormat = context.getResources().getString(R.string.time_ago_invoices_day);
String.format(strDayFormat, diff/DAY_MILLIS, 5);
```

### Kod Çıktısı

```java
5 Overdue by 3 day (s)
```
