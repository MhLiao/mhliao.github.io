# mhliao.github.io

个人学术主页，由 GitHub Pages + Jekyll 驱动。

## 目录结构

```
_data/
  about.yml          # About Me 简介与经历（内容在这里维护）
  publications.yml   # 论文列表（内容都在这里维护）
  news.yml           # News 动态
  awards.yml         # Honors & Awards
index.html           # 页面布局模板（一般不需要改）
assets/              # 论文 teaser 图片
_config.yml          # 站点配置
```

内容与布局已解耦：日常更新**只改 `_data/` 下的 yml 文件**，push 后 GitHub Pages 自动重新构建。

## 如何新增一篇论文

1. 把 teaser 图片放入 `assets/`（如 `assets/NewPaper.png`）
2. 在 `_data/publications.yml` **顶部**追加一段：

```yaml
- title: "论文标题"
  authors: "First Author, Minghui Liao, ..."   # "Minghui Liao" 会自动加粗
  venue: "CVPR, 2026"                          # 或 "arXiv preprint arXiv:xxxx, 2026"
  oral: true                                   # 可选，显示红色 Oral 标记
  image: assets/NewPaper.png
  alt: "NewPaper"
  tags: ["Project Lead"]                       # 可选，蓝色标签，可多个
  links:                                       # 可选，按钮链接，可多个
    - label: "GitHub"
      url: "https://github.com/..."
    - label: "Project Page"
      url: "https://..."
```

3. commit & push，一两分钟后线上自动更新。

## 更新 News / Awards

- News：编辑 `_data/news.yml`，`text` 支持 HTML（如 `<strong>`）
- Awards：编辑 `_data/awards.yml`，只有 `year` 和 `title` 两个字段

## 本地预览（可选）

```bash
gem install jekyll
jekyll serve
# 打开 http://localhost:4000
```

注意：`index.html` 开头的两行 `---` 是 Jekyll 处理标记，**不要删除**；否则模板语法不会被渲染。
