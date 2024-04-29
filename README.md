# هارمونی


**ساخت لینک ساب** با قابلیت اضافه کردن خودکار آی‌پی تمیز کلادفلر در کانفیگ‌های VLESS

---


**دستورالعمل پیکربندی:**

**ملاحظات:**

- متن ارائه شده به عنوان دستورالعمل پیکربندی `CloudFlare Workers` ارائه می‌شود.
- فرض بر این است که مخاطب از دانش فنی لازم برخوردار است.

**مراحل:**

**1. ایجاد کانفیگ Vless:**

- از هر کد وورکر که تمایل دارید برای ساخت یک کانفیگ `Vless` استفاده کنید.
- برای ما دو عنصر کلیدی در این پروسه، `UUID` و `hostname` کانفیگ شما هستند.
- من برای مثال از این وورکر قدیمی برای ساخت یک کانفیگ vless استفاده کردم [لینک کد وورکر](_worker.js)

**2. ویرایش اسکریپت:**
- ابتدا اسکریپت هارمونی را کپی یا دانلود کنید. [لینک هارمونی](harmony.js)
- این اسکریپت را میتوان توسط [++Notepad](https://notepad-plus-plus.org/downloads/) ویندوز یا ابزارهای مدیریت فایل مانند [MT Manager](https://t.me/new_folder_revil/2720) در اندروید و یا درویرایشگر گیت‌هاب و ... ویرایش کرد، در صورت دسترسی نداشتن به هیچکدام؛ ابتدا وورکر جدید کلادفلر ایجاد کرده و این کد را داخل ان جاگذاری و سپس اقدام به ویرایش آن کنید.
- اسکریپت را برای ویرایش باز کنید.
- در ابتدا `UUID` پیش فرض در لاین `54` را با UUID خود (از داخل وورکر یا پیج خود یا از داخل یکی از کانفیگ‌های ساخت خود) کپی کرده و با آن جایگزین کنید.
- در قدم آخر از ویرایش کد باید `6` مرتبه `hostname` پیش فرض در لاین های `817-820` و `853-856` و `874-877` را با هاست‌نیم خود (مانند uuid از داخل کانفیگ خود کپی کرده) و جایگزین کنید.
- کد ویرایش شده را ذخیره کنید.

**3. ایجاد یک Worker در CloudFlare:**

- به حساب CloudFlare خود وارد شوید.
- به بخش `Workers and Pages` بروید.
- یک Worker جدید ایجاد کنید.
- > Cloudflare account > workers and pages > new application > create worker > rename > deploy.
- سپس روی گزینه `Edit Worker` کلیک کنید.

**4. وارد کردن اسکریپت در Worker:**

- قطعه کد پیشفرض در صفحه ادیتور را حذف کرده و کد شخصی‌سازی شده در مرحله قبل را در آن جایگذاری کرده و سپس برای اعمال تغییرات از گوشه سمت راست روی گزینه `deploy` کلیک کنید.
- 
- > نکته: برای بهم نریختن قالب بندی کد، لطفا از کلیدهای `ctrl+c` برای کپی کد و `ctrl+v` برای جایگذاری در ویندوز استفاده کنید، در موبایل می‌توان فایل js را درون وورکر آپلود کرد.

**5. دریافت لینک اشتراک:**

- پس از deploy شدن worker در همان محیط می‌توان با کلیک بر روی گزینه `worker.dev` لینک وورکر را در تب جدید مشاهده کرد، کانفیگ‌های داخل این لینک ساب با فرمت base64 هستند.
- از بخش آدرس بار مرورگر لینک آدرس را کپی کرده و از آن‌ به عنوان لینک ساب در کلاینت دلخواه خود استفاده کنید.در تمام کلاینت‌های ویتوری می‌توان استفاده کرد.
-  این URL به عنوان لینک اشتراک شما عمل خواهد کرد.

**6. به‌روزرسانی اشتراک:**

- بر روی دکمه `به‌روزرسانی اشتراک` داخل کلاینت خود کلیک کنید.
- این کار 30 عدد کانفیگ‌ جدید با IP های تمیز به کلاینت شما اضافه خواهد کرد.

> [!TIP]
> To achieve further personalization, please read the details provided below.

<details>
<summary> توضیحات غیرضروری </summary>
  
بالاتر گفتم واسه ی اینکه بتونید شخصا از این اسکریپت استفاده کنید برای کانفیگ‌های خود لینک ساب درست کنید باید uuid و hostname خودتون رو در لاین های ذکر شده جایگذاری کنید. حالا میخوام یکم شخصی سازی بکنیم طبق نیاز خودمون

1. ما سه تا مخزن آی‌پی داریم که از هر کدوم ده تا آی‌پی میگیره و برامون داخل کانفیگ‌ها قرار میده، جمعا سی تا
   - مخزن اول در واقع آی‌پی هایی هستن که خودم داخل کد نوشتم، از لاین `71` شروع میشن تا لاین `686` آیپی از نوع ورژن 6 هستن، و از لاین `688` دامین های پشت کلادفلر رو قرار دادم اونایی ک خوب کار میکردن رو و پشت سر اون‌ها از لاین `707` چندتا IPv4 عادی کلادفلر نوشتم تا لاین `776`. هرکدوم از این دو نوع آی‌پی و دامین هارو که دلتون خواست میتونید تغییر بدید هیچ مشکل و محدودیتی برای اینکار نداریم، میتونید کم کنید تعداد و یا زیاد کنید یا کلا حذف کنید فرضا دامین هارو ... خلاصه ک be my guess
   - مخزن دوم آی‌پی اطلاعاتش رو از [گیت‌هاب وحید فرید](https://raw.githubusercontent.com/vfarid/cf-clean-ips/main/list.json) میگیره، مخزن بدی نیست، اخرین بار در تاریخ 2024.2.10 بروزرسانی شده، این هم میتونید باز دوباره تغییر بدید به مخزن دلخواه خودتون، از لاین `826` کد قابل تغییر هستش.
   - مخزن سوم آی‌پی‌های ما اطلاعاتش رو از [گیت‌هاب YeBeKhe](https://raw.githubusercontent.com/yebekhe/cf-clean-ip-resolver/main/list.json) میگیره، اطلاعات اون در تاریخ 2024.04.29 بروزرسانی شده،این مخزن نیز از لاین `833` کد قابل تغییره.
 
</details>



 
 
 ## Disclaimer:
