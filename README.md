# Chistara MCP server — Iranian legal corpus · سرور MCP چیستارا

**Chistara (چیستارا, [hoghogh.ai](https://hoghogh.ai))** is an AI legal assistant for Iranian law. This MCP server gives
Claude, ChatGPT, Codex, Perplexity and any other MCP client the same verified legal corpus and calculators that power the
Chistara app: 70,000+ statute articles and notes, 50,000+ court rulings, the Judiciary's advisory opinions, official
circulars, yearly official rates and procedural deadlines, and 14 legal calculators. Every result carries a `source_url`
on hoghogh.ai, so the assistant can cite the exact article or ruling instead of answering from memory.

چیستارا دستیار حقوقی هوش مصنوعی برای قوانین ایران است. با این سرور MCP، Claude و ChatGPT و دیگر دستیارها به همان
پایگاه قوانین، آرا، نظریات مشورتی، بخشنامه‌ها و ماشین‌حساب‌های حقوقی چیستارا وصل می‌شوند و هر پاسخ پیوند منبع رسمی دارد.

| | |
|---|---|
| Endpoint | `https://hoghogh.ai/mcp/connect` (OAuth sign-in) · `https://hoghogh.ai/mcp` (personal link) — Streamable HTTP |
| Official MCP Registry | `ai.hoghogh/chistara` |
| Tools | 23, all read-only (`readOnlyHint: true`, `destructiveHint: false`) |
| Language | Persian content; tool titles in Persian and English |
| Account | A Chistara account with credit; each successful tool call is charged to that balance |

## Connect

**Claude and ChatGPT (sign in, recommended)**

1. Add a custom connector with the URL **`https://hoghogh.ai/mcp/connect`**
   - Claude (claude.ai or the desktop app): Settings → Connectors → *Add custom connector*.
   - ChatGPT: Settings → Apps & Connectors → *Create* (developer mode).
2. Your assistant opens Chistara's sign-in page: sign in to your Chistara account and choose **Allow**.
3. Ask a question about Iranian law. The assistant calls the tools it needs and cites the sources.

This is standard OAuth 2.1 (PKCE, dynamic client registration). Disconnect at any time in Chistara:
Settings → دستیار هوشمند → «برنامه‌های متصل».

**Other MCP clients (Codex, Cursor, VS Code, Perplexity…)**

Use your **personal connection link** from [Settings → دستیار هوشمند → MCP](https://hoghogh.ai/app/settings?tab=assistant#mcp)
(`https://hoghogh.ai/mcp/<token>`), or the server URL `https://hoghogh.ai/mcp` with the header
`Authorization: Bearer <token>`.

> **A personal link is a key to your account.** Paste it only into the assistant itself, never into a website that offers to
> connect it for you. You can revoke it and make a new one in the same settings card.

Tool *listing* is public so clients and directories can read the definitions; every tool *call* needs the personal link.

## Tools

| Tool | What it does | فارسی |
|---|---|---|
| `search_law_articles` | Search Iranian law articles | جست‌وجوی مواد قانونی |
| `lookup_law_article` | Look up one article verbatim | متن دقیق یک ماده |
| `search_case_law` | Search Iranian court rulings | جست‌وجوی آرای قضایی |
| `search_circular` | Search official circulars | جست‌وجوی بخشنامه‌ها |
| `calculate_diyeh` | Calculate blood money (دیه) | محاسبهٔ دیه |
| `calculate_litigation_fee` | Calculate court filing fees | محاسبهٔ هزینهٔ دادرسی |
| `calculate_severance` | Calculate end-of-service entitlements | محاسبهٔ حق سنوات و مزایای پایان کار |
| `search_advisory_opinions` | Search official advisory opinions | جست‌وجوی نظریات مشورتی |
| `lookup_annual_rate` | Look up official yearly rates | نرخ‌های رسمی سالانه |
| `lookup_sentencing_range` | Look up statutory sentencing range | مجازات قانونی جرم |
| `lookup_statute_of_limitations` | Look up statute of limitations | مرور زمان |
| `lookup_procedure` | Look up procedural deadlines | مهلت‌های دادرسی |
| `calculate_mahrieh` | Calculate mahrieh at today's value | محاسبهٔ مهریه به نرخ روز |
| `calculate_inheritance` | Calculate inheritance shares | محاسبهٔ سهم‌الارث |
| `calculate_delay_penalty` | Calculate late-payment damages | محاسبهٔ خسارت تأخیر تأدیه |
| `calculate_stamp_duty` | Calculate registration duty | محاسبهٔ حق‌الثبت |
| `calculate_notary_fee` | Calculate notary fee | محاسبهٔ حق‌التحریر دفترخانه |
| `calculate_lawyer_fee` | Calculate lawyer fee (bar tariff) | محاسبهٔ حق‌الوکاله |
| `calculate_execution_fee` | Calculate judgment execution fee | محاسبهٔ نیم‌عشر اجرایی |
| `calculate_arbitration_fee` | Calculate arbitrator fee | محاسبهٔ حق‌الزحمهٔ داوری |
| `calculate_judicial_service_fee` | Calculate 1405 judicial service fees | محاسبهٔ هزینهٔ خدمات قضایی ۱۴۰۵ |
| `calculate_expert_fee` | Calculate court expert fee | محاسبهٔ دستمزد کارشناسی رسمی |
| `calculate_tax` | Calculate Iranian taxes | محاسبهٔ مالیات |

## Sources

Statute text is kept verbatim from its official source and links the exact official page; rulings, advisory opinions and
circulars come from the Judiciary's and government publications. Yearly figures (diyeh, minimum wage, court fees, tariffs)
are read from the current year's official instruments. Calculators show the rule they applied and the article behind it.

Chistara is a legal research and drafting tool. For a decision in a real case, have a qualified lawyer review the result.

## Links

- Website: [hoghogh.ai](https://hoghogh.ai) · English: [hoghogh.ai/en](https://hoghogh.ai/en) · Pricing: [hoghogh.ai/pricing](https://hoghogh.ai/pricing)
- Registry manifest: [`server.json`](server.json)
- Contact: [info@hoghogh.ai](mailto:info@hoghogh.ai)

Documentation © Chistara, licensed [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). The server itself is a hosted
service; this repository holds its public documentation and registry manifest.
