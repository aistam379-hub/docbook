# DocBook — نظام إدارة العيادة

تطبيق ويب (HTML/CSS/JS خالص، بلا بناء) لإدارة عيادة، عربيّ RTL، يعمل كـ PWA.

## البنية

| المسار | الوصف |
|--------|-------|
| `index.html` | صفحة الجذر — تحوّل إلى صفحة الدخول الموحّدة |
| `doctor/` | لوحة الطبيب + صفحة الدخول الموحّدة (`doctor/index.html`) |
| `nurse/` | لوحة الممرضة |
| `booking/` | صفحة حجز المواعيد للمرضى (عامّة) |
| `firestore.rules` | قواعد أمان Firestore (مرجع) |

## الدخول الموحّد

- صفحة دخول واحدة (`/` أو `/doctor/` أو `/nurse/`) عبر **حساب جوجل**.
- الدور يُحدَّد من البريد في `doctor/config.js` و `nurse/config.js` (`DOCBOOK_ROLES`).
- الطبيب → `/doctor/app.html` · الممرّضة → `/nurse/app.html` — تلقائيّاً.

## الإعداد (`config.js` — انسخه مطابقاً في `doctor/` و `nurse/` و `booking/`)

1. `FIREBASE_CONFIG` — من Firebase Console ← Project settings ← Web app.
2. `DOCBOOK_ROLES` — إيميلات غوغل للطبيب والممرّضة (نفسها في `firestore.rules`).
3. Firebase Console ← Authentication ← Authorized domains ← أضِف دومين النشر.

## النشر

انشر جذر المستودع كما هو (GitHub Pages / Netlify / Vercel / Firebase Hosting). لا خطوة بناء.
