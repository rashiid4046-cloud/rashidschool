# مدرسة المنيعي – الموهوبات (نسخة Netlify)

## هيكل المشروع
```
public/index.html              الواجهة (صفحة واحدة)
netlify/functions/api.mjs      الخادم: تسجيل الدخول، التقدم، إدارة الطالبات
netlify.toml                   إعدادات النشر
package.json                   الاعتماديات (@netlify/blobs)
```

## النشر (يجب استخدام Git أو CLI لأن الدوال تحتاج بناء، والسحب والإفلات لا يكفي)

### الطريقة 1: GitHub
1. ارفعي المجلد إلى مستودع GitHub.
2. في Netlify: Add new site → Import an existing project → اختاري المستودع.
3. اتركي الإعدادات كما هي (يقرأها Netlify من netlify.toml) ثم Deploy.

### الطريقة 2: سطر الأوامر
```
npm install
npx netlify login
npx netlify init        # ربط/إنشاء الموقع
npx netlify deploy --prod
```

## كلمة مرور المعلمة (مهم)
في Netlify: Site configuration → Environment variables → أضيفي
`TEACHER_PASSWORD` بقيمة كلمة مرور قوية، ثم أعيدي النشر.
(إن لم تُضبط، تكون القيمة الافتراضية 1234 وهي غير آمنة.)

## التشغيل محلياً
```
npm install
npx netlify dev
```
ثم افتحي http://localhost:8888

## أين تُحفظ البيانات؟
في Netlify Blobs (مخزن gifted-school، المفتاح roster) على الخادم، فتظهر لكل الأجهزة.
الشعار يُحفظ في متصفح الجهاز الذي رُفع منه فقط.
