# مهارة كتابة القصة العربية
### (Arabic Story Skill — Story Craft + فصحى)

**Arabic story-writing skill for AI agents** — plans, structures and drafts authentic Arabic short stories: العقدة ← الصراع ← الحل, opening and ending, character and dialogue, then filters the prose through the anti-العَرَنْجِيَّة rules of `arabic-writing-skill` (`قام بزيارة` ← `زار`). Works with Claude Code, Codex, Antigravity and VS Code agent harnesses.

🔗 **الموقع المرجعي (الدليل والهيكل والشخصية والحوار والنماذج): [specailm5.github.io/arabic-story-skill](https://specailm5.github.io/arabic-story-skill/)**

> مهارة برمجية وأدبية لوكلاء الذكاء الاصطناعي لكتابة **القصة العربية القصيرة** على أصولها الفنية: العقدة والصراع والحل، والبداية والنهاية، والشخصية بأبعادها الثلاثة، والحوار، والأسلوب، والترقيم؛ مستندةً إلى كتاب **«فن كتابة القصة»** للأستاذ **حسين القباني** (الدار المصرية للتأليف والترجمة)، ومسنودة بأصول **مهارة الكتابة العربية الفصيحة ونبذ العَرَنْجِيَّة**.

---

## 📖 ما هي المهارة؟

مهارة تُعلِّم الوكيل الذكي **صنعة القصة** (كيف تُبنى) و**لسانها** (كيف تُصاغ عربيةً فصيحةً)، فتجمع بين أمرين لا يتفارقان:

1. **الهيكل الفني**: العقدة (المأزق والهدف)، الصراع (ضد الظروف، بين الشخصيات، داخل الشخصية)، الحل (النهاية المفاجئة المعقولة)، ووحدة الزمان والمكان، والتشويق، والمصادفة المعقولة.
2. **فلتر اللسان**: تمرير السرد والحوار على قواعد `arabic-writing-skill` لنبذ التراكيب الإفرنجية المنقولة؛ فتستقيم الجملة عربيةً في بنائها وروحها لا في إعرابها وحده.

---

## 📂 بنية المهارة ومكوناتها

```
arabic-story-skill/
│
├── skills/arabic-story-skill/            # المهارة (تركيب Agent Skills القياسي)
│   ├── SKILL.md                          # الدليل الأساسي للمهارة (منهج كتابة القصة كاملاً)
│   ├── references/                       # الملاحق المرجعية التفصيلية
│   │   ├── story_structure.md            # الهيكل والعناصر: العقدة والصراع والحل والبداية والنهاية
│   │   ├── character_and_dialogue.md     # الشخصية وأبعادها الثلاثة وأغراض الحوار وأنواع فقراته
│   │   └── style_and_language.md         # الأسلوب والترقيم وفلتر العرنجية المفصَّل
│   └── examples/                         # دراسات الحالة والنماذج التطبيقية
│       └── before_after_stories.md       # من خبر/حكمة/عبارة إلى قصة، ونص قصصي قبل وبعد التحرير
│
├── docs/                                 # الموقع المرجعي الإلكتروني (GitHub Pages)
│
├── .agents/skills/arabic-story-skill/    # مسار الاكتشاف التلقائي لبيئات Codex و Antigravity
│
└── .claude/skills/arabic-story-skill/    # مسار الاكتشاف التلقائي لبيئة Claude Code
```

---

## 🚀 طرق التثبيت والاستخدام (Installation Guide)

### أولاً: التثبيت بأمر واحد عبر `npx` (الطريقة الأسرع — موصى به)

```bash
npx skills add specailm5/arabic-story-skill -g -y
```

ولاختيار بيئات بعينها أو التثبيت داخل مشروع محدد:

```bash
npx skills add specailm5/arabic-story-skill -a claude-code -a codex
npx skills add specailm5/arabic-story-skill --skill arabic-story-skill -g -y
```

### ثانياً: التثبيت العام (يدوياً)

#### لنظام Windows (PowerShell):
```powershell
$src = "skills\arabic-story-skill"

# 1. Claude Code
New-Item -ItemType Directory -Force -Path "$env:USERPROFILE\.claude\skills\arabic-story-skill"
Copy-Item -Recurse -Force "$src\*" "$env:USERPROFILE\.claude\skills\arabic-story-skill\"

# 2. Codex / Agent Skills العامة
New-Item -ItemType Directory -Force -Path "$env:USERPROFILE\.agents\skills\arabic-story-skill"
Copy-Item -Recurse -Force "$src\*" "$env:USERPROFILE\.agents\skills\arabic-story-skill\"

# 3. Google Antigravity / Gemini
New-Item -ItemType Directory -Force -Path "$env:USERPROFILE\.gemini\config\skills\arabic-story-skill"
Copy-Item -Recurse -Force "$src\*" "$env:USERPROFILE\.gemini\config\skills\arabic-story-skill\"
```

#### لنظام macOS / Linux (Bash):
```bash
src=skills/arabic-story-skill
mkdir -p ~/.claude/skills/arabic-story-skill && cp -r "$src/." ~/.claude/skills/arabic-story-skill/
mkdir -p ~/.agents/skills/arabic-story-skill && cp -r "$src/." ~/.agents/skills/arabic-story-skill/
mkdir -p ~/.gemini/config/skills/arabic-story-skill && cp -r "$src/." ~/.gemini/config/skills/arabic-story-skill/
```

### ثالثاً: التثبيت المحلي داخل مشروع محدد (VS Code Workspace Harness)

انسخ مجلد `skills/arabic-story-skill` داخل مجلد `.agents/skills/` أو `.claude/skills/` في جذر مشروعك، فيكتشف الوكيلُ المهارةَ عند كتابة أي قصة.

---

## ⚡ كيف تعمل المهارة؟ (أوامر سريعة)

**هيكل القصة — الدعائم الثلاث:**

<table dir="rtl">
<thead>
<tr>
<th align="right">الدعامة</th>
<th align="right">مضمونها</th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>العقدة</strong></td>
<td>اضطراب وحيرة + هدف؛ مأزقٌ لابدّ له من حلّ</td>
</tr>
<tr>
<td><strong>الصراع</strong></td>
<td>مواجهة قوتين: ضد الظروف، بين الشخصيات، داخل الشخصية</td>
</tr>
<tr>
<td><strong>الحل</strong></td>
<td>نتيجة الصراع؛ نهاية مفاجئة معقولة، بلا ذيل وبلا مصادفة ضخمة</td>
</tr>
</tbody>
</table>

**فلتر اللسان — تعرج النص:**

<table dir="rtl">
<thead>
<tr>
<th align="right">الأسلوب العرنجي الهجين ❌</th>
<th align="right">الصواب العربي الفصيح ✅</th>
<th align="right">التوجيه</th>
</tr>
</thead>
<tbody>
<tr>
<td>كان يشعر بالحزن</td>
<td>أَحسَّ بغمٍّ / حَزِن</td>
<td>نبذ الفعل المساعد</td>
</tr>
<tr>
<td>تم إغلاق الدكان من قِبل البلدية</td>
<td>أغلقت البلديةُ الدكانَ</td>
<td>امتناع المبني للمجهول إذا عُلم الفاعل</td>
</tr>
<tr>
<td>قام بإغلاق الصحيفة</td>
<td>أطبق الصحيفة</td>
<td>الاشتقاق المباشر</td>
</tr>
<tr>
<td>لعب دوراً مهماً في</td>
<td>كان قطبَ الرحى</td>
<td>استعارة مسطَّحة مستوردة</td>
</tr>
<tr>
<td>على صعيد آخر</td>
<td>وفي شأنٍ آخر</td>
<td>نبذ <code>على صعيد</code></td>
</tr>
<tr>
<td>أريد أن أعرف السبب فقط</td>
<td>ما أريد إلا أن أعرف السبب</td>
<td>أسلوب الحصر والقصر</td>
</tr>
</tbody>
</table>

---

## 📚 المراجع والاعتماد

* كتاب **«فن كتابة القصة»**، تأليف **حسين القباني** (الدار المصرية للتأليف والترجمة). نسخة مصوّرة مرفوعة على **موقع أرشيف الإنترنت (Internet Archive)** — «مكتبتي الخاصة». النصّ المفرَّغ آليًّا في `source/reference.txt`.
* **مهارة الكتابة العربية الفصيحة ونبذ العَرَنْجِيَّة** (`arabic-writing-skill`)، مستخلصة من كتاب «العَرَنْجِيَّة: بلغات أعجمية وألسن عربية» لأحمد الغامدي.

> **المصدر الأساس** لهذه المهارة هو كتاب «فن كتابة القصة» لحسين القباني، وهو الكتاب المرفوع على موقع الأرشيف المذكور.

---

## 📜 الترخيص (License)

هذه المهارة مفتوحة المصدر ومتاحة للاستخدام الشخصي والتجاري والبحثي لدعم الكتابة القصصية بالعربية الفصيحة.
