# Flutter-RoadMap
This is the documentation of my flutter learning journey, it may prove helpful for others or myself in the future.

## نصب فلاتر
بدون معطلی میرم سراغ معرفی مسیر خودم از یادگیری فریم ورک جذاب فلاتر. بدیهیه که ابتدا باید فلاتر نصب بشه آموزش های زیادی در اینترنت در مورد این هست من هم طبق اون ها پیش رفتم و در نهایت باید به این نقطه برسی که دستور flutter doctor رو در ترمینال بزنی و هیچ خطایی وجود نداشته باشه و همه چیز نصب باشه.

## نمای کلی برنامه نویسی با فلاتر

وقتی به دنیای یک زبان برنامه نویسی جدید وارد میشم برام خیلی جذابه که بدونم چطور صفر تا صد یک پروژه قراره با این زبان نوشته بشه و دوست دارم ابتدا یک نمای کلی از تمام مسیری که قراره پیش روم باشه ببینم برای همین این ویدیوی یوتیوب رو دیدم:

Flutter basics by a real project: https://www.youtube.com/watch?v=D4nhaszNW4o

## پیاده سازی رابط کاربری (UI)

این جمله ی تکراری رو میگم: در فلاتر همه چیز ویجت هست. پس ابتدا باید ببینیم چطور میشه از این ویجت ها استفاده کرد تا یک رابط کاربری جذاب ایجاد کرد. برای این کار من اولین منبع خودم رو که کمک کرد دست به کد بشم این منبع میدونم هرچند ممکنه جسته و گریخته از مطالب دیگه هم استفاده کرده باشم؛

پروژه اینستاگرام با فلاتر از سایت تاپ لرن. این دوره رایگان تمرکز اصلیش روی رابط کاربری (UI) است و ترس شما رو از ایجاد رابط های کاربری مدرن به کل میریزه:

Toplearn Instagram UI with flutter: https://toplearn.com/c/5958

## مطالعه ی اصولی
با وجود تمام ویدیوهای باحال توی اینترنت من همیشه بهترین نتیجه رو از مطالعه کردن گرفتم چون وقتی مطالعه میکنی بیشتر باهاش درگیر میشی و البته نوشته ها هم ساختاربندی بهتری نسبت به ویدیوها دارن. کتابی که معرفی میکنم اومده ابتدا از معرفی ویجت ها شروع کرده، بعدش دیالوگ ها رو گفته و ادامه ماجرا. در کنارش میتونین از داکیومنت های خود فلاتر استفاده کنین تا مطالب رو عمیق تر یاد بگیرین:

Practical Flutter (Frank Zammetti): https://link.springer.com/book/10.1007/978-1-4842-4972-7

ضمنا میتونید کتاب های فلاتر رو از این لینک گیت هاب دانلود کنید:

Flutter Books: https://github.com/imrishuroy/Flutter/tree/master

بعد از این که فصل 3 کتاب رو خوندین میتونین به آموزش بعدی مراجعه کنین

## ارتباط رابط کاربری با کد (UX)
من اکثر ویدیوهایی که در مورد فلاتر میدیدم قسمت UI رو خیلی خوب آموزش میدادن ولی با توجه به تغییراتی که فلاتر نسبت به زبان های قبلی ای که کار کردم مثل جاوا و سی شارپ داره همیشه برام سوال بود که چطور UI رو به کد ارتباط بدم. خیلی خلاصه میگم که باید از Stateful Widget استفاده کنی یعنی State اون در طول برنامه تغییر میکنه، بعد مثلا جایی که داری Button رو تعریف میکنی یک attribute به نام onClick بهش نسبت میدی که مقدارش اسم تابعی هست که قراره موقع کلیک کردن فراخوانی بشه. بعد توی اون تابع بعد از اجرای کدها، تابع SetState رو فراخوانی میکنی که به معنی آپدیت شدن UI هست و یک سری مقادیر رو توی یک متغیرهایی ذخیره میکنی، اونوقت ویجت Stateful میاد بر اساس متغیرهای تغییر داده شده، رابط کاربری رو مجددا build میکنه.

اگه بخوای در تابع مقداری که توی یک Text نوشته شده رو بخونی باید یک TextEditingController به اتریبیوت controller اون Text نسبت بدی و بعد از طریق کنترلر مقدار رو بخونی.

برای درک این موضوع یک مثال خیلی ساده جمع دو عدد و محاسبه نتیجه رو به کمک Gemini نوشتم و ازش خواستم تمام کد رو خیلی ساده توضیح بده که میتونی اینجا ببینی:

Sum Two Numbers: [Documents/SumTwoNumbers.md](Documents/SumTwoNumbers.md)

حالا اومدم یکم تغییرات توی کد دادم و اونو تبدیل کردم به یک صفحه لاگین و ثبت نام که خیلی ساده کاربرها رو توی یک لیست ذخیره میکنه و از توی لیست هم میبینه:

Simple Login Page: [Documents/SimpleLoginPage.md](Documents/SimpleLoginPage.md)

بعد از این صفحه ی ساده لاگین مطمئنا مرحله ی بعدی که به ذهن آدم میرسه اینه که این اطلاعات رو در یک دیتابیس ذخیره کنه. پس مرحله ی بعدی یادگیری دیتابیسه.

قبل از یادگیری دیتابیس در فلاتر لازمه که با یک مفهوم به نام Future آشنا بشین، فیوچر برای زمانی استفاده میشه که دریافت یک سری اطلاعات مدتی زمان میبره و شما نمی‌خواهید برنامه تون تا زمانی که اطلاعات در دسترس نیست منتظر بمونه، در عوض میخواید که از یک عملیات غیر همزمان برای دریافت اطلاعات و ادامه اجرای کد در حین انجام این فرآیند استفاده کنید.

Futures In Flutter: [Documents/FuturesInFlutter.md](Documents/FuturesInFlutter.md)

در مرحله ی بعدی برای یادگیری دیتابیس پیشنهاد میکنم این ویدیو رو ببینید:

Flutter Local Database: [Flutter Local Database Using sqfLite](https://www.youtube.com/watch?v=q8UXj-44dk8)

همچینین سورس کد مربوط به ویدیو از این لینک قابل دانلود است:

Flutter Local Database: [Flutter Local Database Github](https://github.com/yehya-qassim/local_database)

## دوره ی آموزشی

میرسیم به مرحله ای که دیگه لازمه یک دوره کامل همراه یک پروژه عملی انجام بشه. به نظرم دوره عماد قاسم پور از آکادمی welearn میتونه برای شروع مناسب باشه. این دوره کاملا رایگانه.

Welearn Flutter Course: [Flutter and Dart from scratch]https://welearn.site/course/flutter-video-tutorial/


