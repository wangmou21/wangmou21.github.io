---
layout: single
title: 音频领域每日新论文
permalink: /paper-audio/
author_profile: true
---
<div id="loading">正在加载今日论文日报...</div>
<script>
function getTodayPath() {
  const d = new Date();
  const year = d.getFullYear();
  const month = String(d.getMonth() + 1).padStart(2, '0');
  const day = String(d.getDate()).padStart(2, '0');
  const dateStr = `${year}-${month}-${day}`;
  const monthFolder = `${year}-${month}`;
  // md文件地址
  const mdPath = `report/${monthFolder}/Arxiv_Report_${dateStr}.md`;
  // jsdelivr加速链接
  const mdUrl = `https://cdn.jsdelivr.net/gh/Sprout-Lee/daily-paper-reading@main/${mdPath}`;
  return {mdUrl, dateStr};
}

window.onload = function() {
  const info = getTodayPath();
  // 使用开源md在线渲染服务，把md链接转成网页
  const renderUrl = `https://md2pdf.netlify.app/view?url=${encodeURIComponent(info.mdUrl)}`;
  document.getElementById('loading').innerHTML = `
    <iframe src="${renderUrl}" width="100%" height="90vh" border="0"></iframe>
    <p>今日：${info.dateStr}</p>
  `;
}
</script>
