# Book Review Theme

**书评主题** - 专注于书籍评论和推荐的 Hugo 主题,完全优化 SEO 结构化数据。

## 特性

- ✅ **Schema.org Review 标记** - 完整的 Google Rich Results 支持
- ✅ **Schema.org Article 标记** - SEO 优化的文章结构
- ✅ **响应式设计** - 完美适配桌面、平板和手机
- ✅ **内链支持** - 通过 `internal-link` shortcode 支持智能内链
- ✅ **评分系统** - 星级评分可视化显示
- ✅ **书籍元数据** - ISBN、作者、出版年份等完整信息
- ✅ **标签分类** - 支持按标签和类型分类
- ✅ **现代 UI** - 简洁美观的卡片式设计

## 安装

### 方法 1: Git Submodule

```bash
cd your-hugo-site
git submodule add https://github.com/yourusername/hugo-theme-book-review.git themes/book-review
```

### 方法 2: 直接克隆

```bash
cd your-hugo-site/themes
git clone https://github.com/yourusername/hugo-theme-book-review.git book-review
```

## 配置

在 `config.toml` 中添加以下配置:

```toml
baseURL = "https://example.com/"
languageCode = "zh-CN"
title = "我的书评站"
theme = "book-review"

[params]
  description = "分享阅读心得,推荐优质书籍"
  author = "书评作者"
  logo = ""
  main_site_url = "https://main-site.example.com"

[[menu.main]]
  name = "关于"
  url = "/about/"
  weight = 1

[taxonomies]
  tag = "tags"
  genre = "genres"
```

## 使用方法

### 创建书评文章

在 `content/reviews/` 目录下创建 Markdown 文件:

```markdown
---
title: "《三体》书评:科幻与哲学的完美融合"
date: 2024-10-04
book_title: "三体"
author: "刘慈欣"
isbn: "9787536692930"
published_year: "2008"
genre: "科幻小说"
rating: 5
book_image: "/images/books/three-body.jpg"
tags: ["科幻", "三体", "刘慈欣", "硬科幻"]
description: "《三体》是一部震撼人心的硬科幻小说..."
---

## 初读印象

第一次翻开《三体》,我就被刘慈欣构建的宏大宇宙观深深吸引...

{{< internal-link novel-id="123" text="了解更多三体相关内容" >}}
```

### Front Matter 字段说明

| 字段 | 类型 | 必填 | 说明 |
|------|------|------|------|
| `title` | String | ✅ | 书评标题 |
| `date` | Date | ✅ | 发布日期 |
| `book_title` | String | ✅ | 书籍名称 |
| `author` | String | ⭕ | 书籍作者 |
| `isbn` | String | ⭕ | ISBN 编号 |
| `published_year` | String | ⭕ | 出版年份 |
| `genre` | String | ⭕ | 书籍类型 |
| `rating` | Number | ⭕ | 评分 (1-5) |
| `book_image` | String | ⭕ | 书籍封面图片 URL |
| `tags` | Array | ⭕ | 标签列表 |
| `description` | String | ✅ | 书评摘要 (SEO) |
| `read_time` | Number | ⭕ | 阅读时长(分钟) |

### 使用内链 Shortcode

在书评正文中插入内链:

```markdown
{{< internal-link novel-id="123" text="点击阅读完整小说" >}}
```

参数说明:
- `novel-id`: 小说 ID (必填)
- `text`: 链接文本 (必填)

## SEO 优化

### Schema.org Review 结构化数据

本主题自动为每篇书评生成 Schema.org Review 标记,包含:
- 书籍信息 (Book type)
- 评分 (Rating)
- 评论作者
- 评论内容
- 发布日期

### Schema.org Article 结构化数据

同时生成 Article 标记,包含:
- 文章标题和描述
- 作者信息
- 发布和修改日期
- 出版者信息

### Open Graph 标签

自动生成 Facebook/Twitter 分享所需的 Open Graph 标签。

## 目录结构

```
book-review/
├── layouts/
│   ├── _default/
│   │   ├── baseof.html      # 基础模板(含 Schema.org)
│   │   ├── single.html       # 书评详情页
│   │   └── list.html         # 书评列表页
│   ├── partials/
│   │   ├── header.html       # 页头
│   │   ├── footer.html       # 页脚
│   │   └── tags.html         # 标签组件
│   ├── shortcodes/
│   │   └── internal-link.html # 内链组件
│   └── index.html            # 首页
├── static/
│   └── css/
│       └── style.css         # 样式文件
├── exampleSite/              # 示例站点
└── theme.toml                # 主题配置
```

## 浏览器支持

- Chrome (最新版)
- Firefox (最新版)
- Safari (最新版)
- Edge (最新版)

## License

MIT License

## 作者

Your Name

## 贡献

欢迎提交 Issue 和 Pull Request!
