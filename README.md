# مهارة النحو والإعراب
### (Arabic Grammar & I'rab Skill)

**Arabic grammar skill for AI agents** — corrects Arabic grammar, explains the rule, parses the sentence, and produces a clear إعراب table: `إنّ الطالبُ` ← `إنّ الطالبَ`, `أكرمتُ المجتهداتَ` ← `أكرمتُ المجتهداتِ`. Works with Claude Code, Codex, Antigravity and VS Code agent harnesses.

🔗 **الموقع المرجعي (النحو والصرف والإعراب والنماذج): [specailm5.github.io/arabic-grammar-skill](https://specailm5.github.io/arabic-grammar-skill/)**

> مهارة برمجية ولغوية لنماذج الذكاء الاصطناعي والمحررات الذكية (Codex، Claude Code، Antigravity IDE، VS Code Agent Harness) لتصحيح النصوص العربية وشرح قواعدها وإعرابها، استناداً إلى **«جامع الدروس العربية»** لمصطفى الغلاييني، و**«النحو الوافي»** لعباس حسن.

---

## 🎬 عرض توضيحي (Demo)

| قبل ❌ | بعد ✅ | التوجيه |
| :--- | :--- | :--- |
| «إنّ الطالبُ مجتهدٌ» | «إنّ الطالبَ مجتهدٌ» | «إنّ» تنصب الاسم وترفع الخبر |
| «كان الطالبُ مجتهدٌ» | «كان الطالبُ مجتهدًا» | «كان» ترفع الاسم وتنصب الخبر |
| «أكرمتُ المجتهداتَ» | «أكرمتُ المجتهداتِ» | جمع المؤنث السالم ينصب بالكسرة |
| «مررتُ بأحمدٍ» | «مررتُ بأحمدَ» | الممنوع من الصرف يُجر بالفتحة |
| «لن يكتبون» | «لن يكتبوا» | الأفعال الخمسة تنصب بحذف النون |
| «جاء قاضي» | «جاء قاضٍ» | المنقوص تُحذف ياؤه في الرفع والجر |

---

## 📖 ما هي المهارة؟

**النحو** هو ضبط مواقع الكلمات في الجملة، و**الإعراب** هو بيان ذلك الموقع وعامله وعلامته. كثير من النصوص العربية «مستقيمة المعنى، مضطربة الإعراب»؛ فتجد الفاعل منصوباً، والمفعول مرفوعاً، وجمع المؤنث السالم مجروراً بالكسرة، والممنوع من الصرف منوّناً.

تُمكِّنُ هذه المهارةُ الوكيلَ الذكيَّ من:

1. **تشخيص الخطأ** وتصنيفه: إعراب، بناء، مطابقة، ترتيب، حذف/زيادة، صرف، إملاء، ترقيم.
2. **تصحيحه بأقل تعديل**، مع الحفاظ على معنى الكاتب وصوته.
3. **شرح القاعدة** من الكتاب، لا من الذاكرة.
4. **إعراب الجملة** بمنهج من ست خطوات، لا بسرد علامات.
5. **التنبيه إلى الخلاف** في المسائل النحوية، بلا جزم.

**القواعد الأربع:**
> **المعنى أولاً. أقل تعديل. كل تعديل بسببه. لا حكم بلا كتاب.**

---

## 📂 بنية المهارة ومكوناتها

```
arabic-grammar-skill/
│
├── skills/arabic-grammar-skill/          # المهارة (تركيب Agent Skills القياسي)
│   ├── SKILL.md                          # الدليل الأساسي: التشخيص والتصحيح والإعراب
│   ├── references/                       # المراجع التفصيلية
│   │   ├── nahw.md                       # الجملة والمواقع الإعرابية
│   │   ├── sarf.md                       # الصرف والأوزان والمشتقات
│   │   ├── common_errors.md              # ٥٠ خطأً شائعاً
│   │   ├── irab_method.md                # منهج الإعراب
│   │   └── punctuation.md                # الإملاء والترقيم
│   └── examples/                         # دراسات الحالة والنماذج
│       ├── before_after_grammar.md       # نماذج قبل/بعد
│       └── irab_examples.md              # نماذج إعرابية
│
├── docs/                                 # الموقع المرجعي (GitHub Pages)
│
├── .agents/skills/arabic-grammar-skill/  # مسار Codex و Antigravity
│
└── .claude/skills/arabic-grammar-skill/  # مسار Claude Code
```

---

## 🚀 طرق التثبيت والاستخدام (Installation Guide)

تُثبَّتُ المهارةُ إما في مشروعٍ بعينه (**محلياً**)، وإما **عامةً (Global)** لتعمل في كافة المشاريع.

---

### أولاً: التثبيت بأمر واحد عبر `npx` (الطريقة الأسرع — موصى به)

```bash
npx skills add specailm5/arabic-grammar-skill -g -y
```

ولاختيار بيئات بعينها أو التثبيت داخل مشروع محدد:

```bash
npx skills add specailm5/arabic-grammar-skill -a claude-code -a codex
npx skills add specailm5/arabic-grammar-skill --skill arabic-grammar-skill -g -y
```

---

### ثانياً: التثبيت العام لبيئة Claude Code و Codex و Antigravity (يدوياً)

#### لنظام Windows (PowerShell):

```powershell
# مصدر المهارة داخل المستودع
$src = "skills\arabic-grammar-skill"

# 1. تثبيت لبيئة Claude Code
New-Item -ItemType Directory -Force -Path "$env:USERPROFILE\.claude\skills\arabic-grammar-skill"
Copy-Item -Recurse -Force "$src\*" "$env:USERPROFILE\.claude\skills\arabic-grammar-skill\"

# 2. تثبيت لبيئة Codex و Agent Skills العامة
New-Item -ItemType Directory -Force -Path "$env:USERPROFILE\.agents\skills\arabic-grammar-skill"
Copy-Item -Recurse -Force "$src\*" "$env:USERPROFILE\.agents\skills\arabic-grammar-skill\"

# 3. تثبيت لبيئة Google Antigravity / Gemini
New-Item -ItemType Directory -Force -Path "$env:USERPROFILE\.gemini\config\skills\arabic-grammar-skill"
Copy-Item -Recurse -Force "$src\*" "$env:USERPROFILE\.gemini\config\skills\arabic-grammar-skill\"
```

#### لنظام macOS / Linux (Bash):

```bash
src=skills/arabic-grammar-skill

# 1. لبيئة Claude Code
mkdir -p ~/.claude/skills/arabic-grammar-skill
cp -r "$src/." ~/.claude/skills/arabic-grammar-skill/

# 2. لبيئة Codex و Agent Harness
mkdir -p ~/.agents/skills/arabic-grammar-skill
cp -r "$src/." ~/.agents/skills/arabic-grammar-skill/

# 3. لبيئة Antigravity / Gemini
mkdir -p ~/.gemini/config/skills/arabic-grammar-skill
cp -r "$src/." ~/.gemini/config/skills/arabic-grammar-skill/
```

---

### ثالثاً: التثبيت المحلي داخل مشروع محدد (VS Code Workspace Harness)

إذا أردت حصر المهارة داخل مستودع أو مجلد عمل واحد في VS Code:

```powershell
# داخل مجلد مشروعك الحالي:
New-Item -ItemType Directory -Force -Path ".agents\skills\arabic-grammar-skill"
Copy-Item -Recurse -Force "path\to\skills\arabic-grammar-skill\*" ".agents\skills\arabic-grammar-skill\"
```

بمجرد فتح المشروع في **VS Code** أو تشغيل `Claude Code` / `Codex`، يكتشفُ الوكيلُ المهارةَ ويقرؤها من تلقاء نفسه عند صياغة أي نص باللغة العربية.

---

### رابعاً: الاستخدام اليدوي (Direct System Prompt / Custom Instructions)

إذا كنت تستخدم واجهات الويب (مثل ChatGPT أو Claude أو Gemini) مباشرة دون بيئة برمجية:

* افتح ملف [`skills/arabic-grammar-skill/SKILL.md`](skills/arabic-grammar-skill/SKILL.md) وانسخ محتواه وضعه في خانة **التعليمات المخصصة (Custom Instructions)** أو **System Prompt**.

---

## ⚡ كيف تعمل المهارة؟

### خمسة أسئلة قبل التصحيح

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

### منهج الإعراب

```
① نوع الجملة  ② نوع الكلمة  ③ العامل
④ الموقع      ⑤ العلامة      ⑥ السبب
```

### علامات الإعراب

| الحالة | الأصلية | الفرعية |
| :--- | :--- | :--- |
| **رفع** | الضمة | الألف، الواو، ثبوت النون |
| **نصب** | الفتحة | الألف، الياء، الكسرة، حذف النون |
| **جر** | الكسرة | الياء، الفتحة |
| **جزم** | السكون | حذف حرف العلة، حذف النون |

---

## 📚 المراجع والاعتماد

* **«جامع الدروس العربية»** — مصطفى الغلاييني — ثلاثة أجزاء:
  <https://archive.org/details/g_doros>
* **«النحو الوافي»** — عباس حسن — دار المعارف، القاهرة — أربعة أجزاء:
  * <https://archive.org/details/Heliopolis1957_gmail_1_20181124_0052>
  * <https://archive.org/details/Heliopolis1957_gmail_2_20181124>
  * <https://archive.org/details/Heliopolis1957_gmail_3_20181124_0105>
  * <https://archive.org/details/Heliopolis1957_gmail_4_201811>

> **إقرار بالفضل:** هذه المهارة صياغة تعليمية مستقلة لمبادئ هذين الكتابين، مع نقل قواعد وأمثلة بإسنادها إلى أبوابها. ولا يتضمّن المستودع نسخاً كاملة من الكتابين، ولا يُغني عن الرجوع إلى الأصل.

---

## ⚠️ حدود المسؤولية

- المهارة **لتصحيح النحو وشرحه**، لا لتدريس النحو كاملاً.
- لا تُفتى في القراءات، ولا تُحسم المسائل الخلافية بلا مصدر.
- بعض الأمثلة خلافية؛ يُذكر الخلاف ولا يُجزم.
- المستخدم مسؤول عن مراجعة النص النهائي.
- لا تُستخدم المهارة لتغيير معنى النص أو فرض الفصحى على عامي مقصود.

---

## 📜 الترخيص (License)

هذه المهارة مفتوحة المصدر ومتاحة للاستخدام الشخصي والتجاري والبحثي لدعم اللغة العربية.
