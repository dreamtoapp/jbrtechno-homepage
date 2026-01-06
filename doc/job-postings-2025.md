# Job Postings Specification - 2025

## Implementation Guide

This document specifies three new job positions to be added to the codebase. Each position follows the `Position` interface structure defined in `helpers/extractMetrics.ts`.

### Position Interface Structure:

```typescript
interface Position {
  title: string; // Arabic title
  titleEn: string; // English title
  count: number; // Number of positions
  salaryMin: number; // Minimum salary (0 if not specified)
  salaryMax: number; // Maximum salary (0 if not specified)
  phase: number; // 0=Leadership, 1=Technical, 2=Content, 3=Operations, 4=Sales
  requirements: string[]; // Arabic requirements array
  requirementsEn: string[]; // English requirements array
  employmentType?: 'full-time' | 'project-based'; // Optional
  filledBy?: string; // Optional - leave undefined for new positions
}
```

### Requirements Format:

- **Regular items**: Plain strings
- **Section headers**: `'--- Section Name ---'`
- **Empty lines**: `''` (empty string for spacing between sections)
- **Bonus items**: `'⭐ Item text'` (star emoji prefix for nice-to-have items)

### Phase Mapping:

- **Phase 0**: Leadership & Executive
- **Phase 1**: Technical Team
- **Phase 2**: Content Team
- **Phase 3**: Operations & Support
- **Phase 4**: Sales & Marketing

### How to Implement:

1. Copy each position object from the sections below
2. Add to `helpers/extractMetrics.ts` in the `getTeamPositions()` function
3. Place in the appropriate section based on `phase` value
4. Requirements arrays can be copied directly as-is

---

## Position 1: Account Manager | مدير حسابات

### Metadata

- **title**: `'مدير حسابات'`
- **titleEn**: `'Account Manager'`
- **count**: `1`
- **salaryMin**: `0`
- **salaryMax**: `0`
- **phase**: `3` (Operations)
- **employmentType**: `'full-time'`
- **filledBy**: `undefined` (new position)

### Requirements (Arabic)

```typescript
requirements: [
  '--- المؤهلات والخبرة ---',
  'خبرة عملية لا تقل عن سنة واحدة كمدير حسابات أو دور مشابه في إدارة العملاء',
  'خلفية قوية في التسويق (Digital Marketing / Campaign Management / Marketing Strategy)',
  'فهم عميق للـ operations وإدارة العمليات الداخلية',
  '',
  '--- المسؤوليات الأساسية ---',
  'إدارة والتواصل المستمر مع العملاء (Client Relationship Management)',
  'فهم متطلبات العملاء وتحويلها إلى خطط تنفيذ واضحة وقابلة للقياس',
  'التنسيق بين فرق التسويق والتنفيذ والعمليات لضمان التكامل والجودة',
  'متابعة الأداء، المواعيد النهائية، وجودة التسليم للعملاء',
  'إعداد التقارير الدورية للعملاء والإدارة العليا',
  'المساهمة في تحسين الـ workflows والعمليات الداخلية باستمرار',
  'إدارة التوقعات وضمان رضا العملاء على المدى الطويل',
  'التعامل مع التحديات والاستفسارات من العملاء بطريقة احترافية',
  'تنسيق الاجتماعات الدورية والـ check-ins مع العملاء',
  'تحليل أداء الحسابات وتحديد فرص النمو والتحسين',
  '',
  '--- المهارات التقنية ---',
  'إتقان أدوات إدارة المشاريع (Project Management Tools): Notion, Trello, Asana, Monday.com',
  'خبرة في أدوات التواصل والعروض: Slack, Microsoft Teams, Google Workspace',
  'فهم أساسي لأدوات التحليلات: Google Analytics, CRM systems',
  'معرفة بأدوات التسويق الرقمي الأساسية',
  '',
  '--- المهارات الشخصية ---',
  'مهارات تواصل وتنظيم عالية جداً',
  'القدرة على العمل تحت ضغط وإدارة أكثر من حساب في نفس الوقت',
  'مهارات حل المشكلات والتفكير التحليلي',
  'القدرة على بناء علاقات طويلة المدى مع العملاء',
  'مهارات التفاوض وإدارة التوقعات',
  'الانتباه للتفاصيل والدقة في التنفيذ',
  'مهارات العرض والتقديم (Presentation Skills)',
  'القدرة على العمل بشكل تعاوني مع فرق متعددة',
  '',
  '--- اللغات ---',
  'إتقان اللغة العربية (شرط أساسي)',
  'إتقان اللغة الإنجليزية (مطلوب)',
  '',
  '--- ميزات إضافية ---',
  '⭐ خبرة في العمل مع شركات SaaS أو B2B',
  '⭐ خبرة في السوق السعودي أو الخليجي',
  '⭐ شهادات في إدارة المشاريع (PMP, Agile)',
  '⭐ خبرة في استخدام أدوات CRM متقدمة',
  '⭐ فهم أساسي لـ SEO و Digital Marketing metrics',
];
```

### Requirements (English)

```typescript
requirementsEn: [
  '--- Qualifications & Experience ---',
  'Minimum 1 year of hands-on experience as Account Manager or similar client management role',
  'Strong background in marketing (Digital Marketing / Campaign Management / Marketing Strategy)',
  'Deep understanding of operations and internal processes management',
  '',
  '--- Core Responsibilities ---',
  'Manage and maintain continuous communication with clients (Client Relationship Management)',
  'Understand client requirements and translate them into clear, measurable execution plans',
  'Coordinate between marketing, execution, and operations teams to ensure integration and quality',
  'Monitor performance, deadlines, and delivery quality for clients',
  'Prepare periodic reports for clients and senior management',
  'Continuously contribute to improving workflows and internal processes',
  'Manage expectations and ensure long-term client satisfaction',
  'Handle challenges and client inquiries professionally',
  'Coordinate regular meetings and check-ins with clients',
  'Analyze account performance and identify growth and improvement opportunities',
  '',
  '--- Technical Skills ---',
  'Proficiency in Project Management Tools: Notion, Trello, Asana, Monday.com',
  'Experience with communication and presentation tools: Slack, Microsoft Teams, Google Workspace',
  'Basic understanding of analytics tools: Google Analytics, CRM systems',
  'Knowledge of basic digital marketing tools',
  '',
  '--- Soft Skills ---',
  'Excellent communication and organizational skills',
  'Ability to work under pressure and manage multiple accounts simultaneously',
  'Problem-solving and analytical thinking skills',
  'Ability to build long-term relationships with clients',
  'Negotiation skills and expectation management',
  'Attention to detail and execution accuracy',
  'Presentation skills',
  'Ability to work collaboratively with multiple teams',
  '',
  '--- Languages ---',
  'Fluent in Arabic (essential)',
  'Fluent in English (required)',
  '',
  '--- Plus Points ---',
  '⭐ Experience working with SaaS or B2B companies',
  '⭐ Experience in Saudi or GCC market',
  '⭐ Project management certifications (PMP, Agile)',
  '⭐ Experience with advanced CRM tools',
  '⭐ Basic understanding of SEO and Digital Marketing metrics',
];
```

---

## Position 2: SEO Specialist | أخصائي SEO

### Metadata

- **title**: `'أخصائي SEO'`
- **titleEn**: `'SEO Specialist'`
- **count**: `1`
- **salaryMin**: `0`
- **salaryMax**: `0`
- **phase**: `2` (Content Team)
- **employmentType**: `'full-time'`
- **filledBy**: `undefined` (new position)

### Requirements (Arabic)

```typescript
requirements: [
  '--- المؤهلات والخبرة ---',
  'خبرة عملية 4 سنوات أو أكثر في SEO',
  'خبرة متقدمة في On-Page, Off-Page & Technical SEO',
  'فهم قوي لخوارزميات Google وأفضل ممارسات SEO',
  'القدرة على تحليل البيانات واتخاذ قرارات مبنية على أرقام',
  '',
  '--- المسؤوليات الأساسية ---',
  '--- On-Page SEO ---',
  'تنفيذ وتحسين استراتيجيات On-Page SEO (Content Optimization, Keywords, Internal Linking, Meta Data)',
  'تحسين عناوين الصفحات (Title Tags)، الوصف (Meta Descriptions)، والـ Headers (H1-H6)',
  'تحسين بنية URL وهيكلة الموقع',
  'تحسين محتوى الصفحات لتحقيق أفضل ترتيب في محركات البحث',
  'تطبيق Schema Markup وStructured Data',
  'تحسين الصور (Image Optimization) مع ALT tags وضوغط الصور',
  '',
  '--- Off-Page SEO ---',
  'إدارة وتنفيذ استراتيجيات Off-Page SEO (Link Building, Outreach, Backlinks Analysis)',
  'بناء علاقات مع مواقع الويب والمدونات ذات الصلة',
  'تحليل وتحسين ملف الروابط الخلفية (Backlink Profile)',
  'مراقبة والاستجابة لـ Negative SEO إذا حدث',
  'إدارة حملات Guest Posting وContent Outreach',
  '',
  '--- Technical SEO ---',
  'التعامل المتقدم مع Technical SEO (Site Structure, Indexing, Crawling, Page Speed, Core Web Vitals)',
  'إعداد وتحسين ملفات robots.txt و XML sitemaps',
  'تحسين سرعة تحميل الموقع (Page Speed Optimization)',
  'تحسين Core Web Vitals (LCP, FID, CLS)',
  'ضمان Mobile-First Indexing والاستجابة للموبايل',
  'حل مشاكل الـ Indexing والـ Crawling',
  'تحسين بنية الموقع والـ Site Architecture',
  '',
  '--- التحليل والتقارير ---',
  'تحليل الأداء باستخدام أدوات SEO: Google Search Console, Google Analytics, Ahrefs, SEMrush',
  'إعداد تقارير دورية شاملة عن أداء SEO',
  'تتبع الترتيب (Rank Tracking) للكلمات المفتاحية المستهدفة',
  'تحليل المنافسين وتحديد فرص التحسين',
  'عمل SEO Audits دورية واقتراح حلول قابلة للتنفيذ',
  'متابعة التحديثات المستمرة في خوارزميات محركات البحث (Google Algorithm Updates)',
  'تطبيق التغييرات بناءً على البيانات والتحليل',
  '',
  '--- التنسيق والتعاون ---',
  'التعاون مع فريق المحتوى لتحسين المقالات والمنشورات',
  'العمل مع المطورين لتنفيذ التحسينات التقنية',
  'التنسيق مع فريق التسويق لتحقيق الأهداف المشتركة',
  '',
  '--- المهارات التقنية والأدوات ---',
  'خبرة متقدمة في أدوات SEO الأساسية:',
  'Google Search Console (متقدم)',
  'Google Analytics (GA4)',
  'Ahrefs أو SEMrush (أحدهم على الأقل)',
  'Screaming Frog أو أدوات Crawling مشابهة',
  'PageSpeed Insights و Core Web Vitals',
  'معرفة بـ Schema.org و Structured Data',
  'فهم لـ HTML, CSS, JavaScript (أساسي)',
  'خبرة في استخدام أدوات Link Building',
  '',
  '--- المهارات الشخصية ---',
  'مهارات تحليلية ممتازة',
  'القدرة على العمل بشكل مستقل وإدارة الأولويات',
  'الانتباه للتفاصيل والدقة',
  'مهارات تواصل ممتازة (كتابة وعرض)',
  'القدرة على شرح المفاهيم التقنية لغير المتخصصين',
  'مهارات حل المشكلات والتفكير الإبداعي',
  '',
  '--- اللغات ---',
  'إتقان اللغة العربية (شرط أساسي)',
  'إتقان اللغة الإنجليزية (مطلوب)',
  '',
  '--- ميزات إضافية ---',
  '⭐ خبرة في SEO للمحتوى العربي والسوق السعودي/الخليجي',
  '⭐ خبرة في SEO لـ E-commerce platforms (Shopify, WooCommerce, Salla, Zid)',
  '⭐ معرفة بـ Local SEO',
  '⭐ شهادات SEO (Google Analytics Certification, etc.)',
  '⭐ خبرة في استخدام أدوات AI لتحسين SEO',
  '⭐ خبرة في Python أو Scripting لـ SEO automation',
];
```

### Requirements (English)

```typescript
requirementsEn: [
  '--- Qualifications & Experience ---',
  '4 years or more of hands-on SEO experience',
  'Advanced experience in On-Page, Off-Page & Technical SEO',
  'Strong understanding of Google algorithms and SEO best practices',
  'Ability to analyze data and make data-driven decisions',
  '',
  '--- Core Responsibilities ---',
  '--- On-Page SEO ---',
  'Execute and optimize On-Page SEO strategies (Content Optimization, Keywords, Internal Linking, Meta Data)',
  'Optimize page titles (Title Tags), descriptions (Meta Descriptions), and Headers (H1-H6)',
  'Optimize URL structure and site architecture',
  'Optimize page content to achieve best search engine rankings',
  'Implement Schema Markup and Structured Data',
  'Optimize images (Image Optimization) with ALT tags and image compression',
  '',
  '--- Off-Page SEO ---',
  'Manage and execute Off-Page SEO strategies (Link Building, Outreach, Backlinks Analysis)',
  'Build relationships with relevant websites and blogs',
  'Analyze and improve backlink profile',
  'Monitor and respond to Negative SEO if it occurs',
  'Manage Guest Posting campaigns and Content Outreach',
  '',
  '--- Technical SEO ---',
  'Advanced Technical SEO (Site Structure, Indexing, Crawling, Page Speed, Core Web Vitals)',
  'Setup and optimize robots.txt and XML sitemaps files',
  'Optimize page loading speed (Page Speed Optimization)',
  'Optimize Core Web Vitals (LCP, FID, CLS)',
  'Ensure Mobile-First Indexing and mobile responsiveness',
  'Resolve Indexing and Crawling issues',
  'Optimize site structure and Site Architecture',
  '',
  '--- Analysis & Reporting ---',
  'Analyze performance using SEO tools: Google Search Console, Google Analytics, Ahrefs, SEMrush',
  'Prepare comprehensive periodic SEO performance reports',
  'Track ranking (Rank Tracking) for target keywords',
  'Analyze competitors and identify improvement opportunities',
  'Conduct periodic SEO Audits and propose actionable solutions',
  'Monitor continuous updates in search engine algorithms (Google Algorithm Updates)',
  'Apply changes based on data and analysis',
  '',
  '--- Coordination & Collaboration ---',
  'Collaborate with content team to optimize articles and posts',
  'Work with developers to implement technical improvements',
  'Coordinate with marketing team to achieve shared goals',
  '',
  '--- Technical Skills & Tools ---',
  'Advanced experience with essential SEO tools:',
  'Google Search Console (advanced)',
  'Google Analytics (GA4)',
  'Ahrefs or SEMrush (at least one)',
  'Screaming Frog or similar crawling tools',
  'PageSpeed Insights and Core Web Vitals',
  'Knowledge of Schema.org and Structured Data',
  'Understanding of HTML, CSS, JavaScript (basic)',
  'Experience using Link Building tools',
  '',
  '--- Soft Skills ---',
  'Excellent analytical skills',
  'Ability to work independently and manage priorities',
  'Attention to detail and accuracy',
  'Excellent communication skills (writing and presentation)',
  'Ability to explain technical concepts to non-specialists',
  'Problem-solving and creative thinking skills',
  '',
  '--- Languages ---',
  'Fluent in Arabic (essential)',
  'Fluent in English (required)',
  '',
  '--- Plus Points ---',
  '⭐ Experience in SEO for Arabic content and Saudi/GCC market',
  '⭐ Experience in SEO for E-commerce platforms (Shopify, WooCommerce, Salla, Zid)',
  '⭐ Knowledge of Local SEO',
  '⭐ SEO certifications (Google Analytics Certification, etc.)',
  '⭐ Experience using AI tools for SEO optimization',
  '⭐ Experience in Python or Scripting for SEO automation',
];
```

---

## Position 3: Content Writer | كاتب محتوى

### Metadata

- **title**: `'كاتب محتوى'`
- **titleEn**: `'Content Writer'`
- **count**: `1`
- **salaryMin**: `0`
- **salaryMax**: `0`
- **phase**: `2` (Content Team)
- **employmentType**: `'full-time'`
- **filledBy**: `undefined` (new position)

### Requirements (Arabic)

```typescript
requirements: [
  '--- المؤهلات والخبرة ---',
  'خبرة عملية لا تقل عن سنتين في كتابة المحتوى',
  'خبرة سابقة في السوق الخليجي (شرط أساسي)',
  'وجود Portfolio / Samples واضح يظهر جودة العمل (شرط أساسي)',
  'خبرة في كتابة محتوى تسويقي للعلامات التجارية',
  '',
  '--- المسؤوليات الأساسية ---',
  '--- إنشاء المحتوى ---',
  'كتابة محتوى احترافي يناسب طبيعة الجمهور الخليجي (Saudi, UAE, Kuwait, etc.)',
  'كتابة محتوى تسويقي متعدد الأشكال:',
  'Social Media: منشورات، قصص، محتوى تفاعلي',
  'Websites: صفحات المنتج، صفحات الهبوط (Landing Pages)',
  'Ads: نصوص إعلانية لـ Google Ads, Meta Ads, LinkedIn Ads',
  'Blogs: مقالات SEO-friendly للمدونة',
  'الكتابة بأسلوب احترافي مناسب للعلامات التجارية',
  'الالتزام بـ Tone of Voice الخاص بالبراند والحفاظ على الاتساق',
  'كتابة محتوى يراعي SEO (SEO-aware content) مع دمج الكلمات المفتاحية بشكل طبيعي',
  '',
  '--- مراجعة وتحرير ---',
  'مراجعة وتحرير المحتوى لضمان الجودة والدقة اللغوية',
  'التأكد من خلو المحتوى من الأخطاء الإملائية والنحوية',
  'ضمان الاتساق في الأسلوب والشكل',
  'التحقق من دقة المعلومات والوقائع',
  '',
  '--- التعاون والتنسيق ---',
  'التعاون مع فريق التسويق لتحقيق أهداف الحملات',
  'العمل مع SEO Specialist لتحسين المقالات للمحركات البحث',
  'التنسيق مع فريق التصميم لإنشاء محتوى متكامل',
  'المشاركة في اجتماعات التخطيط وBrainstorming sessions',
  'الالتزام بالمواعيد النهائية والعمل ضمن فريق',
  '',
  '--- البحث والفهم ---',
  'البحث المستمر عن الموضوعات والاتجاهات في السوق الخليجي',
  'فهم عميق لثقافة الجمهور المستهدف وتفضيلاته',
  'تحليل المحتوى المنافس وتحديد فرص التحسين',
  'البقاء محدثاً بآخر الاتجاهات في التسويق الرقمي والمحتوى',
  '',
  '--- المهارات الكتابية ---',
  'مهارات كتابة ممتازة باللغة العربية',
  'مهارات كتابة جيدة باللغة الإنجليزية',
  'القدرة على التكيف مع أنماط كتابة مختلفة حسب العلامة التجارية',
  'فهم عميق للغة التسويق والإقناع (Copywriting)',
  'القدرة على كتابة محتوى جذاب ومقنع',
  'مهارات البحث وجمع المعلومات',
  '',
  '--- المعرفة المتخصصة ---',
  'فهم عميق لثقافة السوق الخليجي وعادات المستهلكين',
  'معرفة بمنصات التواصل الاجتماعي وأفضل الممارسات',
  'فهم أساسي لـ SEO وكتابة المحتوى المحسّن للمحركات البحث',
  'معرفة بأساسيات التسويق الرقمي',
  '',
  '--- المهارات الشخصية ---',
  'الالتزام بالمواعيد والعمل ضمن فريق',
  'القدرة على العمل تحت ضغط',
  'الانتباه للتفاصيل والدقة',
  'مهارات تواصل جيدة',
  'الإبداع والتفكير الإبداعي',
  'القدرة على تلقي وتطبيق الملاحظات (Feedback)',
  '',
  '--- اللغات ---',
  'إتقان اللغة العربية (شرط أساسي جداً)',
  'إتقان اللغة الإنجليزية (مطلوب)',
  '',
  '--- ميزات إضافية ---',
  '⭐ خبرة في كتابة محتوى لـ E-commerce أو SaaS companies',
  '⭐ خبرة في كتابة محتوى تقني أو B2B',
  '⭐ معرفة بأدوات AI للكتابة (ChatGPT, Jasper, etc.)',
  '⭐ مهارات في التصميم الأساسي (Canva, Adobe)',
  '⭐ معرفة بـ CMS platforms (WordPress, etc.)',
  '⭐ خبرة في إدارة المحتوى على منصات التواصل الاجتماعي',
];
```

### Requirements (English)

```typescript
requirementsEn: [
  '--- Qualifications & Experience ---',
  'Minimum 2 years of hands-on content writing experience',
  'Previous experience in GCC market (essential requirement)',
  'Clear Portfolio / Samples demonstrating work quality (essential requirement)',
  'Experience writing marketing content for brands',
  '',
  '--- Core Responsibilities ---',
  '--- Content Creation ---',
  'Write professional content suitable for GCC audience nature (Saudi, UAE, Kuwait, etc.)',
  'Write multi-format marketing content:',
  'Social Media: Posts, stories, interactive content',
  'Websites: Product pages, landing pages',
  'Ads: Ad copy for Google Ads, Meta Ads, LinkedIn Ads',
  'Blogs: SEO-friendly articles for the blog',
  'Write in professional style suitable for brands',
  'Maintain brand Tone of Voice and consistency',
  'Write SEO-aware content with natural keyword integration',
  '',
  '--- Review & Editing ---',
  'Review and edit content to ensure quality and linguistic accuracy',
  'Ensure content is free from spelling and grammatical errors',
  'Ensure consistency in style and format',
  'Verify accuracy of information and facts',
  '',
  '--- Collaboration & Coordination ---',
  'Collaborate with marketing team to achieve campaign goals',
  'Work with SEO Specialist to optimize articles for search engines',
  'Coordinate with design team to create integrated content',
  'Participate in planning meetings and brainstorming sessions',
  'Meet deadlines and work within a team',
  '',
  '--- Research & Understanding ---',
  'Continuous research on topics and trends in GCC market',
  'Deep understanding of target audience culture and preferences',
  'Analyze competitor content and identify improvement opportunities',
  'Stay updated with latest trends in digital marketing and content',
  '',
  '--- Writing Skills ---',
  'Excellent Arabic writing skills',
  'Good English writing skills',
  'Ability to adapt to different writing styles according to brand',
  'Deep understanding of marketing language and persuasion (Copywriting)',
  'Ability to write engaging and persuasive content',
  'Research and information gathering skills',
  '',
  '--- Specialized Knowledge ---',
  'Deep understanding of GCC market culture and consumer habits',
  'Knowledge of social media platforms and best practices',
  'Basic understanding of SEO and search engine optimized content writing',
  'Knowledge of digital marketing fundamentals',
  '',
  '--- Soft Skills ---',
  'Meeting deadlines and working within a team',
  'Ability to work under pressure',
  'Attention to detail and accuracy',
  'Good communication skills',
  'Creativity and creative thinking',
  'Ability to receive and apply feedback',
  '',
  '--- Languages ---',
  'Fluent in Arabic (highly essential)',
  'Fluent in English (required)',
  '',
  '--- Plus Points ---',
  '⭐ Experience writing content for E-commerce or SaaS companies',
  '⭐ Experience writing technical or B2B content',
  '⭐ Knowledge of AI writing tools (ChatGPT, Jasper, etc.)',
  '⭐ Basic design skills (Canva, Adobe)',
  '⭐ Knowledge of CMS platforms (WordPress, etc.)',
  '⭐ Experience managing content on social media platforms',
];
```

---

## Implementation Example

To add these positions to the codebase, add them to `helpers/extractMetrics.ts` in the `getTeamPositions()` function:

```typescript
// Add to Phase 2 (Content Team) section:
{
  title: 'أخصائي SEO',
  titleEn: 'SEO Specialist',
  count: 1,
  salaryMin: 0,
  salaryMax: 0,
  phase: 2,
  employmentType: 'full-time',
  requirements: [
    // ... copy requirements array from above
  ],
  requirementsEn: [
    // ... copy requirementsEn array from above
  ]
},
{
  title: 'كاتب محتوى',
  titleEn: 'Content Writer',
  count: 1,
  salaryMin: 0,
  salaryMax: 0,
  phase: 2,
  employmentType: 'full-time',
  requirements: [
    // ... copy requirements array from above
  ],
  requirementsEn: [
    // ... copy requirementsEn array from above
  ]
},

// Add to Phase 3 (Operations) section:
{
  title: 'مدير حسابات',
  titleEn: 'Account Manager',
  count: 1,
  salaryMin: 0,
  salaryMax: 0,
  phase: 3,
  employmentType: 'full-time',
  requirements: [
    // ... copy requirements array from above
  ],
  requirementsEn: [
    // ... copy requirementsEn array from above
  ]
}
```

---

## Contact Information

**Application Method:** WhatsApp +966554113107  
**Note:** For Content Writer position, Portfolio/Writing Samples are required.

---

_Last Updated: January 2025_
