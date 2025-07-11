# :material-cloud-question-outline:{ .md .middle } سوالات متداول

??? question "چرا کانفیگ Fragment وصل نمیشه؟"
    اگر `Routing` فعال کردید و VPN متصل نشد تنها دلیلش آپدیت نبودن Geo asset هست. از منوی برنامه‌ی v2rayNG وارد قسمت `Geo asset files` بشید و اون علامت ابر یا دانلود رو بزنید تا آپدیت بشن، اگر آپدیت ناموفق باشه وصل نمیشید. اگر هر کاری کردید آپدیت نشد دو تا فایل از دو تا لینک زیر دانلود کنید و بجای آپدیت زدن، دکمه اضافه کردن رو بزنید و این دوتا فایل رو وارد کنید:
    ```title="GeoIP"
    https://github.com/Loyalsoldier/v2ray-rules-dat/releases/latest/download/geoip.dat
    ```
    ```title="GeoSite"
    https://github.com/Loyalsoldier/v2ray-rules-dat/releases/latest/download/geosite.dat
    ```

??? question "چرا کانفیگ نرمال وصل نمیشه؟"
    برای استفاده از این کانفیگ ها `Mux` رو از تنظیمات هر اپلیکیشنی که استفاده میکنید خاموش کنید.
    همینطوردر تنظیمات برنامه remote DNS به یکی از اشکال زیر  باشه:
    ```title="DoH"
    https://8.8.8.8/dns-query
    ```
    ```title="DoT"
    tls://8.8.8.8  
    ```
    ```title="TCP"
    tcp://8.8.8.8  
    ```

??? question "چرا برنامه‌های Nekobox یا Hiddify Next هیچ سایتی رو باز نمیکنن؟"
    باید داخل تنظیمات اپلیکیشن `remote DNS` رو اینجوری بذارید:
    ```title="DoH"
    https://8.8.8.8/dns-query
    ```
    ```title="DoT"
    tls://8.8.8.8  
    ```
    ```title="TCP"
    tcp://8.8.8.8  
    ```

??? question "چرا کانفیگ فرگمنت روی اپراتور من سرعتش کمه؟"
    هر اپراتوری تنظیمات فرگمنت مخصوص خودش رو داره. اکثرا با پیشفرض پنل اوکی هستن ولی ممکنه روی اپراتور شما این مقادیر بهتر باشه، باید تست کنید:
    ```title="Length"
    10-100
    ```
    ```title="Interval"
    10-20  
    ```

??? question "چرا Ping من انقدر بالاست؟"
    به هیچ عنوان از `https://1.1.1.1/dns-query` برای remote DNS استفاده نکنید چون پینگ رو بالا میبره.

    کلا استفاده از DNS های Cloudflare برای worker خوب نیست.

??? question "من از اون لینک آموزش Proxy IP گذاشتم ولی سایتا رو باز نمیکنه!"
    تعداد این IP ها زیاده و ممکنه تعداد زیادیشون پایدار نباشن. باید تست کنید تا یه خوبشو پیدا کنید.

??? question "وقتی proxy IP گذاشتم کار میکرد ولی الان از کار افتاده!"
    اگر از تک IP استفاده کنید احتمالا بعد یه مدت دوباره از کار میافته و خیلی سایتا باز نمیشن. باید از اول این مراحلو برید. ترجیحا اگر کار خاصی انجام نمیدید که نیاز به IP ثابت داشته باشه بذارید پیشفرض پنل بمونه، Proxy IP تکی نذارید.

??? question "چرا وقتی میرم به آدرس `panel/` ارور میده؟"
    طبق آموزش راه‌اندازی کنید، KV یا UUID یا Trojan Pasword درست تنظیم نشده.

??? question "دپلوی کردم ولی ارور 1101 میده کلادفلر!"
    اگر ورکر بوده از روش Pages بسازید و اگر اونم ارور داد اکانت کلادفلر شما قبلا شناسایی شده، با یک ایمیل رسمی مثل Gmail یه اکانت جدید کلادفلر بسازید و ترجیحا از روش Pages، در ضمن اسم پروژه رو حتما عوض کنید که کلمه‌ی bpb داخلش نباشه.
    [روش جدیدی](installation/wizard.md) برای Pages ارائه شده که از همه‌ی روش‌ها بیشتر توصیه میشه. در حال حاضر از این روش اقدام کنید.

??? question "آیا میتونم ازش برای ترید استفاده کنم؟"
    اگر IP کلادفلر شما آلمان هست (که معمولا همینطوره) از Proxy IP تکی آلمان استفاده کنید احتمالا مشکلی نداشته باشه ولی ترجیحا از روش Chain Proxy استفاده کنید برای فیکس کردن IP.

??? question "چرا در پنل پورت‌های none TLS رو ندارم؟"
    دقت کنید برای استفاده از کانفیگ‌های non TLS باید فقط از طریق Workers بدون دامنه‌ شخصی (Custom Domain) دپلوی کرده باشید.

??? question "کانفیگ Best Fragment چرا وصل نمیشه یا پینگ میده کار نمیکنه؟"
    از تنظیمات `Prefer IPv6` رو خاموش کنید.

??? question "چرا تماس صوتی Telegram یا clubhouse کار نمیکنه؟"
    کلادفلر نمیتونه درست پروتکل UPD رو برقرار کنه، در حال حاضر راه حل موثری براش نیست. از کانفیگ‌های Warp استفاده کنید.

??? question "کانفیگ نرمال Trojan چرا وصل نمیشه؟"
    در صورتی که با ساب نرمال میخواید وصل بشید، از هر برنامه‌ای که استفاده میکنید باید Remote DNS رو چک کنید که مثل پنل باشه، فرمت‌های udp://1.1.1.1 یا 1.1.1.1 با تروجان کار نمیکنن. فرمت‌های زیر مناسبن:
    ```title="DoH"
    https://8.8.8.8/dns-query
    ```
    ```title="DoT"
    tls://8.8.8.8  
    ```
    ```title="TCP"
    tcp://8.8.8.8  
    ```

    توصیه میکنم از ساب Full Normal یا Fragment استفاده کنید که همه‌ی تنظیمات رو خودشون دارن.

??? question "چرا ChatGPT باز نمیشه؟"
    بخاطر اینکه Proxy IP های پیشفرض پنل عمومی هستن و ممکنه خیلیاشون برای ChatGPT مشکوک باشن. از لینک زیر باید بگردید تست کنید و یه IP مناسب برای خودتون بردارید:
    ```link
    https://www.nslookup.io/domains/bpb.yousef.isegaro.com/dns-records/
    ```
    یا اینکه گزینه‌ی Bypass ChatGPT رو در قسمت routing پنل فعال کنید.

??? question "پسورد پنل یادم نمیاد چیکار کنم؟"
    به داشبورد کلادفلر برید، از قسمت KV اون KV که برای Worker یا Pages ساختید رو پیدا کنید و view رو بزنید، به قسمت KV Pairs برید، توی جدول یه pwd میبینید، مقدار روبروش پسوردتونه.

??? question "اگر UUID و پسورد Trojan رو عوض نکنم چی میشه؟"
    از وزژن 2.7.7 به بعد تنظیم این دو پارامتر الزامیه و پنل بدون این‌ها بالا نماد.

??? question "از روش آپلود Pages ساختم ولی 404 میاد."
    کلادفلر برای ثبت دامنه‌های Pages کمی زمان در حدود 4-5 دقیقه نیاز داره، بنابراین بهش زمان بدید و برگردید رفرش کنید درست میشه.

??? question "چرا پنل تیک Block Ads رو نشون نمیده؟"
    افزونه‌های uBlock یا AdGuard یا حتی بعضی مرورگرهایی که تنظیمات حذف تبلیغات دارن این کارو میکنن. برای پنل غیرفعال کنید.
