# فروشگاه رعد — دیتابیس Google Sheets + GitHub Pages

## بخش ۱: ساخت دیتابیس (Google Apps Script)
1. در Google Sheets یک فایل جدید بسازید (مثلاً «دیتابیس رعد»).
2. از منو: **Extensions ← Apps Script**
3. کل محتوای پیش‌فرض را پاک کنید و محتوای فایل `apps-script/Code.gs` را بچسبانید.
4. در خط اول، مقدار `TOKEN` را به یک رمز طولانی و دلخواه تغییر دهید (این رمز را یادداشت کنید).
5. **Deploy ← New deployment ← Select type: Web app**
   - Execute as: **Me**
   - Who has access: **Anyone**
6. دکمه Deploy را بزنید، دسترسی‌ها را تأیید کنید (Advanced ← Go to project) و **آدرس Web app** (که به `/exec` ختم می‌شود) را کپی کنید.

> هر بار کد Code.gs را تغییر دادید: Deploy ← Manage deployments ← Edit ← Version: New version.

## بخش ۲: انتشار روی GitHub Pages
1. در GitHub یک repository جدید بسازید (مثلاً `raad`).
2. فایل‌های `index.html`، `manifest.json`، `sw.js`، `icon-192.png` و `icon-512.png` را در ریشه‌ی repository آپلود کنید.
   (پوشه‌ی `apps-script` و این README لازم نیست آپلود شود. **TOKEN را هرگز داخل GitHub نگذارید.**)
3. **Settings ← Pages ← Source: Deploy from a branch ← Branch: main / (root) ← Save**
4. بعد از یکی دو دقیقه آدرس برنامه می‌شود: `https://USERNAME.github.io/raad/`

## بخش ۳: اتصال
1. آدرس بالا را باز کنید و با رمز ورود برنامه وارد شوید.
2. **تنظیمات ← دیتابیس ابری (Google Sheets)**: آدرس Web app و TOKEN را وارد کنید و «اتصال و همگام‌سازی» را بزنید.
   - اگر شیت خالی باشد، داده‌های همین دستگاه در آن آپلود می‌شود.
   - اگر شیت داده داشته باشد، از آن بارگذاری می‌شود (نسخه‌ی قبلی همین دستگاه در `raad_db_before_cloud` مرورگر نگه‌داری می‌شود).
3. از این به بعد هر تغییر حدود ۱.۵ ثانیه بعد خودکار در شیت ذخیره می‌شود.

## نصب به‌صورت نرم‌افزار
- کامپیوتر (Chrome/Edge): آیکون نصب در نوار آدرس ← Install
- اندروید: منوی Chrome ← Install app
- آیفون: Safari ← Share ← Add to Home Screen

## نکات
- شیت‌های `products`، `invoices`، `customers`، `transactions` برای دیدن و گزارش‌گیری‌اند. منبع اصلی داده ستون `_json` است؛ ویرایش دستی سلول‌های دیگر به برنامه برنمی‌گردد.
- اگر هم‌زمان از دو دستگاه کار کنید و داده‌ی یکی جدیدتر باشد، برنامه پیام «تداخل» می‌دهد و شما انتخاب می‌کنید کدام نسخه بماند.
- بدون اینترنت هم کار می‌کند (ذخیره‌ی محلی)؛ با وصل شدن دوباره، با اولین تغییر همگام می‌شود.
