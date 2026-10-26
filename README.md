# نور – تطبيق أندرويد (تطوير محمد النبهان)

## أسهل طريقة: بناء APK من GitHub (بدون تثبيت أي شيء)
1. أنشئ حساباً على github.com ثم مستودعاً جديداً (Private يكفي).
2. ارفع كل محتويات هذا المجلد (بما فيها مجلد .github) إلى المستودع.
3. افتح تبويب Actions ثم Build APK ثم Run workflow.
4. بعد 5 – 10 دقائق افتح التشغيل الناجح ونزّل noor-apk من Artifacts، وفكّ الضغط.
5. انقل app-debug.apk إلى هاتفك وثبّته (اسمح بالتثبيت من مصدر غير معروف).

## على جهازك
تحتاج Node 20 وJava 17 وAndroid SDK:
    npm install && npx cap add android && npx cap sync android
    cd android && ./gradlew assembleDebug
الملف الناتج: android/app/build/outputs/apk/debug/app-debug.apk

## بعد التجربة
- الأيقونة: الافتراضية الآن. لتغييرها استخدم @capacitor/assets مع icon.png بحجم 1024.
- صوت الأذان في الإشعار: ضع ملفاً مرخصاً في android/app/src/main/res/raw ثم أضف sound في الإشعار.
- النشر في Google Play: يلزم توقيع release (AAB) بمفتاح خاص بك، وهذا غير الـ debug.
