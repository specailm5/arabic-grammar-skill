# مهارة النحو والإعراب
### (Arabic Grammar & I'rab Skill)

**Arabic grammar skill for AI agents** — diagnoses the sentence, classifies the error, applies the smallest correct edit, explains the rule from the classical and modern grammar books, and produces a clear إعراب table when requested. Covers the nominal and verbal sentence, the case system, the fourteen منصوبات, الصرف, الهمزات, punctuation and the common modern errors. Works with Claude Code, Codex, Antigravity and VS Code agent harnesses.

🔗 **الموقع المرجعي: [specailm5.github.io/arabic-grammar-skill](https://specailm5.github.io/arabic-grammar-skill/)**

> مهارة برمجية لتصحيح النص العربي وشرح قواعده وإعرابه، مبنية على **«جامع الدروس العربية»** لمصطفى الغلاييني، و**«النحو الوافي»** لعباس حسن. لا تصحيح بلا سبب، ولا إعراب بلا منهج، ولا حكم بلا كتاب.

---

## 📖 ما هي المهارة؟

أربع وظائف:

1. **تصحيح النحو:** تشخيص الخطأ، تعديله، وشرح السبب.
2. **الإعراب:** منهج من ست خطوات، وجدول واضح لكل كلمة.
3. **شرح القاعدة:** من المستوى المبتدئ إلى المتخصص.
4. **تدقيق لغوي:** إعراب + صرف + إملاء + ترقيم + مطابقة.

**القواعد الأربع:**
> **المعنى أولاً. أقل تعديل. كل تعديل بسببه. لا حكم بلا كتاب.**

---

## 📂 بنية المهارة

```
arabic-grammar-skill/
│
├── skills/arabic-grammar-skill/
│   ├── SKILL.md
│   ├── references/
│   │   ├── nahw.md              # الجملة والمواقع الإعرابية
│   │   ├── sarf.md              # الصرف والأوزان والمشتقات
│   │   ├── common_errors.md     # ٥٠ خطأً شائعاً
│   │   ├── irab_method.md       # منهج الإعراب
│   │   └── punctuation.md       # الإملاء والترقيم
│   └── examples/
│       ├── before_after_grammar.md
│       └── irab_examples.md
│
├── docs/                        # الموقع المرجعي
├── .agents/skills/arabic-grammar-skill/
└── .claude/skills/arabic-grammar-skill/
```

---

## 🚀 التثبيت

### بأمر واحد

```bash
npx skills add specailm5/arabic-grammar-skill -g -y
```

أو لبيئات محددة:

```bash
npx skills add specailm5/arabic-grammar-skill -a claude-code -a codex
```

### يدوياً (Windows)

```powershell
$src = "skills\arabic-grammar-skill"

New-Item -ItemType Directory -Force -Path "$env:USERPROFILE\.claude\skills\arabic-grammar-skill"
Copy-Item -Recurse -Force "$src\*" "$env:USERPROFILE\.claude\skills\arabic-grammar-skill\"

New-Item -ItemType Directory -Force -Path "$env:USERPROFILE\.agents\skills\arabic-grammar-skill"
Copy-Item -Recurse -Force "$src\*" "$env:USERPROFILE\.agents\skills\arabic-grammar-skill\"

New-Item -ItemType Directory -Force -Path "$env:USERPROFILE\.gemini\config\skills\arabic-grammar-skill"
Copy-Item -Recurse -Force "$src\*" "$env:USERPROFILE\.gemini\config\skills\arabic-grammar-skill\"
```

---

## ⚡ كيف تعمل؟

### خمسة أسئلة

| السؤال | لماذا؟ |
| :--- | :--- |
| **ما نوع النص؟** | فصيح/عامي/مترجم/أكاديمي/شعري |
| **ما المطلوب؟** | تصحيح/إعراب/شرح/تدقيق |
| **ما مستوى القارئ؟** | يحدد عمق الشرح |
| **تصحيح صامت أم مشروح؟** | يحدد شكل المخرج |
| **هل النص عاميّ مقصود؟** | لا تُحوّله إلى الفصحى |

### مستويات الخطأ

| المستوى | مثال | العلاج |
| :--- | :--- | :--- |
| **الإعراب** | نصب الفاعل | بيّن العامل والعلامة |
| **البناء** | إعراب الماضي | ذكّر أنه مبني |
| **المطابقة** | تأنيث الفعل مع مذكر | اضبط المطابقة |
| **الترتيب** | تقديم معمول على عامله | أعد الترتيب |
| **الحذف/الزيادة** | حذف المبتدأ | احذف/أضف |
| **الصرف** | همزة، جمع، تصغير | صحح البنية |
| **الإملاء/الترقيم** | همزة، فاصلة | صحح الرسم |

### علامات الإعراب

| الحالة | الأصلية | الفرعية |
| :--- | :--- | :--- |
| **رفع** | الضمة | الألف، الواو، ثبوت النون |
| **نصب** | الفتحة | الألف، الياء، الكسرة، حذف النون |
| **جر** | الكسرة | الياء، الفتحة |
| **جزم** | السكون | حذف حرف العلة، حذف النون |

### أمثلة سريعة

| قبل | بعد | السبب |
| :--- | :--- | :--- |
| «إنّ الطالبُ» | «إنّ الطالبَ» | اسم إنّ منصوب |
| «كان الطالبُ مجتهدٌ» | «كان الطالبُ مجتهدًا» | خبر كان منصوب |
| «أكرمتُ المجتهداتَ» | «أكرمتُ المجتهداتِ» | جمع مؤنث سالم |
| «مررتُ بأحمدٍ» | «مررتُ بأحمدَ» | ممنوع من الصرف |
| «لن يكتبون» | «لن يكتبوا» | حذف النون |
| «جاء قاضي» | «جاء قاضٍ» | المنقوص |
| «ذهبت بفاطمة» | «ذهب بفاطمة» | نائب الفاعل المجرور |

---

## 📚 المصادر

1. **«جامع الدروس العربية»** — مصطفى الغلاييني — ثلاثة أجزاء:
   <https://archive.org/details/g_doros>
2. **«النحو الوافي»** — عباس حسن — دار المعارف، القاهرة — أربعة أجزاء:
   - <https://archive.org/details/Heliopolis1957_gmail_1_20181124_0052>
   - <https://archive.org/details/Heliopolis1957_gmail_2_20181124>
   - <https://archive.org/details/Heliopolis1957_gmail_3_20181124_0105>
   - <https://archive.org/details/Heliopolis1957_gmail_4_201811>

> **إقرار بالفضل:** هذه المهارة صياغة تعليمية مستقلة لمبادئ هذين الكتابين، مع نقل قواعد وأمثلة بإسنادها إلى أبوابها. ولا يتضمّن المستودع نسخاً كاملة من الكتابين، ولا يُغني عن الرجوع إلى الأصل.

---

## ⚠️ حدود المسؤولية

- المهارة **لتصحيح النحو وشرحه**، لا لتدريس النحو كاملاً.
- لا تُفتى في القراءات، ولا تُحسم المسائل الخلافية بلا مصدر.
- بعض الأمثلة خلافية؛ يُذكر الخلاف ولا يُجزم.
- المستخدم مسؤول عن مراجعة النص النهائي.
- لا تُستخدم المهارة لتغيير معنى النص أو فرض الفصحى على عامي مقصود.

---

## 📜 الترخيص

هذه المهارة مفتوحة المصدر ومتاحة للاستخدام الشخصي والتجاري والبحثي لدعم اللغة العربية.
