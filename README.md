# Zhuqing Liu — 个人主页

经典学术模板风格：顶部横幅 + 横向导航条 + 白色内容框 + 左侧照片/联系栏 + News 列表 + 页脚版权行。纯静态，无构建步骤。

```
index.html          Home：照片联系栏、Short Biography、招生通知、研究兴趣、News
research.html       Research：三个方向各一节，带代表工作
publications.html   Publications：34 篇，按年份分组，编号引用格式
grants.html         Grants：汇总表 + 按资助机构分组 + Acknowledgement
teaching.html       Teaching：课程表（含教学评分）+ 招生说明
activities.html     Activities：TPC / 审稿 / 指导 / 受邀报告 / 教育背景
style.css           全站样式（含手机适配与打印样式）
assets/             CV PDF、照片
.nojekyll           告诉 GitHub Pages 跳过 Jekyll
```

## 部署

仓库名要正好是 `6zhuqing.github.io`，把本文件夹**里面**的内容传到仓库根目录（不要连外层文件夹一起传）：

```bash
git init
git add .
git commit -m "Site"
git branch -M main
git remote add origin https://github.com/6zhuqing/6zhuqing.github.io.git
git push -u origin main
```

然后 Settings → Pages → Source 选 `Deploy from a branch`，Branch `main`，目录 `/ (root)` → Save。等 1–2 分钟访问 https://6zhuqing.github.io

## 日常维护

**加 News**（最常用）：在 `index.html` 的 `<ul class="news">` 最上面插一条：

```html
<li>A paper on XXX has been accepted by <b>ICML 2027</b> (acceptance rate: 26%).</li>
```

**加论文**：在 `publications.html` 对应年份的 `<ol class="pubs">` 里加：

```html
<li><span class="title">"<a href="链接">标题</a>,"</span> 作者, <span class="self">Zhuqing Liu</span>, 作者, in Proc. 会议, 地点, 时间 (acceptance rate: xx%).</li>
```

Spotlight/Oral 在 `in` 前面加 `<span class="flag">Spotlight</span>, `。

**加 Grant**：在 `grants.html` 对应机构的 `<ol class="grants">` 里加一条；新机构就复制一整段 `<p class="agency">…</p>` + `<ol class="grants">…</ol>`。记得同步更新顶部汇总表的总额。

**改导航**：六个页面的 `<div id="nav">` 是重复的，加页面要六个文件都改一遍。

## 换成本地照片

现在照片还是引用 Google Sites 的链接，能显示但以后可能失效。把照片存成 `assets/profile.jpg`，然后改 `index.html` 里唯一那处 `<img class="photo" src="...">` 即可。

## 需要你核对的几处

- **News 是我根据简历替你写的**，内容都来自你的论文和 Grant 记录，但顺序和措辞你可以按实际时间调整；有些条目（比如入职 UNT）没有确切日期，我按大致时间排的。
- **课号**：简历写 CSCE 4201，旧主页写 CSCE 4210，我按简历取了 4201。
- **Texas Higher Education Project** 缺正式项目名和编号，有的话补进 `grants.html`。
- **办公室地址**我填的是 Discovery Park 的通用地址，具体门牌号请自己补上（`index.html` 侧栏和横幅各一处）。
- Research 页面三个方向的介绍文字是我根据你的论文写的，可以直接改成你自己的表述。
