آموزش چگونگی ارتباط از طریق سیستم عامل لینوکس با Github

همانطور که میدانید محیط های گرافیکی زیادی وجود دارند که توسط این برنامه ها می توانیم با گیت هاب ارتباط برقرار کنیم
از جمله برنامه های معروفی همچون:
Github Desktop
Git Cola
Git Dag
GitKeraken
و...
اشاره کرد و نام برد
همه ما میدانیم که برنامه های گرافیکی برای سهولت کاربر جهت ارتباط بین کاربر و سیستم عامل به کار گرفته می شود
اما برای یک برنامه نویس حرفه ای هیچ راهی امتحان نشده و نرفته نباید وجود داشته باشد هرچند که علوم کامپیوتر هیچ انتهای ندارد
یک برنامه نویس حرفه ای همیشه با محیطی به نام Terminal کار میکند
یعنی خبری از پنجره ها و فرم ها و ... نیست
اگر دقت کرده باشید تمام مدیران IT از محیطی به نام محیط Terminal استفاده می کنند
در لینوکس اگر کار با دستورات ترمینال را بلد نباشید هیچ تفاوتی با کاربران ویندوز ندارید

در این مقاله ارتباط بین ترمینال لینوکس و گیت هاب گفته می شود
این مقاله برای کسانی گفته شده که حداقل کار با دستورات git را بلد هستند


لینوکس استفاده شده Fedora 35 

![version-fedora](https://user-images.githubusercontent.com/64849090/153438324-cc29c776-5ad0-4030-b256-42e7231649d0.png)

گیت دستوری دارد به نام clone که با این دستور تمام محتویات آدرس گیت هاب و یا حتی جهت دانلود نرم افزار بر روی سیستم خود می توان به کار گرفت
نحوه به کار گیری دستور clone به شکل زیر است
git clone < آدرس >

حال آدرس مورد نظر را به چه صورت پیدا کنیم؟
وارد پورفایل گیت هاب خود شده و مطابق عکس زیر عمل میکنیم


سپس وارد محیط ترمینال لینوکس می شویم و یک دایرکتوری جهت انتقال و تبادل اطلاعات بین گیت هاب و سیستم عامل می سازیم ساخت دایرکتوری توسط دستور mkdir صورت می گیرد

![Screenshot from 2022-02-10 19-49-18](https://user-images.githubusercontent.com/64849090/153450493-018e99c4-6875-4318-ac71-59a37c371a5a.png)

سپس مطابق تصویر بالا وارد دایرکتوری ساخته شده می شویم و از دستور git clone استفاده می کنیم تا تمام اطلاعات گیت هاب جهت ویرایش به داخل دایرکتوری انتقال پیدا کنند

![Screenshot from 2022-02-10 19-54-20](https://user-images.githubusercontent.com/64849090/153451146-3d7e1869-a6c3-47b8-99f8-6dc57fab9ff0.png)

اگر تمام مراحل گفته شده را درست طی کرده باشیم با ورود به دایرکتوری ساخته شده میبینیم که تمام اطلاعات به دایرکتوری انتقال پیدا کردند

![Screenshot from 2022-02-10 19-57-02](https://user-images.githubusercontent.com/64849090/153451616-03e25215-da97-4b81-b620-6f56b22ca773.png)

دقت کنید در فایل README.md نوشته شده < آموزش چگونگی ارتباط از طریق سیستم عامل لینوکس با Github > 

![22](https://user-images.githubusercontent.com/64849090/153452601-06d5cab8-3b86-4e43-9d2f-52ef40030403.png)

حال اگر بخواهیم نوشته داخل فایل README.md را توسط سیستم در محیط ترمینال تغییر دهیم ابتدا وارد دایرکتوری ساخته شده می شویم و فایل README.md را با هر نرم افزار
ادیتوری یا در همان محیط ترمینال توسط vim باز می کنیم و هر نوشته دلخواهی بنا نظر شخصی مینویسیم و ثبت می کنیم . در تصویر زیر فایل README.md توسط vim باز و مورد 
ویرایش قرار گرفته

![33](https://user-images.githubusercontent.com/64849090/153453736-91d5f394-cd1c-473b-8d02-b6d06e88f70c.png)
![44](https://user-images.githubusercontent.com/64849090/153453742-20733ea8-67fc-49bf-adac-9e3ee5bdb300.png)

خوب تا اینجا توانستیم اطلاعات مربوط به گیت هاب رو به سیستم منتقل کنیم و ویرایش کنیم حال اگر بخواهیم اطلاعات داخل سیستم که تغییر پیدا کردند رو در گیت هاب اعمال 
کنیم باید چه مراحلی رو طی کنیم؟
اینجاست که دستورات گیت به ما کمک میکنند
جای نگرانی نیست در نگاه اول همه وقتی این کد ها و عکس ها رو می بینند به قول امروزی ها جا میزنند . نترسید با دقت در نوشته های این مقاله و چندبار تمرین متوجه 
می شوید که چقدر آسان و لذت بخش هست

اولین دستور در گیت که همیشه مورد استفاده قرار میگیرد دستور status است
این دستور وضعیت فایل ها که در اختیار گیت هستند رو به نمایش میگذاره

حتما دقت شود که باید ابتدا وارد دایرکتوری ساخته شده باشیم در غیر این صورت با اجرای دستور گیت اعلام می کنه که هیچ فایلی در اختیار و مدیریت من نیست
نمونه خطای گفته شده در عکس زیر مشخص است
![git error](https://user-images.githubusercontent.com/64849090/153455600-39c729a4-551c-4c0c-9b35-af1a04df3c8f.png)
اگر در تصویر بالا دقت کرده باشید متوجه می شوید که آدرس گفته شده به گیت اشتباه است این در حالی است که باید وارد دایرکتوری گفته شده بشویم سپس نام دایرکتوری ای که
قبلا ساختیم بشویم سپس دستور گیت رو اجرا کنیم

![git status](https://user-images.githubusercontent.com/64849090/153456209-f0dca603-6a43-47ba-9224-5c18424edae8.png)

در تصویر بالا گیت اعلام میکند که در برانچ main هستیم و فایل README.md با رنگ قرمز نشان دهنده آن است که تغییری در فایل صورت گرفته . تغییر همان نوشته ای است که در 
چند عکس قبلی با دستور vim به ویرایش پرداختیم . حال که تغییرات صورت گرفته برای اعمال تغییر باید ابتدا فایل تغییر کرده را add کنیم . این کار توسط دستور git add
صورت میگیرد

![git add](https://user-images.githubusercontent.com/64849090/153456997-f1041611-fe60-4aed-8a62-4eb57a8d5f5b.png)

حال مجددا دستور git status را اجرا می کنیم و میبینیم که فایل README.md به رنگ سبز در آمده که نشان دهنده آن است که دستور git add با موفقیت انجام شده
دراصل ما فایل README.md رو برای انتقال آمده کردیم . برای انتقال از دو دستور git commit و git push استفاده می کنیم

ابتدا دستور git commit -m را اجرا در عکس اگر دقت کنید بعد از آرگومان -m داخل جفت کوتیشن یک نوشته است آن نوشته می تواند نام شما باشد که وقتی وارد پروفایل گیت هاب
خود می شوید نام شخصی که داخل همان جفت کوتیشن بوده ذکر شده که نمایانگر آن است همان نام تغییر دهنده است که در صورت تایید شما تغییرات وی انجام می شود


![commit -m](https://user-images.githubusercontent.com/64849090/153459222-5d8a003e-b77e-44f8-ad60-a6d847feedcb.png)

بعد از دستور git commit نوبت به دستور نهایی که همان دستور git push --all است دقت کنید آرگومان --all به گیت می گوید که تمام تغییرات بر روی همه برانچ ها اعمال شود
نحوه اجرای دستور به شرح زیر است
git push --all



در عکس بالا دقت کرده باشید یک username و password لازم است
یوزر شما همان نام پروفایل شما است و اما پسورد . همه به اشتباه همان پسورد ورود به گیت هاب رو وارد می کنند که با خطا مواجه می شوند این پسورد آن پسورد نیست
برای داشتن پسورد باید مطابق ویدیو ضمیمه در مقاله عمل کنید

با تشکر





















