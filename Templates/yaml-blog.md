---
title: <%* tR += tp.file.title %>
date: <%* tR += tp.date.now("YYYY-MM-DD") %>
lastmod: <%* tR += tp.date.now("YYYY-MM-DD") %>
draft: false
categories:
    - 
tags: []
slug: <%* 
  const title = tp.file.title;
  const slug = title
    .toLowerCase()
    .replace(/[\s\u4e00-\u9fa5]+/g, '-')      // 中英文空格/汉字转连字符
    .replace(/[^\w\-]/g, '')                   // 移除特殊字符（保留字母、数字、连字符）
    .replace(/-+/g, '-')                       // 合并多个连字符
    .replace(/^-|-$/g, '');                    // 去掉首尾连字符
  tR += slug;
%>
comments: true
---

<%* 
// 可选：自动在正文插入标题（避免重复）
// await tp.file.cursor(1);
// tR += "# " + tp.file.title + "\n\n";
%>