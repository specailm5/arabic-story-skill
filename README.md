# مهارة كتابة القصة العربية
### (Arabic Story Skill — Story Craft + فصحى)

**Arabic story-writing skill for AI agents** — plans, structures and drafts authentic Arabic short stories: العقدة → الصراع → الحل, opening and ending, character and dialogue, then filters the prose through the anti-العَرَنْجِيَّة rules of `arabic-writing-skill` (`قام بزيارة` → `زار`). Works with Claude Code, Codex, Antigravity and VS Code agent harnesses.

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

| الدعامة | مضمونها |
| :--- | :--- |
| **العقدة** | اضطراب وحيرة + هدف؛ مأزقٌ لابدّ له من حلّ |
| **الصراع** | مواجهة قوتين: ضد الظروف، بين الشخصيات، داخل الشخصية |
| **الحل** | نتيجة الصراع؛ نهاية مفاجئة معقولة، بلا ذيل وبلا مصادفة ضخمة |

**فلتر اللسان — تعرج النص:**

| الأسلوب العرنجي الهجين ❌ | الصواب العربي الفصيح ✅ | التوجيه |
| :--- | :--- | :--- |
| كان يشعر بالحزن | أَحسَّ بغمٍّ / حَزِن | نبذ الفعل المساعد |
| تم إغلاق الدكان من قِبل البلدية | أغلقت البلديةُ الدكانَ | امتناع المبني للمجهول إذا عُلم الفاعل |
| قام بإغلاق الصحيفة | أطبق الصحيفة | الاشتقاق المباشر |
| لعب دوراً مهماً في | كان قطبَ الرحى | استعارة مسطَّحة مستوردة |
| على صعيد آخر | وفي شأنٍ آخر | نبذ `على صعيد` |
| أريد أن أعرف السبب فقط | ما أريد إلا أن أعرف السبب | أسلوب الحصر والقصر |

---

## 📚 المراجع والاعتماد

* كتاب **«فن كتابة القصة»**، تأليف **حسين القباني** (الدار المصرية للتأليف والترجمة). نسخة مصوّرة مرفوعة على **موقع أرشيف الإنترنت (Internet Archive)** — «مكتبتي الخاصة». النصّ المفرَّغ آليًّا في `source/reference.txt`.
* **مهارة الكتابة العربية الفصيحة ونبذ العَرَنْجِيَّة** (`arabic-writing-skill`)، مستخلصة من كتاب «العَرَنْجِيَّة: بلغات أعجمية وألسن عربية» لأحمد الغامدي.

> **المصدر الأساس** لهذه المهارة هو كتاب «فن كتابة القصة» لحسين القباني، وهو الكتاب المرفوع على موقع الأرشيف المذكور.

---

## 📜 الترخيص (License)

هذه المهارة مفتوحة المصدر ومتاحة للاستخدام الشخصي والتجاري والبحثي لدعم الكتابة القصصية بالعربية الفصيحة.
