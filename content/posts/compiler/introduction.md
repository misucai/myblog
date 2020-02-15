---
title: "اصول طراحی کامپایلر"
date: 2020-02-15T11:03:28+03:30
draft: false
description: "سری درک کامپایلر و اصول طراحی کامپایلر"
hideToc: false
enableToc: true
enableTocContent: false
tocPosition: inner
author: victor
authorEmoji: 😎
tags: 
- طراحی کامپایلر
- کامپایلر
- compiler
series:
- اصول طراحی کامپایلر
categories:
- طراحی کامپایلر فصل1

image: "images/post-image/compiler/compiler.png"
meta_image: "images/post-image/compiler/compiler-intro.jpg"
---
امروزه زبان های برنامه نویسی یک ابزار برای نمایش محاسبات به انسان و ماشین هستند و همونطور که می دونیم دنیای ما بیش از پیش به زبان های برنامه نویسی وابستگی داره چون دنیا رو کامپیوتر ها اداره میکنند و نرم افزار هایی که روی آنها در حال اجرا هستند با یک زبان برنامه نویسی نوشته شده اند
### تعریف کامپایلر
اما قبل از این که یک برنامه بتونه اجرا بشه اول از همه باید به چیزی که کامپیوتر میتونه اجرا کنه ترجمه بشه به نرم افزار سیستمی که این ترجمه رو انجام میده کامپایلر می گویند

در این سری به چگونگی ساختن یک کامپایلر و طراحی اون به طور خلاصه می پردازیم و مفاهیم پایه و ایده هایی که در ساختن یک مترجم برای زبان ها و ماشین های مختلف استفاده میشه رو یاد خواهیم گرفت
### فواید دانستن این علم 
علاوه بر کامپایلرها، اصول و تکنیک های طراحی کامپایلر در زمینه های دیگر علوم کامپیوتر قابل استفاده هست و یک دانشمند کامپیوتر یا برنامه نویس ممکن است در حرفه خود چندین بار از این مفاهیم استفاده کند
### پیش نیازها
همچنین یادگیری نوشتن کامپایلر علوم مختلفی رو در بر میگیره که از مهم ترین آنها میتوان به موارد زیر اشاره کرد
* آشنایی با زبان های برنامه نویسی
* معماری کامپیوتر و ماشین ها
* نظریه زبان ها
* الگوریتم ها
* مهندسی نرم افزار
### مباحث فصل اول
در این فصل مقدماتی شکل های مختلف مترجم های زبان (language translators) معرفی می شوند و یک مرور کلی بر یک نمونه کامپایلر خواهیم داشت و درباره مباحث ترند زبان های برنامه نویسی و روند آنها و معماری کامپیوتر و ماشین که کامپایلر ها رو در بر گرفتند بحث خواهیم کرد همچنین نگاهی بر رابطه بین طراحی کامپایلر و علوم کامپیوتر خواهیم داشت
کامپایلر ها فرا تر از کامپایل یک برنامه کاربرد های دیگری هم دارند که در ادامه به طور خلاصه بررسی می کنیم.
در پایان فصل، مفاهیم مهم زبان های برنامه نویسی که برای مطالعه کامپایلر ها نیاز داریم رو به طور خلاصه یاد میگیرم  