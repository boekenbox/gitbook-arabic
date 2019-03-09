---
description: >-
  فيما يأتي نظرة عامة سريعة حول أهم التغييرات التي تم إدخالها على Gunbot الإصدار
  12.
---

# ما الجديد في الإصدار 12؟

## الميزات والتغييرات الجديدة 

* **دعم منصة Bitmex:** يدعم Gunbot الآن التداول بالرافعة المالية في منصتي  Bitmex and Bitmex testnet. الوظيفة الجديدة `PRE_ORDER`تتيح لك الحصول على سجل الطلبيات \(order book\) لزيادة فرصة امتلاء أوامر \(limit orders\). وعن طريق `MAKER_FEES`  كل الصفقات يمكن وضعها في سجل الطلبيات ك\(post only orders\) مما يجعل Gunbot صانعا للسوق!
* **Margin trading strategies:** Strategies for Bitmex offer triggers to go long, short, stop and close on the desired ROE - or trail ROE up!
* **Blockchain license verification**: Using GUNTHY token, it is now possible to self-manage your API keys for free. Read more about [Managing API keys](https://github.com/GuntharDeNiro/BTCT/wiki/api-key-management).
* **Improved ichimoku:** Both the [regular](https://github.com/GuntharDeNiro/BTCT/wiki/Ichimoku) and [margin](https://github.com/GuntharDeNiro/BTCT/wiki/Ichimoku-margin) version of the ichimoku strategy got a lot more powerful, you can now choose to open and close trades using either Tenkan-Sen, Kumo or Kijun-Sen.
* **Market orders:** Option to use market orders instead of limit orders, customizable for all order types. Works on exchanges that support Market orders: Binance, Bitfinex, Bitmex, Coinbase Pro, Kraken and Poloniex.
* **List view in GUI dashboard**: New list view for pairs on the dashoard: all relevant info in one quick overview, improves load times especially for setups with many trading pairs.
* **Chart improvements**: The GUI can now show all Gunbot supported indicators. Trading targets are now shown in charts.
* **Renko candles:** You can now use Renko candles instead of regular candle sticks \(Currently only works for margin trading with ichimoku\).
* **Deprecating** `CANCEL_ORDERS_CYCLE_CAP` **except when using** `MAKER_FEES`: orders are now only automatically cancelled if bid/ask are above/below the order rate.
* **Retain GUI access on startup errors**: Automatically stop Gunbot core when ran without pairs. If startup errors occur, a Telegram notification is sent and core gets stopped.
* **Dark theme for the settings page**: the settings page in the GUI is now dark.
* **Renamed executables**: the main executable files got renamed to be more coherent between operating systems.
* **Various small changes**

\*\*\*\*

## إصلاحات الأخطاء

Many critical issues were already patched in the bugfix releases for v11. Notable new fixes:

* Fix an issue that would not save some settings changes made in the GUI.
* Work around Binance "minPrice" / "maxPrice" being 0.
* Improved handling of PAX & TUSD as base currency.
* Improved handling of sell orders at Binance.
* Fixes to SMACROSS, MACD and MACDH that prevented trades in specific conditions.
* Fix "RSI undefined" callback.
* Make sure a pair actually sold before letting `COUNT_SELL` disable it.
* Fix support for TUSD as base currency at Binance.
* Fix libraries for Raspberry Pi support.
* Reduced data/resource usage for the GUI.
* [Workaround](https://github.com/GuntharDeNiro/BTCT/wiki/TradingView#to-close-positions-at-bitfinex-use-the-following-alerts) for an issue with Bitfinex not accepting close orders.
* Fix an issue that reset DU count after a partial sell order.
* Fix an issue with marging trading through TV add-on on Huobi.
* Various smaller fixes.

## الترقية

قم بتنزيل التحديث وفك ضغطه إلى مجلد جديد ، وقم بنسخ ملفات `config.js` و `gunbotgui.db`من التنصيب السايق للإصدار 11 في المجلد الجديد للحفاظ على الإعدادات. في حالة استخدام https لواجهة المستخدم الرسومية، تأكد أيضًا من نسخ كل من المفتاح وملفات الشهادات إلى المجلد الجديد.

إذا كان لديك أزواج موجودة بالفعل في DU أو RT ، فقم أيضًا بنسخ مجلد json من الإصدار 11 إلى الإصدار 12.

سيتم إضافة معلمات الإستراتيجية \(Parameters\) الجديدة لـلإصدار 12 تلقائيًا من خلال واجهة المستخدم الرسومية في أول مرة تقوم فيها بتحديث استراتيجية. هذا يحدث على أساس كل استراتيجية.

_بسبب المكتبات الجديدة المستخدمة، لا يمكنك ببساطة الكتابة فوق الملف التنفيذي \(exe\) لهذا الإصدار._

{% page-ref page="../setup-and-general-settings/installation/download.md" %}

