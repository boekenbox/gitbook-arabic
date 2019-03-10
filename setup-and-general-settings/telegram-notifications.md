# إشعارات التليجرام \(Telegram\)

يمكن لـ Gunbot إرسال إشعارات على Telegram لكل تداول يقوم به.

لإعداد هذا ، انتقل إلى الإعدادات \(**Settings\)** &gt; التليجرام  **\(Telegram\)**.

![Available settings options for Telegram notifications.](../.gitbook/assets/image-24.png)

## خطوات إنشاء بوت Telegram

تعمل الإشعارات أولا من خلال إنشاء بوت شخصي على Telegram، ثم يتصل Gunbot بهذا البوت لدفع الإشعارات إليك.

هذه هي الطريقة لإنشاء البوت:

1. افتح محادثة مع [@botfather](https://telegram.me/botfather). ثم قم بإنشاء بوت جديد باستخدام الأمر /newbot واختر اسمًا واسمًا للمستخدم للبوت الخاص بك \(username\)، ثم احفظ رمز البوت \(Token Id\).
2. افتح محادثة مع [@myidbot](https://telegram.me/myidbot) لرؤية معرف الدردشة الخاصة بك \(Chat ID\) ثم قم بحفظه.
3. قم بتمكين إشعارات Telegram لـ Gunbot، وأدخل رمز البوت \(Token Id\) ومعرف الدردشة \(Chat ID\) الذي جمعته منذ قليل.
4. ابدأ محادثة باستخدام اسم المستخدم الذي اخترته لبوتك \(username\)، ثم اضغط على زر البدء. إذا كنت لا ترى زر البدء ، فاكتب "/start" ثم انقر فوقه.

## وصف الإعدادات

ستجد بالأسفل وصفا مفصلا لجميع المعلمات المتاحة \(available parameters\) لإخطارات Telegram.

### مفعل \(Enabled\)

{% tabs %}
{% tab title="الاسم" %}
اسم المعلمة \(Parameter name\) في ملف الإعدادات `config.js`: `TELEGRAM_ENABLED`
{% endtab %}

{% tab title="القيم" %}
**القيم:** true or false

**القيمة الافتراضية:** false
{% endtab %}

{% tab title="الوصف" %}
تمكين هذا لجعل Gunbot يرسل إشعارات التداول عبر Telegram.
{% endtab %}
{% endtabs %}

### اسم الشهرة \(Bot Nickname\)

{% tabs %}
{% tab title="Description" %}
Each trade notification starts with the nickname set here.

Use this to easily check from which bot instance the notifications have been sent.
{% endtab %}

{% tab title="Values" %}
**Values:** string

**Default value:** Gunbot
{% endtab %}

{% tab title="Name" %}
Parameter name in `config.js`: `TELEGRAM_NICK`
{% endtab %}

{% tab title="الوصف" %}
يبدأ كل إخطار تداول باسم الشهرة الذي يتم تعيينه هنا.

استخدم هذا لتتحقق بسهولة من أي من نسخة bot التي ترسل الإشعارات.
{% endtab %}
{% endtabs %}

### Token

{% tabs %}
{% tab title="Description" %}
The Telegram token for your bot.
{% endtab %}

{% tab title="Values" %}
**Values:** string

**Default value:** YOURTOKEN
{% endtab %}

{% tab title="Name" %}
Parameter name in `config.js`: `TOKEN`
{% endtab %}
{% endtabs %}

### Chat ID

{% tabs %}
{% tab title="Description" %}
The Chat ID for your bot to send its messages to.

**Valid options:**

_**"12345"**_

A positive integer, to send messages directly to a telegram user. Use this method when you just want to receive notifications for your personal use.

To find your telegram id, send /start to @MyTelegramID\_bot and it will respond with your ID.

_**"-12345"**_

A negative integer, to send messages to a group chat.

The easiest way to obtain a groups id, is to open [https://web.telegram.org](https://web.telegram.org) login, and navigate to the group. Now pay attention to the URL, you should see something like [https://web.telegram.org/\#/im?p=g12345](https://web.telegram.org/#/im?p=g12345) - the number after the p=g part is the group id.

This must be listed in chat\_id with a - symbol in front, in this case "-12345"
{% endtab %}

{% tab title="Values" %}
**Values:** string

**Default value:** 123456789
{% endtab %}

{% tab title="Name" %}
Parameter name in `config.js`: `chat_id`
{% endtab %}
{% endtabs %}

### TG PL Only

{% tabs %}
{% tab title="Description" %}
When enabled notifications will be only sent for strategy sell orders.
{% endtab %}

{% tab title="Values" %}
**Values:** true or false

**Default value:** false
{% endtab %}

{% tab title="Name" %}
Parameter name in `config.js`: `TG_PL_ONLY`
{% endtab %}
{% endtabs %}

### Telegram Order Timeout

{% tabs %}
{% tab title="Description" %}
When set above 0, you'll receive a Telegram dialog to manually allow or deny every order Gunbot wants to place.

During the set amount of seconds you can choose to allow the order \(and it will immediately be placed\) or deny it. After the timeout passes without reply, the order will be placed at the exchange.
{% endtab %}

{% tab title="Values" %}
**Values:** numerical, represent time in seconds.

**Default value:** 0
{% endtab %}

{% tab title="Name" %}
Parameter name in `config.js`: `TG_PL_ONLY`
{% endtab %}
{% endtabs %}

### TG Test

{% tabs %}
{% tab title="Description" %}
Enable this to test if your Telegram bot is working.

A test message will be sent on the first round for each pair. Disable after verifying your bot works.
{% endtab %}

{% tab title="Values" %}
**Values:** true or false

**Default value:** false
{% endtab %}

{% tab title="Name" %}
Parameter name in `config.js`: `TG_TEST`
{% endtab %}
{% endtabs %}

