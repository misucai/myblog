---
title: "نصب فتوشاپ cc در گنو لینوکس"
date: 2020-02-14T22:15:50+03:30
draft: false
description: "نصب فتوشاپ cc در گنو لینوکس با استفاده از یک بش اسکریپت"
hideToc: false
enableToc: true
enableTocContent: false
tocPosition: inner
author: victor
authorEmoji: 😎
tags:
- نصب فتوشاپ cc در لینوکس
- فتوشاپ cc
- photoshop
categories:
- کاربردی
- گنو/لینوکس
series:
-
image: "images/post-image/2020/photoshop.png"
meta_image: "images/post-image/2020/photoshop.jpg"
---
![photoshop cc on linux](/images/post-image/2020/photoshop.jpg)
## مقدمه
از آنجایی که فتوشاپ یکی از ابزار های قدرتمند ویرایش تصویر هست و افراد زیادی با اون سرو کار دارن و یکی از چیزهایی که بعد از مهاجرت به گنولینوکس باهاش مواجه می شوید نبودن این ابزار برای این سیستم عامل هست اگر چه جایگیزین های خیلی خوب و متن باز مثل [Gimp](https://www.gimp.org/) وجود دارند و چه بهتر اگر بتونید از این ابزار ها به جای فتوشاپ در گنو لینوکس استفاده کنید.
اما برای افرادی مثل من که قبلا فتوشاپ رو یاد گرفتیم شاید یکم یاد گرفتن گیمپ زمان بر و خسته کننده تر باشه همچنین قدرتمند بودن فتوشاپ و وجود آموزش های زیاد تر و رابط کاربری دلچسبش از دلایل دیگری هست که نمیتونید ازش دل بکنید.
برای همین تصمیم گرفتم داخل لینوکس نصبش کنم و بعد از کلی آزمون خطا و نصب برنامه های پیش نیاز در کنار [wine](https://www.winehq.org/) به نتیجه مطلوب و قابل قبولی رسیدم و برای اینکه روند کار و کانفیگ واین رو سریع تر کنم یک [بش اسکریپت](https://github.com/Gictorbit/photoshopCClinux) نوشتم که این کار رو اتوماتیک برای شما می کنه و درگیر کانفیگ واین و نصب نیازمندی ها نمیشید در ادامه روش نصب با اسکریپت رو مرور می کنیم

## معرفی Wine
خب چون فتوشاپ نسخه لینوکس نداره ما مجبوریم نسخه ویندوز رو در لینوکس با یکم جینگولک بازی نصب کنیم و برای این کار از ابزاری به نام واین یا [wine](https://www.winehq.org/) استفاده میکنیم این ابزار یک ویندوز رو داخل لینوکس شبیه سازی میکنه و ما میتونیم فایل exe فتوشاپ رو داخلش نصب کنیم من برای کارایی بهتر فتوشاپ در کنارش dll های مورد نیاز رو قرار میدادم خوشبختانه شما هیچ نیازی به فایل فتوشاپ و یا dll ها ندارید اسکریپت در صورت نیاز همه اجزا رو دانلود میکنه قبل از نصب میتونید wine رو از مدیر بسته توزیع خودتون نصب کنید برای مثال در آرچ لینوکس:
```bash
sudo pacman -Syy wine
```
## قابلیت ها
* نصب نسخه photoshop cc v19
* به حداقل رساندن لگ و کندی با استفاده از نصب dll ها و برنامه های پیش نیاز مثل (`msxml`,`vcrun`,`atmlib`,...)
* پشتیبانی از برند های مختلف کارت گرافیک مثل (`intel`,`Nvidia`,...)
* نصب نسخه اکتیو شده دائم بدون نیاز به شماره سریال و فعال ساز
* دانلود خودکار فایل فتوشاپ و نرم افزار های مورد نیاز
* ساختن آیکون دسکتاپ برای لانچر
* کانفیگ واین به صورت خودکار و پشتیبانی از دارک مود
## نصب فتوشاپ
برای نصب اول از همه باید اسکریپت رو از گیت هاب کلون کنیم با دستور زیر:
```bash
git clone https://github.com/Gictorbit/photoshopCClinux.git
```
بعد از کلون کردن ریپوزیتوری وارد دایرکتوری میشیم و به اسکریپت قابلیت اجرایی میدیم:
```bash
cd photoshopCClinux
chmod +x PhotoshopSetup.sh
```
قبل از اجرای اسکریپت از نصب بودن دانلود منیجر `aria2` در توزیع خود مطمئن بشید چون اسکریپت برای دانلود فایل ها از این برنامه در پشت صحنه استفاده میکنه مثلا برای نصب از مدیر بسته در آرچ:
```bash
sudo pacman -S aria2
```
### اجرای اسکریپت
برای اجرای اسکریپت بعد از انجام قدم های بالا فقط کافیه دستور زیر رو در فولدر ریپوزیتوری بزنید و اسکریپت `PhotoshopSetup.sh` رو اجرا کنید
```bash
./PhotoshopSetup.sh
```
بعد از اجرا، اسکریپت داده های مورد نیاز رو دانلود و در مسیر `/home/$USER/.photoshopCCV19/` نصب می کنه هم چنین فایل های دانلود شده در کش شما ذخیره می شوند تا برای نصب دوباره نیازی به دانلود دوباره نداشته باشید همچنین می تونید از فایل های موجود در مسیر `/home/$USER/.cache/photoshopCCV19/` بکاپ بگیرید و دفعات بعدی برای نصب از آنها استفاده کنید
## حذف فتوشاپ
برای حذف فتوشاپ فقط کافیه اسکریپت `uninstaller.sh` رو با دستورات زیر اجرا کنید
```bash
chmod +x uninstaller.sh
./uninstaller.sh
```
{{< box >}}
برای اطلاعات بیشتر به صفحه <a href="https://github.com/Gictorbit/photoshopCClinux">ریپوزیتوری</a> در گیتهاب مراجعه کنید
{{< /box >}} 

 


