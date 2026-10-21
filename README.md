# مهارة النحو والإعراب
### (Arabic Grammar & I'rab Skill)

<p align="center">
  <a href="https://github.com/specailm5/arabic-grammar-skill/blob/master/LICENSE"><img alt="License" src="https://img.shields.io/github/license/specailm5/arabic-grammar-skill?style=flat-square"></a>
  <a href="https://github.com/specailm5/arabic-grammar-skill/commits/master"><img alt="Last commit" src="https://img.shields.io/github/last-commit/specailm5/arabic-grammar-skill?style=flat-square"></a>
  <a href="https://specailm5.github.io/arabic-grammar-skill/"><img alt="Docs" src="https://img.shields.io/badge/docs-live-brightgreen?style=flat-square"></a>
  <img alt="Agent Skills" src="https://img.shields.io/badge/Agent%20Skills-compatible-5B21B6?style=flat-square">
</p>

**Arabic grammar skill for AI agents** — corrects Arabic grammar, explains the rule, parses the sentence, and produces a clear إعراب table: `إنّ الطالبُ` ← `إنّ الطالبَ`, `أكرمتُ المجتهداتَ` ← `أكرمتُ المجتهداتِ`. Works with Claude Code, Codex, Antigravity and VS Code agent harnesses.

🔗 **الموقع المرجعي (النحو والصرف والإعراب والنماذج): [specailm5.github.io/arabic-grammar-skill](https://specailm5.github.io/arabic-grammar-skill/)**

> مهارة برمجية ولغوية لنماذج الذكاء الاصطناعي والمحررات الذكية (Codex، Claude Code، Antigravity IDE، VS Code Agent Harness) لتصحيح النصوص العربية وشرح قواعدها وإعرابها، استناداً إلى **«جامع الدروس العربية»** لمصطفى الغلاييني، و**«النحو الوافي»** لعباس حسن.

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

<pre dir="rtl"><code>
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
</code></pre>

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

<table dir="rtl">
<thead>
<tr>
<th align="right">السؤال</th>
<th align="right">لماذا؟</th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>ما نوع النص؟</strong></td>
<td>فصيح/عامي/مترجم/أكاديمي/شعري</td>
</tr>
<tr>
<td><strong>ما المطلوب؟</strong></td>
<td>تصحيح/إعراب/شرح/تدقيق</td>
</tr>
<tr>
<td><strong>ما مستوى القارئ؟</strong></td>
<td>يحدد عمق الشرح</td>
</tr>
<tr>
<td><strong>تصحيح صامت أم مشروح؟</strong></td>
<td>يحدد شكل المخرج</td>
</tr>
<tr>
<td><strong>هل النص عاميّ مقصود؟</strong></td>
<td>لا تُحوّله إلى الفصحى</td>
</tr>
</tbody>
</table>

### مستويات الخطأ

<table dir="rtl">
<thead>
<tr>
<th align="right">المستوى</th>
<th align="right">مثال</th>
<th align="right">العلاج</th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>الإعراب</strong></td>
<td>نصب الفاعل</td>
<td>بيّن العامل والعلامة</td>
</tr>
<tr>
<td><strong>البناء</strong></td>
<td>إعراب الماضي</td>
<td>ذكّر أنه مبني</td>
</tr>
<tr>
<td><strong>المطابقة</strong></td>
<td>تأنيث الفعل مع مذكر</td>
<td>اضبط المطابقة</td>
</tr>
<tr>
<td><strong>الترتيب</strong></td>
<td>تقديم معمول على عامله</td>
<td>أعد الترتيب</td>
</tr>
<tr>
<td><strong>الحذف/الزيادة</strong></td>
<td>حذف المبتدأ</td>
<td>احذف/أضف</td>
</tr>
<tr>
<td><strong>الصرف</strong></td>
<td>همزة، جمع، تصغير</td>
<td>صحح البنية</td>
</tr>
<tr>
<td><strong>الإملاء/الترقيم</strong></td>
<td>همزة، فاصلة</td>
<td>صحح الرسم</td>
</tr>
</tbody>
</table>

### منهج الإعراب

<pre dir="rtl"><code>
① نوع الجملة  ② نوع الكلمة  ③ العامل
④ الموقع      ⑤ العلامة      ⑥ السبب
</code></pre>

### علامات الإعراب

<table dir="rtl">
<thead>
<tr>
<th align="right">الحالة</th>
<th align="right">الأصلية</th>
<th align="right">الفرعية</th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>رفع</strong></td>
<td>الضمة</td>
<td>الألف، الواو، ثبوت النون</td>
</tr>
<tr>
<td><strong>نصب</strong></td>
<td>الفتحة</td>
<td>الألف، الياء، الكسرة، حذف النون</td>
</tr>
<tr>
<td><strong>جر</strong></td>
<td>الكسرة</td>
<td>الياء، الفتحة</td>
</tr>
<tr>
<td><strong>جزم</strong></td>
<td>السكون</td>
<td>حذف حرف العلة، حذف النون</td>
</tr>
</tbody>
</table>

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

## 🤝 المساهمة

نرحب بالمساهمات التي تحسّن المادة أو التحرير أو التوثيق. اقرأ [CONTRIBUTING.md](CONTRIBUTING.md) قبل فتح طلب سحب، والتزم بـ[قواعد السلوك](CODE_OF_CONDUCT.md).

## 🛡️ الأمان

إن وجدت مشكلة أمنية، فلا تفتح قضية عامة؛ راجع [SECURITY.md](SECURITY.md).

## 📄 سجل التغييرات

راجع [CHANGELOG.md](CHANGELOG.md) لمعرفة ما أُضيف في كل إصدار.

## 📬 الدعم

للأسئلة والاقتراحات: [افتح قضية](https://github.com/specailm5/arabic-grammar-skill/issues).

---

## 📜 الترخيص (License)

هذه المهارة مفتوحة المصدر تحت رخصة [MIT](LICENSE)، ومتاحة للاستخدام الشخصي والتجاري والبحثي لدعم اللغة العربية.
