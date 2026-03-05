# 产品发布的 SEO & GEO 优化指南

> 让你的 Launch 在搜索引擎和 AI 搜索中持续获得曝光

## 为什么 Launch 需要 SEO/GEO？

产品发布是**一次性事件**，但 SEO/GEO 能让发布的势能**持续转化**：
- Launch 期间创造的内容可以长期带来自然流量
- AI 搜索（ChatGPT、Perplexity）会引用你的发布内容
- 媒体报道和 KOL 内容会产生高质量反向链接

---

## 🚀 Launch 前 SEO 准备清单

### 官网优化 (L-4周)

**技术基础**
- [ ] HTTPS + 移动端适配
- [ ] Core Web Vitals 达标 (LCP<2.5s, CLS<0.1)
- [ ] XML Sitemap 提交至 GSC + Bing Webmaster
- [ ] **实施 IndexNow** — 关键！让新内容秒级进入 Bing/AI 搜索

**页面优化**
- [ ] 首页 Title: `[产品名] - [一句话价值主张] | [品牌]` (≤70字符)
- [ ] Meta Description: 包含核心关键词 + CTA (≤160字符)
- [ ] H1 唯一且包含核心关键词
- [ ] 产品截图/视频有描述性 alt 文本

**结构化数据**
```json
{
  "@context": "https://schema.org",
  "@type": "SoftwareApplication",
  "name": "产品名",
  "operatingSystem": "Web",
  "applicationCategory": "类目",
  "offers": {
    "@type": "Offer",
    "price": "0",
    "priceCurrency": "USD"
  }
}
```

### 关键词布局

| 页面类型 | 目标关键词示例 |
|----------|---------------|
| 首页 | [产品名], [品类] tool, [品类] software |
| 功能页 | [功能] tool, how to [任务] |
| 对比页 | [产品名] vs [竞品], [产品名] alternative |
| 定价页 | [产品名] pricing, [产品名] free |

---

## 📰 Launch 内容的 SEO 优化

### 发布博客文章

**Title 公式**
```
Introducing [产品名]: [核心价值] | [品牌名]
例: Introducing AFFiNE: The Open Source Notion Alternative
```

**内容结构**
1. **开头100词**: 直接说明产品是什么、解决什么问题
2. **H2 功能介绍**: 每个核心功能一个 H2
3. **H2 使用场景**: 谁会用、怎么用
4. **H2 定价/开源说明**: 商业模式透明
5. **CTA**: 清晰的下一步行动

**Schema 实施**
```json
{
  "@type": "Article",
  "headline": "Introducing 产品名",
  "datePublished": "2026-03-06",
  "author": {"@type": "Organization", "name": "品牌名"}
}
```

### Product Hunt 页面优化

PH 页面本身有高 DA，但你可以控制：
- **Tagline**: 包含核心关键词 (≤60字符)
- **Description**: 开头就提核心功能和价值
- **Maker Comment**: 补充 SEO 关键词

---

## 🤖 GEO: 让 AI 搜索引用你

### IndexNow 即时推送

Launch Day 发布后**立即**提交所有新 URL：

```bash
# 批量提交
curl -X POST https://www.bing.com/indexnow \
  -H "Content-Type: application/json" \
  -d '{
    "host": "yourproduct.com",
    "key": "YOUR-INDEXNOW-KEY",
    "urlList": [
      "https://yourproduct.com/blog/launch-announcement",
      "https://yourproduct.com/features",
      "https://yourproduct.com/pricing"
    ]
  }'
```

### AI 引用优化

AI 搜索倾向于引用：
1. **直接回答问题**的内容 → 在页面开头给出答案
2. **结构化信息** → 使用表格、列表、FAQ
3. **权威来源** → 引用数据、案例、专家观点

**FAQ Schema 示例**
```json
{
  "@type": "FAQPage",
  "mainEntity": [{
    "@type": "Question",
    "name": "What is [产品名]?",
    "acceptedAnswer": {
      "@type": "Answer",
      "text": "[一句话定义]"
    }
  }]
}
```

### robots.txt AI 爬虫配置

```
# 允许 AI 搜索爬虫（推荐）
User-agent: ChatGPT-User
Allow: /

User-agent: OAI-SearchBot
Allow: /

User-agent: Bingbot
Allow: /
```

---

## 📈 Launch 后的 SEO 持续优化

### 第1周: 反向链接收割

- [ ] 监测媒体报道，确保都包含链接
- [ ] 将无链接的品牌提及转为有链接
- [ ] 向引用你的文章发感谢邮件（建立关系）

### 第2-4周: 内容扩展

- [ ] 根据搜索数据创建 FAQ 页面
- [ ] 创建 vs 竞品 对比页面
- [ ] 发布使用教程/案例研究

### 持续: 内容更新

- [ ] 每季度更新发布文章（添加新功能、里程碑）
- [ ] 监测排名下滑的页面，及时优化
- [ ] 追踪品牌在 AI 搜索中的引用情况

---

## 🔧 推荐工具

| 工具 | 用途 | 费用 |
|------|------|------|
| Google Search Console | 监测搜索表现 | 免费 |
| Bing Webmaster Tools | Bing 索引 + IndexNow | 免费 |
| Ahrefs / Semrush | 关键词 + 反链分析 | 付费 |
| Schema Markup Validator | 验证结构化数据 | 免费 |

---

## ⚡ 快速行动清单

**Launch 前必做**
- [ ] IndexNow 配置完成
- [ ] 首页/产品页 Title + Meta 优化
- [ ] SoftwareApplication Schema 实施
- [ ] XML Sitemap 提交

**Launch Day 必做**
- [ ] 发布博客文章 + IndexNow 提交
- [ ] 确保所有新页面 15 分钟内被索引

**Launch 后持续**
- [ ] 监测 GSC 数据
- [ ] 收割反向链接
- [ ] 创建长尾内容

---

*基于 SEO & GEO 行动手册 v1.0*
