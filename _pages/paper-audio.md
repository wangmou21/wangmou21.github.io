---
layout: single
title: 每日Arxiv论文阅读笔记
permalink: /paper-audio/
author_profile: true
---
<div id="tip">加载中……</div>
<iframe id="mdFrame" style="width:100%;height:90vh;border:0;display:none;"></iframe>

<script>
function getFileUrl() {
  const now = new Date();
  const y = now.getFullYear();
  const m = String(now.getMonth() + 1).padStart(2, '0');
  const d = String(now.getDate()).padStart(2, '0');
  const date = `${y}-${m}-${d}`;
  // 拼接对方完整路径
  const filePath = `reports/${y}-${m}/Arxiv_Report_${date}.md`;
  // jsdelivr加速md原始链接
  const rawMd = `https://cdn.jsdelivr.net/gh/Sprout-Lee/daily-paper-reading@main/${filePath}`;
  // 调用在线md渲染页面，转为网页嵌入
  const previewUrl = `https://mdview.vercel.app/?url=${encodeURIComponent(rawMd)}`;
  return {previewUrl, date};
}

const res = getFileUrl();
document.getElementById("tip").innerText = `正在加载 ${res.date} 论文日报`;
document.getElementById("mdFrame").src = res.previewUrl;
document.getElementById("mdFrame").style.display = "block";
</script>
