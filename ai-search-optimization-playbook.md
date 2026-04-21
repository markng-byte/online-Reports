# AI Search Optimization Playbook
> **Phạm vi:** GEO · AIO · AEO · E-E-A-T · Schema.org  
> **Cập nhật:** 2025–2026  
> **Dùng cho:** SEO, Content, Paid Ads, Sales & Mkt, Developer, Brand/PR

---

## 1. Cơ chế hoạt động của các AI platform

### 1.1 Tổng quan 8 platforms chính

| Platform | Nguồn index chính | Tiêu chí ưu tiên | Điểm mù |
|---|---|---|---|
| **Perplexity** | Bing + crawl riêng + Reddit | Heading H2/H3 rõ, bullets, dữ liệu số, citation | Domain mới / DA thấp bị bỏ qua |
| **ChatGPT Browse (GPT-4o)** | Bing index + plugin | DA cao, content dài, backlink mạnh | Ưu tiên EN, domain .vn yếu hơn |
| **Gemini / AI Overviews** | Google full index | E-E-A-T, Schema, Core Web Vitals, mobile-first | Trang JS-heavy hoặc không indexable |
| **Grok (xAI)** | X (Twitter) real-time + Bing | Được quote/repost trên X, trending hashtag | Nội dung không có presence trên X |
| **Meta AI** | Bing + FB/IG social graph | Engagement (likes, shares, comments) | Rất yếu với B2B và nội dung kỹ thuật |
| **Claude (Anthropic)** | Training data (knowledge cutoff) | Được cite bởi nguồn uy tín, Wikipedia, báo lớn | Không cập nhật real-time |
| **SearchGPT / Bing AI** | Microsoft Bing index | Schema đầy đủ, tốc độ tải, backlink, content fresh | Kém hơn Google về depth indexing |
| **AI Overviews (Google)** | Google full index (top-ranked) | Đã rank top + FAQ schema | Chỉ lấy từ trang Google trust cao |

### 1.2 Nguyên lý chọn nguồn để trích dẫn

AI không tìm "ai rank #1" — AI tìm "ai trả lời rõ nhất và đáng tin nhất". Một trang DA thấp nhưng có FAQ schema + answer-first content vẫn được Perplexity cite, trong khi trang DA cao viết kiểu dẫn dắt dài dòng sẽ bị bỏ qua.

---

## 2. Tín hiệu xếp hạng

### 2.1 Mức độ ảnh hưởng (cao → thấp)

| Tín hiệu | Trọng số | Ghi chú |
|---|---|---|
| E-E-A-T (Experience, Expertise, Authoritativeness, Trust) | ●●●●● 95% | Quan trọng nhất với Google + Perplexity |
| Structured data / Schema markup | ●●●●● 90% | AI extract data trực tiếp từ schema |
| Content structure (H1 → H2 → H3) | ●●●●◐ 88% | AI đọc outline để hiểu hierarchy nội dung |
| Nội dung dạng Q&A / FAQ | ●●●●◐ 85% | Format AI ưa nhất để trả lời queries |
| Domain authority / Backlink | ●●●●○ 82% | Vẫn thiết yếu — AI chọn nguồn được cite nhiều |
| Core Web Vitals / Page speed | ●●●●○ 78% | LCP, INP, CLS ảnh hưởng crawlability |
| Được cite bởi AI khác | ●●●○○ 75% | Hiệu ứng flywheel: càng được cite càng được cite |
| Fresh / updated content | ●●●○○ 65% | Quan trọng với queries time-sensitive |
| Social signals (X, LinkedIn) | ●●●○○ 60% | Platform-specific: Grok & Meta AI đọc social |
| Keyword density (truyền thống) | ●○○○○ 30% | AI đọc ngữ nghĩa, không đếm keyword |

### 2.2 SEO truyền thống vs AI Search Optimization

| Yếu tố | SEO truyền thống | AI Search (GEO/AIO) | Xu hướng |
|---|---|---|---|
| Keyword placement | Title, H1, body 1–2% | Ít quan trọng; AI đọc ngữ nghĩa | ↓ Giảm trọng số |
| Backlink | Số lượng + chất lượng | Vẫn quan trọng — AI chọn nguồn được cite nhiều | → Không đổi |
| Nội dung dài | 3,000+ từ tốt hơn | AI ưu tiên súc tích, trả lời trực tiếp | ↓ Thay đổi lớn |
| Meta description | Tối ưu CTR | AI đọc để hiểu trang, không cite trực tiếp | ↓ Vai trò phụ |
| Schema Markup | Rich snippets, tăng CTR | AI extract data trực tiếp từ schema | ↑ Tăng mạnh |
| FAQ section | Featured snippet | Format AI ưa nhất — trả lời trực tiếp | ↑ Cực kỳ quan trọng |
| Author bio | Ít quan tâm | E-E-A-T signal — AI cần biết ai viết | ↑ Quan trọng hơn |
| Social proof | Off-page yếu | Meta AI / Grok đọc social; ảnh hưởng gián tiếp | ↑ Platform-specific |

---

## 3. Schema & Technical Requirements

### 3.1 Schema types ưu tiên

| Schema type | Dùng khi nào | Platform hưởng lợi | Ưu tiên |
|---|---|---|---|
| `FAQPage` | Mọi landing page, blog có câu hỏi | Google AIO, ChatGPT, Perplexity | 🟢 Cao nhất |
| `HowTo` | Hướng dẫn, quy trình từng bước | Google AIO, Perplexity | 🟢 Cao |
| `Article` / `BlogPosting` | Tất cả bài viết blog | Tất cả platforms | 🟢 Cao |
| `Organization` | Homepage, About page | Knowledge Graph, Claude training | 🔵 Trung bình-cao |
| `Person` | Author page, team bios | E-E-A-T cho Google, Perplexity | 🔵 Trung bình-cao |
| `Product` + `Review` | Trang sản phẩm, so sánh | Google Shopping, ChatGPT | 🟡 Tùy ngành |
| `Speakable` | Nội dung muốn AI đọc to (voice) | Google Assistant, voice AI | 🟡 Mới nổi |
| `ClaimReview` | Fact-checking, báo chí | Google News, Perplexity | ⚪ Niche |

> **Lưu ý triển khai:** Dùng JSON-LD inject vào `<head>`, không dùng Microdata inline. Validate bằng [Google Rich Results Test](https://search.google.com/test/rich-results) sau mỗi lần deploy.

### 3.2 Technical checklist

#### Crawlability (bắt buộc)

- [ ] **robots.txt** — không block AI bots: `GPTBot`, `ClaudeBot`, `PerplexityBot`, `Google-Extended`, `CCBot`, `meta-externalagent`, `Applebot-Extended`, `YouBot`
- [ ] **Sitemap.xml** cập nhật tự động, submit lên Google Search Console + Bing Webmaster Tools
- [ ] **HTTPS** toàn site, không lỗi 404/500 (crawl error giảm trust score toàn domain)
- [ ] **Server-side rendering** cho nội dung JS-heavy (AI crawler không render JS tốt)

#### AI Readability (ưu tiên cao)

- [ ] **llms.txt** tại `/llms.txt` — liệt kê nội dung tốt nhất cho LLM đọc (tương tự robots.txt nhưng dành cho AI)
- [ ] **JSON-LD schema** đúng type cho từng page (FAQPage, Article, Organization, Person)
- [ ] **Semantic HTML**: đúng H1 > H2 > H3, mỗi trang chỉ 1 thẻ H1
- [ ] **Author markup**: mỗi bài có author link đến author page đầy đủ credentials + Person schema

#### Performance

- [ ] **Core Web Vitals**: LCP < 2.5s · INP < 200ms · CLS < 0.1
- [ ] **Mobile-first**: responsive hoàn toàn, Google index mobile version trước
- [ ] **Canonical URL** đúng, tránh duplicate content

#### Social & Discovery

- [ ] **Open Graph + Twitter Card** đầy đủ (Grok và Meta AI đọc OG tags)
- [ ] **Internal linking** rõ ràng, anchor text mô tả đúng destination
- [ ] **hreflang** nếu có đa ngôn ngữ VI/EN

### 3.3 Danh sách AI user agents (cho robots.txt)

```
GPTBot              # OpenAI — ChatGPT, SearchGPT
ClaudeBot           # Anthropic — Claude
PerplexityBot       # Perplexity AI
Google-Extended     # Google Gemini training
Googlebot           # Google Search + AI Overviews
CCBot               # Common Crawl (training data nhiều LLM)
Bytespider          # ByteDance / TikTok AI
Applebot-Extended   # Apple AI / Siri
YouBot              # You.com
meta-externalagent  # Meta AI
```

---

## 4. Chiến lược nội dung (GEO — Generative Engine Optimization)

### 4.1 Format nội dung AI ưa nhất

| Thứ tự | Format | Lý do AI ưa | Cách áp dụng |
|---|---|---|---|
| 1 | **Q&A / FAQ** | Trực tiếp trả lời intent, dễ extract | 5–8 câu hỏi thực tế cuối mỗi bài + FAQPage schema |
| 2 | **Định nghĩa rõ ràng** | AI tìm "X là gì" — muốn definition ngay đầu | Paragraph đầu tiên: định nghĩa súc tích 2–3 câu |
| 3 | **Numbered list / Steps** | Dễ trích dẫn từng bước, có cấu trúc | Quy trình, hướng dẫn: số thứ tự, không dùng bullet chung |
| 4 | **Comparison table** | AI extract bảng để trả lời "X vs Y" | So sánh sản phẩm, dịch vụ, đối thủ |
| 5 | **Statistic + source** | AI ưu tiên nội dung có số liệu được cite | Mỗi claim quan trọng có số liệu + link nguồn |
| 6 | **Expert quote** | E-E-A-T signal, tăng trust | Trích dẫn chuyên gia kèm title + tổ chức |
| 7 | **Summary / TL;DR box** | AI đọc tóm tắt trước để lấy answer nhanh | Key takeaways 3–5 điểm ở đầu bài |

### 4.2 Nguyên tắc GEO

**Answer-first writing**
Trả lời câu hỏi chính ngay trong 1–2 câu đầu tiên. Không dẫn dắt. AI lấy snippet từ đầu trang.

**Topical authority**
Xây topic cluster: 1 pillar page + 10–15 supporting pages cùng chủ đề. AI nhận ra domain expertise và ưu tiên nguồn đó cho mọi queries trong ngành.

**Cite từ nguồn uy tín**
Nếu bạn cite Wikipedia, nghiên cứu học thuật, báo lớn — AI coi bạn đáng tin hơn. Backlink 2 chiều càng tốt.

**Không gate nội dung quan trọng**
Nội dung sau paywall / login không được crawl. Phần quan trọng nhất phải public hoàn toàn.

**Cập nhật định kỳ**
Thêm "Updated: [date]" vào bài. Perplexity và AI search ưu tiên nội dung fresh cho queries time-sensitive.

**Tạo nội dung gốc / research**
Survey, case study, dữ liệu riêng của bạn → được các nguồn khác cite → AI thấy bạn là primary source, không phải aggregator.

**Ngôn ngữ tự nhiên, câu hỏi thực**
Dùng cách người thực sự hỏi AI: "Làm thế nào để...", "Tại sao...", "Sự khác biệt giữa... là gì". Không nhồi keyword máy móc.

---

## 5. Playbook theo từng team

### 5.1 SEO Team

- Implement `FAQPage` + `HowTo` schema trên tất cả pages
- Tối ưu semantic HTML: H1 > H2 > H3 đúng hierarchy
- Tạo `/llms.txt` file tại root domain
- Review `robots.txt` — không block AI bots (xem danh sách mục 3.3)
- Xây topic cluster: 1 pillar + 10+ supporting posts mỗi chủ đề cốt lõi
- Track Featured Snippet + AI Overview appearances trong Search Console
- Monitor Core Web Vitals hàng tuần bằng PageSpeed Insights
- Submit sitemap lên cả Google Search Console và Bing Webmaster Tools

### 5.2 Content / Editorial Team

- Answer-first writing: trả lời intent trong 2 câu đầu, không dẫn dắt
- Mỗi bài có FAQ section 5–8 câu ở cuối với FAQPage schema
- Thêm author bio đầy đủ + credentials vào mỗi bài (name, title, LinkedIn)
- Dùng số liệu + cite nguồn uy tín cho mọi claim quan trọng
- Tạo "Key Takeaways" box đầu mỗi bài dài hơn 1,000 từ
- Update bài cũ + thêm "Last updated [date]" khi có thông tin mới
- Tạo glossary / định nghĩa cho terms ngành
- Viết comparison articles (X vs Y) có structured table rõ ràng

### 5.3 Paid Ads / Performance Team

- Landing page cần đủ schema để AI hiểu product (Product + FAQPage)
- Dùng FAQ schema trên landing page quảng cáo — cải thiện Quality Score
- Kiểm tra định kỳ: AI Overview có xuất hiện khi search brand keywords?
- Khi AI cite đối thủ, phân tích họ viết gì để xây dựng counter-content
- AI-driven queries thường có CPC thấp hơn — cơ hội mở rộng keyword pool
- Setup UTM tracking cho AI referral: `utm_source=perplexity`, `chatgpt`, `copilot`
- Remarketing audience từ người đến qua AI referral (khác behavior với organic)

### 5.4 Sales & Marketing Team

- Khi khách nói "AI recommend", hỏi platform nào — dùng để đo AI share of voice
- Tạo nội dung "Why [Brand]" — AI hay trả lời câu này khi user so sánh
- Collect testimonial + case study có số liệu cụ thể — AI dùng làm social proof
- FAQ từ sales call thực tế → đưa vào website FAQ schema
- Xây dựng brand mentions trên báo, diễn đàn ngành, podcast
- LinkedIn thought leadership cho key persons → tăng E-E-A-T author
- Press release lên PRNewswire, 24h.com.vn → AI index nhanh

### 5.5 Developer / Technical Team

- Tạo `/llms.txt` + `/llms-full.txt` theo spec (llmstxt.org)
- Inject JSON-LD schema vào `<head>` động theo page type (không hardcode)
- Server-side rendering cho toàn bộ nội dung quan trọng (không phụ thuộc JS)
- Tự động hóa sitemap update khi publish bài mới
- Monitor server logs để theo dõi GPTBot, ClaudeBot crawl gì và khi nào
- PageSpeed target: LCP < 2s, CLS = 0 cho trang quan trọng
- Implement `hreflang` đúng cho đa ngôn ngữ VI/EN
- Setup GA4 custom dimension để phân tích AI referral traffic riêng

### 5.6 Brand / PR Team

- Tạo / cập nhật Wikipedia article về brand (nếu chưa có)
- Tạo Wikidata entity cho company — AI đọc để fact-check thông tin brand
- Pitch để được mention trong báo lớn (VnExpress, CafeF, Tuổi Trẻ, Nhịp Cầu Đầu Tư)
- Tham gia industry rankings, awards — AI cite các danh sách này
- Build presence trên Reddit, Quora (EN) — Perplexity index rất mạnh
- Kiểm soát thông tin sai trên web trước khi AI học và lan rộng
- Theo dõi brand mention trên AI platforms định kỳ (test query hàng tháng)

---

## 6. Lộ trình triển khai

### 6.1 Ưu tiên theo thứ tự

| # | Hạng mục | Timeline | Team | Ghi chú |
|---|---|---|---|---|
| 1 | Kiểm tra & fix `robots.txt` | Ngay lập tức | Dev | Nếu block AI bots, mọi effort sau đều vô nghĩa |
| 2 | Triển khai FAQPage Schema | Tuần 1–2 | Dev + SEO | 10–20 trang quan trọng nhất trước |
| 3 | Tạo file `/llms.txt` | Tuần 1–2 | Dev | Mất 30–60 phút, ROI cao |
| 4 | Answer-first content rewrite | Tháng 1 | Content | Bắt đầu từ 20 bài traffic cao nhất |
| 5 | Author E-E-A-T pages | Tháng 1–2 | Content + Dev | Person schema + author page đầy đủ |
| 6 | Topic cluster architecture | Tháng 2–3 | SEO + Content | 3–5 chủ đề cốt lõi trước |
| 7 | Brand mentions & digital PR | Ongoing | PR + Mkt | Compound effect theo thời gian |
| 8 | Track AI referral traffic | Ongoing | Dev + Ads | KPI mới song song organic |

### 6.2 KPIs mới cần theo dõi

Bên cạnh các KPI SEO truyền thống, bổ sung:

- **AI referral sessions** — traffic từ perplexity.ai, chatgpt.com, copilot.microsoft.com, claude.ai
- **AI Overview appearances** — số lần brand xuất hiện trong Google AI Overviews
- **Share of AI voice** — khi test query ngành, brand có được AI nhắc đến không?
- **Schema coverage** — % trang quan trọng đã có đúng schema type
- **llms.txt crawl rate** — xem trong server logs có AI bots đọc file này không

---

## 7. Tài nguyên tham khảo

- [Google Search Central — E-E-A-T](https://developers.google.com/search/docs/fundamentals/creating-helpful-content)
- [Schema.org — Full type list](https://schema.org/docs/full.html)
- [Google Rich Results Test](https://search.google.com/test/rich-results)
- [llmstxt.org — llms.txt specification](https://llmstxt.org)
- [Google AI Overviews documentation](https://developers.google.com/search/docs/appearance/ai-overviews)
- [Bing Webmaster Tools](https://www.bing.com/webmasters)

---

*Document này là module độc lập, có thể include vào kế hoạch chiến lược tổng thể. Cập nhật định kỳ theo diễn biến của các AI platforms.*
