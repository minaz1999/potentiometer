به نام خداوند جان و خرد

نام و نام خانوادگی	تاریخ آزمایش	شماره آزمایش
مینا زواری	چهارشنبه 20 فروردین	آزمایش شماره 14


عنوان: 
طراحی و پیاده‌سازی مدار کنترل شدت نور LED با پتانسیومتر با استفاده از آردوینو
هدف آزمایش:
هدف اصلی این آزمایش، طراحی و پیاده‌سازی مداری است که در آن شدت نور یک لامپ LED با استفاده از یک پتانسیومتر و از طریق تغییر مقدار ولتاژ آنالوگ خوانده شده توسط برد آردوینو کنترل می‌شود.
تئوری آزمایش:
•	برد آردوینو UNO: این برد یک میکروکنترلر است که می‌تواند ورودی‌ها را از طریق پین‌های خود دریافت کرده و خروجی‌ها را کنترل کند. در این آزمایش، از پین‌های دیجیتال آردوینو برای کنترل لامپ‌های LED استفاده می‌شود. در این آزمایش، از یک پین آنالوگ برای خواندن مقدار پتانسیومتر و یک پین دیجیتال با قابلیت PWM برای کنترل شدت نور LED استفاده می‌شود.
•	لامپ LED: این قطعه یک دیود نورگسیل است که با عبور جریان الکتریکی از آن، نور تولید می‌کند.
•	مقاومت: برای محدود کردن جریان عبوری از LED و جلوگیری از سوختن آن، از یک مقاومت استفاده می‌شود.
•	پتانسیومتر: یک مقاومت متغیر سه سر است که با چرخاندن محور آن، مقدار مقاومت بین پایه وسط و هر یک از پایه‌های کناری تغییر می‌کند. در این آزمایش، از پتانسیومتر به عنوان یک تقسیم کننده ولتاژ استفاده می‌شود تا ولتاژ متغیری را به پین آنالوگ آردوینو اعمال کند.
•	AnalogRead()‎: یک تابع در محیط آردوینو است که مقدار ولتاژ اعمال شده به یک پین آنالوگ را خوانده و آن را به یک عدد صحیح بین 0 تا 1023 تبدیل می‌کند.
•	AnalogWrite()‎: یک تابع در محیط آردوینو است که برای تولید سیگنال PWM بر روی پین‌های دیجیتال دارای این قابلیت استفاده می‌شود. این تابع یک مقدار بین 0 تا 255 را به عنوان ورودی دریافت می‌کند که نشان دهنده Duty Cycle سیگنال PWM است و در نتیجه شدت نور LED را کنترل می‌کند.



شرح مدار و قطعات مورد استفاده:
•	برد آردوینو UNO
•	1 عدد لامپ  LED 
•	1 عدد پتانسیومتر
•	1 عدد مقاومت (220 اهم)
•	سیم‌های مخابراتی
•	برد بورد

روش انجام آزمایش:

اتصالات سخت افزاری (مطابق تصویر اول):
•	پتانسیومتر را روی برد بورد قرار می‌دهیم.
•	پایه سمت چپ پتانسیومتر را با استفاده از سیم مخابراتی به پین V5 برد آردوینو متصل می‌کنیم (سیم قرمز).
•	پایه سمت راست پتانسیومتر را با استفاده از سیم مخابراتی به پین زمین (GND) برد آردوینو متصل می‌کنیم (سیم سفید).
•	پایه وسط پتانسیومتر را با استفاده از سیم مخابراتی به پین آنالوگ A0 برد آردوینو متصل می‌کنیم (سیم سبز).
•	لامپ LED را روی برد بورد قرار می‌دهیم.
•	پایه کاتد (پایه کوتاه تر) LED را با استفاده از یک مقاومت به پین زمین (GND) برد آردوینو متصل می‌کنیم (سیم مشکی)
•	پایه آند (پایه بلندتر) LED را مستقیماً با استفاده از یک سیم مخابراتی به پین دیجیتال شماره 9 برد آردوینو متصل می‌کنیم (آبی).




	









2. برنامه نویسی آردوینو: 
o	برنامه آردوینو IDE را باز کنید.
o	کدهای زیر را در آن وارد کنید:








 

نتیجه گیری:
نتیجه‌گیری کلی آزمایش: در این آزمایش، یک مدار کنترل شدت نور LED با استفاده از پتانسیومتر و برد آردوینو طراحی و پیاده‌سازی شد. با چرخاندن محور پتانسیومتر، ولتاژ اعمال شده به پین آنالوگ A0 تغییر می‌کند. برد آردوینو این تغییرات ولتاژ را خوانده و با استفاده از تابع analogWrite()، Duty Cycle سیگنال PWM ارسالی به LED را تغییر می‌دهد. در نتیجه، شدت نور LED به طور پیوسته و متناسب با موقعیت پتانسیومتر کنترل می‌شود. همچنین، مقدار آنالوگ خوانده شده از پتانسیومتر از طریق پورت سریال قابل مشاهده است. این آزمایش نشان می‌دهد که چگونه می‌توان از ورودی‌های آنالوگ آردوینو برای کنترل خروجی‌های آنالوگ (از طریق PWM) استفاده کرد.






![IMG_20250409_114825](https://github.com/user-attachments/assets/f8a132e7-b3d1-44f9-9263-f321bcf9dfb1)
فایل ویدیو بزرگ است![potentiometer](https://github.com/user-attachments/assets/21313927-2fd1-40fd-a22d-ee5c8de3df03)
[potentiometer.pdf](https://github.com/user-attachments/files/19769187/potentiometer.pdf)
