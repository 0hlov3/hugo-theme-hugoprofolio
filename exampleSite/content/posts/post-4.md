+++
title = 'Post 4 - Canonical URL'
date = 2025-01-18T10:00:00-07:00
draft = false
canonicalURL = "https://example.com/my-original-article"
tags = ['red','green']
+++

A canonical link (or canonical tag) is an HTML element (<link rel="canonical">) that informs search engines about the preferred version of a webpage. It is especially useful when you have duplicate or similar content published across multiple URLs or platforms. By specifying a canonical link, you help search engines identify and prioritize the original or authoritative source of the content, preventing issues like:

- Duplicate content penalties: Search engines might penalize sites with duplicate content if the original source is unclear. 
- Split ranking signals: Traffic, backlinks, and other ranking signals might get distributed across multiple URLs, reducing the impact on the preferred version.

For example, if you publish an article on your personal blog and also repost it on Medium, you can set a canonical link on the Medium post to point to your original blog post. This tells search engines to index and rank the original blog post over the Medium one.

### Example of a Canonical Link
```html
<link rel="canonical" href="https://example.com/my-original-article" />
```

Why Use Canonical Links?

1. SEO Optimization: Avoids duplicate content issues and consolidates ranking signals.
2. Content Attribution: Ensures proper credit to the original source.
3. User Experience: Directs users to the most authoritative and relevant page.