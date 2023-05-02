# ابهامات
* پروتکل اسپنینگ تری
* یه دیوایس برای فهمیدن مک و آی پی بقیه دیوایس ها آرپ میزنه سوئیچ و بریج برای فهمیدن مک و آی پی بقیه چیکار میکنن ؟
* چرا داخل سوئیچ تمرین 3 پینگ نداریم ؟
* چرا داخل محیط فیزیکال رک رو نشون نمیده ؟
* استاد این ورژن سیسکو کی استون نداره ؟
* چرا ماژول های روی یک پی سی رو نمیشه عوض کرد ؟
* فرآیند NIC Teaming پشت پرده اش چه اتفاقی میوفته ؟

# خلاصه ای از نکات مهم

* دو دستگاهی که از یک خانواده هستند می بایست با کابل  `cross`  به یکدیگر وصل شوند.

<br>
<p align="center">
    <img width="500" src="assets/pictures/01.png">
</p>
<br>

* کابل های کراس تا 100 متر جوابگو هستند ولی بهتر است در فاصله های بیشتر از 70، 80 متر از آنها استفاده نشود.
* تأثیرات طول کابل را اگر در `Preferences` فعال کردیم فقط در محیط Physical اعمال می‌شود و در محیط Logical تأثیری ندارد.
* در پکت تریسر هر جا که PT در اسم دیوایس های مشاهده کردیم به این معنی هست که که این دیوایس رو پکت تریسر طراحی کرده و در دنیای واقعی وجود ندارد.
* برای تغییر موقعیت دیوایس ها در محیط Physical از منو بالا و تب `Navigation` کمک می‌گیریم و همچنین با کمک دکمه `Back` در کنار `Navigation` می‌توان به یک بخش بالاتر منتقل شد.
* برای اتصالات بین 2 کامپیوتر که بیشتر از 100 متر فاصله دارند از `Repeater` های Active استفاده می‌کنیم که اصطلاحا به `Repeater` هایی گفته می‌شود که به برق متصل شوند.
* دستگاه `Hub` در اصل همون `Repeaeter` هست با تعداد پورت های بیشتر.
* دستگاه `Hub` اطلاعاتی که به سمتش میان رو BroadCast میکنه.
* دستگاه های `Repeaeter` که به صورت Active هستند در 2 طرفشان میتواند کابل هایی با حداکثر طول 100 متر قرار بگیرد که مجموع 2 طرف باید از 200 متر تجاوز نکند.
* نکته بالا بری موارد Passive به گونه ای هست که مجموع 2 طرف نباید از 100 متر بیشتر بشود چرا که `Repeaeter` های بدون برق کار باز تولید سیگنال را انجام نمی‌دهند.
* مفهوم دستگاه `Generic` در پکت تریسر به معنی این است که این دستگاه صرفا برای شبیه سازی در پکت تریسر طراحی شده است.
* دستگاه `Hub` یک دستگاه `Half Duplex` است یعنی از send , receive به طور همزمان پشتیبانی نمی‌کند در یک لحظه یک Interface یا ارسال اطلاعات رو انجام میده یا دریافت.
* به مشکل ارسال همزمان اطلاعات توسط 2 interface روی یک بستر مشترک `Collision` یا `تصادم` گفته می‌شود.
* داخل `Hub` به شکل توپولوژی Bus طراحی شده است.
* دستگاه `Bridge` شبکه ما رو به segment تبدیل میکنه که این موضوع باعث میشه `BroadCast Domain` ما کوچک تر بشه.
* بعد از `Hub` و `Bridge` دستگاه `Switch` معرفی شد که بر خلاف دو دستگاه قبلی قابلیت برنامه ریزی داشت (`Manageable` بود) و همچنین interface های خیلی بیشتری داشت و هوشمندتر عمل می‌کرد.
* در `Rack` عبارت `PDU` مخفف Power Distribution Unit می‌باشد که تأمین کننده برق دستگاه ها در داخل `Rack` می‌باشد.
* به هر 3 سوراخ روی نوار کنار `Rack` یک `U` که مخفف `Unit` هست میگوند.
* برای تمیزتر کار کردن در شبکه های محلی برای اتصال دیوایس ها به سوئیچ در داخل رک به طور مستقیم آنها را وصل نمی‌کنیم بلکه از `Key Stone` یا `Wall jack` استفاده میکنیم که یک طرف آن در دیوار با داکت کابل از سمت رک و سوئیچ می‌آید و از طرف دیگر، کلاینت با کابل `Pach cord` که انواع مختلفی نظیر فیبر نوری یا `Twisted Pair` به `Key Stone` متصل می‌شود.
* کابل هایی که از `Key Stone` به سمت `Rack` کشیده می‌شوند برای سازماندهی بهتر هب `Pach Panel` و سپس از `Pach Panel` با کابل `Pach Core` به سوئیچ متصل می‌شوند.
* انواع ماژول 
<br>
    - ماژول های HOT PLUG (در هنگامی که دستگاه روشن باشد نیز می‌توانند تعویض شوند مثل هارد)
    - ماژول های NON HOT PLUG (امکان تعویض هنگام روشن بودن دستگاه میزبان را ندارند مثل رم)
* به هر دستگاهی که بتوان روی آن IP ست کرد `HOST` گفته می‌شود.
* عبارت `NM` مخفف Network Module هست.
* حرف `E` مخفف `Ethernet` با سرعت 10 مگ
* حرف `F` مخفف `Fast Ethernet` با سرعت 100 مگ
* حرف `G` مخفف `GIG` با سرعت 1000 مگ 
* با استفاده از قابلیت `NIC Teaming` می‌توان چند کارت شبکه رو یکی کرد که بیشتر روی سرور ها استفاده می‌شود.
* در شبکه اگر یک طرف سرعت بالاتری داشته باشه و طرف دیگه سرعتش پایینتر باشه هر دو طرف سره سرعت پایینتر توافق می‌کنند.
## مفهوم subnet mask

# مواردی که ممکنه در محیط شبیه سازی مشکل ساز باشند
* فعال کردن گزینه تاثیرات طول کابل در قسمت `prefrences`
* فایل های ذخیره شده با ورژن های بالاتر پکت تریسر روی ورژن های پایین تر باز نمی شوند.

# ترمینال
* با اجرای عبارت `ncpa.cpl` در محیط `Run windows (Win + R)` می‌توان لیست کارت شبکه ها را مشاهده کرد و همچنین می‌توان در قسمت بالای `TCP/IPv4` در Properties از یک کارت شبکه قسمت بالایی IP ست کرد مشابه کاری که برای ست کردن DNS شکن انجام می‌دهیم.
* دستور `arp -a` برای نمایش ARP Table
* دستور `arp -d` برای حذف ARP Table
* 