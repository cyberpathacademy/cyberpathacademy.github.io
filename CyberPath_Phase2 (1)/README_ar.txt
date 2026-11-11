شرح مشروع CyberPath Academy - Phase 2 (HTML + CSS + JavaScript)
================================================================
الاسم: Bahaa Hamayel - 20258293

1) كيف تشغّله
-------------
- فك الضغط عن المجلد cyberpath، وافتح index.html بالمتصفح. كل الصفحات مربوطة بالقائمة في الأعلى.
- لا تنقل صفحة لوحدها: الصفحات تحتاج مجلد images (والصفحة Resources تحتاج مجلد downloads).

2) الملفات (12 صفحة)
--------------------
كل صفحة فيها كل شي داخلها: HTML + CSS داخل <style> + JavaScript داخل <script> (مثل أمثلة الدكتورة). ما في ملفات CSS أو JS خارجية.

index.html .......... Home          (ترحيب حسب الوقت + التاريخ + نصائح)
courses.html ........ Courses       (6 كورسات)
course-details.html . Course Details (تفاصيل الكورس المختار)
tutorials.html ...... Tutorials     (4 شروحات خطوة بخطوة)
practice-labs.html .. Practice Labs (3 مختبرات)
challenges.html ..... Challenges    (اختبار 5 أسئلة)
resources.html ...... Resources     (مصطلحات + روابط + تحميل + نصائح)
blog.html ........... Blog & News   (4 مقالات)
about.html .......... About Us
contact.html ........ Contact Us    (فورم)
signup.html ......... Sign Up       (فورم)
login.html .......... Login         (فورم)
images/ ............. الصور
downloads/ .......... ملف الـ checklist للتحميل

3) CSS (داخل <style> في أول كل صفحة)
-----------------------------------
أنواع الـ selectors (نفس اللي أخذتوه):
* { }            لكل العناصر: نصفّر margin و padding.
p { } h1 { }     عنصر: ننسق كل الفقرات والعناوين.
#header { }      id: لعنصر واحد (الهيدر، اللوقو، القائمة، الفوتر).
.card { }        class: لعدة عناصر (.card .button .box .field ...).
#menu a { }      الروابط داخل القائمة فقط.
.card img { }    الصور داخل البطاقة فقط.
#menu a:hover { } لما نمرر الماوس على الرابط يتغير لونه.

أهم الخصائص:
- background-color / color: الألوان من Phase 1: كحلي #112B50 (هيدر وفوتر)، أزرق #1585C1 (أزرار)، خلفية #EEF3FA، بطاقات بيضاء.
- font-family: Verdana, Arial.
- display: flex : ترتيب العناصر بجانب بعض (القائمة والبطاقات)، و flex-wrap: wrap تنزل لسطر جديد لو الشاشة صغيرة.
- border-radius: حواف مدورة. padding: مسافة داخلية. margin: مسافة خارجية.
- max-width + margin: 0 auto: المحتوى في النص بعرض محدد.
- display: none في .hidden-box: الصندوق مخفي لين نضغط الزر.

4) JavaScript: شو كل دالة تسوي
------------------------------
index.html:
- showGreeting(): تقرأ الساعة بـ getHours() وبـ if/else if تكتب Good morning / afternoon / evening، وتعرض التاريخ.
- nextTip(): array فيها نصائح، و tipNumber يزيد كل ضغطة ويرجع للصفر بعد آخر نصيحة.

course-details.html:
- المصفوفة courses: كل كورس object فيه title و image و objectives و topics (مثل الـ object في مثال الـ chatbot).
- الرابط من صفحة Courses مثل course-details.html#2، والرقم نقرأه من location.hash.substring(1).
- loadCourse(): تعبي العنوان والصورة والقوائم بـ createElement و appendChild (نفس الـ chatbot).
- startCourse(): alert ثم window.location.href تنقلك لصفحة Tutorials.

tutorials / practice-labs / blog / about:
- toggle(id): تظهر أو تخفي صندوق (display = "block" أو "none").

practice-labs.html:
- checkPassword(): loop تدور على رقم في الكلمة، وتحسب نقاط (طول 8 فأكثر، طول 12 فأكثر، حروف كبيرة وصغيرة، رقم) وتعرض Weak / Medium / Strong بلون مختلف.
  (pw !== pw.toLowerCase() معناها فيه حرف كبير، و pw !== pw.toUpperCase() معناها فيه حرف صغير.)
- checkLink(): تفحص هل العنوان يبدأ بـ https:// أو http:// باستخدام indexOf.

challenges.html:
- getAnswer(name): تدور على الراديو المختار بـ loop.
- حدث submit للفورم مع event.preventDefault() (نفس مثال Form Submission)، تحسب الدرجة وتعرض ملاحظة لكل سؤال، وتظهر صورة الكأس لو الدرجة 4 أو 5.

resources.html:
- filterTerms(): loop على كل المصطلحات، وتخفي اللي ما يحتوي النص المكتوب.

contact / signup / login:
- isValidEmail(email): تتأكد إن الإيميل فيه @ ونقطة.
- تحقق من الحقول الفاضية وطول الباسوورد (8 فأكثر) وتطابق كلمتي المرور في Sign Up.
- Sign Up بعد النجاح: alert ثم login.html. Login بعد النجاح: alert ثم index.html.
- في Login: Show password يغير type بين password و text.
- هذا demo: ما في سيرفر، فالحساب ما ينحفظ (مثل Phase 1: demo account).

5) أشياء لازم تنتبه لها
------------------------
- الصور placeholders: بدلها بصورك بنفس الأسماء (png) داخل مجلد images.
- اسمك ورقمك الجامعي موجودين في فوتر كل الصفحات.
- القائمة العلوية فيها كل الصفحات (11 رابط). صفحة Course Details تفتح من صفحة Courses.
- لأن الـ CSS داخل كل صفحة، أي تعديل على التصميم لازم تعمله في الصفحات الـ 12.

6) أسئلة محتملة في الـ Viva (Phase 3)
-------------------------------------
- شو الفرق بين id و class؟ الـ id لعنصر واحد (#header)، والـ class لعدة عناصر (.card).
- كيف تعمل القائمة بجانب بعض؟ display: flex على #header.
- كيف يعرف JavaScript العنصر؟ document.getElementById("اسم الـ id").
- شو يعمل event.preventDefault()؟ يمنع الفورم من إعادة تحميل الصفحة، فنتحكم بالنتيجة بالـ JavaScript.
- كيف تغيّر الصفحة محتواها؟ نغيّر textContent أو style.display أو ننشئ عناصر بـ createElement.
- كيف تعرف صفحة التفاصيل أي كورس تعرض؟ من الرقم بعد # في الرابط، نقرأه من location.hash.
