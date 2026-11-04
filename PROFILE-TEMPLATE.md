# 学术主页维护指南

这份指南说明如何通过 GitHub 网页维护你的学术主页。日常只需修改资料文件或上传图片，再提交到 main 分支；GitHub Pages 会自动生成和发布网站。

主页  https://qiyuqin-hust.github.io/

仓库  https://github.com/qiyuqin-hust/qiyuqin-hust.github.io

管理账号  QinWHang    发布分支  main    发布目录  / root

## 先完成一次网页修改

1. 用 QinWHang 登录 GitHub，进入上面的组织仓库，确认分支为 main。
2. 打开要修改的文件，点击铅笔图标 Edit this file。按下面各节的字段修改。
3. 点击 Commit changes，填写简短说明，选择 Commit directly to the main branch，再提交。
4. 到 Actions 查看 pages build and deployment。成功后刷新主页；若仍显示旧内容，可等待几分钟或强制刷新。

## 找到对应的文件

| 想修改的内容 | 文件或目录 |
| --- | --- |
| 姓名 身份 邮箱 学术链接 头像 CV | _config.yml |
| 简介 研究方向 News 教育 奖项 | _data/profile.yml |
| 已录用论文和预印本 | _data/publications.yml |
| 头像和论文方法图 | images/ |
| 简历 PDF | files/ |
| 栏目结构和展示逻辑 | _pages/about.html |
| 侧栏个人信息展示 | _includes/author-profile.html |
| 排版 字号 手机布局 | _sass/_homepage.scss |

修改组织仓库即可更新新主页。QinWHang/qiyuqin.github.io 是此前的个人仓库，不是新地址的发布来源。


## 修改个人资料和经历

打开 _config.yml，修改 author 下的字段。保留两个空格的缩进；不要修改 url、baseurl、repository，除非以后迁移域名或仓库。

```yaml
author:
  name: "Qiyu Qin"
  name_zh: "秦祺钰"
  avatar: "images/portrait.png"
  bio: "Ph.D. Student (Year 1)"
  employer: "Huazhong University of Science and Technology"
  email: "qiyu_qin@hust.edu.cn"
  cv: ""
```

Google Scholar 只保留公开主页链接；ORCID 使用 https://orcid.org/后接编号。空的可选字段用 "" 表示，侧栏会隐藏对应链接。

## 修改简介和教育

在 _data/profile.yml 中修改 intro、research_interests 和 education。intro 支持 Markdown：**文字** 为加粗，[姓名](完整网址) 为链接。教育列表按时间倒序排列。

```yaml
education:
  - institution: "学校名称"
    degree: "学位或学习阶段"
    date: "2026.09 – Present"
    url: "https://学校主页"
    details: "院系及导师信息"
```

硕转博经历应保留为硕士阶段学习后转入博士项目。只有实际取得硕士学位时，才改成已获 M.Sc. 或 M.Eng.；博士在读可写 Ph.D. student 或 degree 后注明 in progress。Year 1 表示博士第一年，之后需手动更新；2030 应注明 expected，表示预计毕业年份。

## 添加一条 News

```yaml
news:
  - date: "2026.11"
    text: 'Our paper **论文简称** has been accepted to **会议名称**.'
```

将新条目放在旧条目前。日期只写你能确认的精度，例如 2026 或 2026.11；不需要推测录用月份。News 列表为空 [] 时，栏目和导航会同时隐藏。

## 修改奖项

awards 是文字列表，每行从短横线开始。填写实际奖项、年份和单位即可；不要加入未经确认的排名或比例。硕士国家奖学金和博士国家奖学金须区分，学业奖学金也应与实际获奖阶段一致。


## 维护论文列表

_data/publications.yml 分为 accepted 和 preprints 两组。已录用论文显示方法图、标题、作者和会议信息；预印本采用紧凑文字引用，并自动加上 (Preprint)。

### 添加已录用论文

```yaml
accepted:
  - title: "论文正式标题"
    authors: "**Qiyu Qin**, 其他作者，按正式署名顺序"
    venue: "会议或期刊名称"
    year: 2026
    note: "CCF-A (Oral)"
    image: "images/paper-name.png"
    image_alt: "一句话描述这张方法图"
    paper: "https://论文正文网址"

```

复制一篇现有论文的整组字段，再放到 accepted 下合适的位置。不要重复写 accepted:。条目之间保持相同缩进，建议按年份倒序排列。

authors 中只加粗本人名字。共同一作、通讯作者等符号必须与正式论文一致。note 没有内容就留空；会议名称、年份及 Oral 或 Spotlight 应按最终录用信息填写。

### 论文标题链接

paper 可填写公开论文正文或正式论文页面的网址，标题会直接链接到该地址。RISE 尚无公开正文时，保持 paper: ""，页面仅显示标题。获得公开链接后再填写即可。

当前论文条目只展示图片和引用信息，不显示 Paper、Code、Figure 等按钮，也不显示正文链接待补提示。note 可填写 CCF-A 或 CCF-A (Oral)，页面会以红色加粗显示。

### 添加预印本

```yaml
preprints:
  - title: "论文标题"
    authors: "**Qiyu Qin**, 已确认的其他作者"
    paper: ""
```

作者列表尚未确定时，authors 可留空；没有公开链接时，paper 可留空。页面仍会显示题目和 (Preprint)。预印本录用后，将该条从 preprints 移到 accepted，并补齐会议、年份和图片等字段。不要在两组中重复保留。


## 替换头像 图片和简历

1. 打开 images 文件夹，选择 Add file → Upload files，上传头像或论文图并提交 main。
2. 头像默认路径为 images/portrait.png。文件名改变时，同步修改 _config.yml 的 author.avatar。
3. 论文图路径填在对应论文的 image 字段。保留完整方法图，点击缩略图可打开原图查看。
4. 公开版简历上传到 files/cv.pdf，再将 author.cv 改为 "files/cv.pdf"，侧栏会自动出现 Curriculum Vitae。
5. 图片仅用于方法展示；paper 字段中的链接应指向真正的论文正文或论文页面。

文件路径区分大小写。网页路径使用正斜线 /，例如 images/rise.png；不要填写本机绝对路径 /Users/...。外部论文或代码使用完整 https:// 链接。

## 遇到问题时检查

| 现象 | 先检查什么 |
| --- | --- |
| 修改后网页没有变化 | 确认改的是组织仓库 main；查看 Actions 是否成功，再刷新。 |
| 图片不显示或下载链接失效 | 核对文件是否已上传、文件名大小写和相对路径是否一致。 |
| 新论文没有出现 | 确认放在 accepted 或 preprints 下，且 YAML 缩进与上一条一致。 |
| 标题没有链接或简历未显示 | 论文标题链接取决于 paper；侧栏简历链接取决于 author.cv。 |
| 构建失败 | 查看 Actions 的失败步骤，重点检查缩进、漏引号、英文冒号和短横线。 |
| 改错内容需要恢复 | 打开文件 → History，找到正确版本，复制回编辑器，再提交 main。 |

## 保留站点配置

```yaml
url: "https://qiyuqin-hust.github.io"
baseurl: ""
repository: "qiyuqin-hust/qiyuqin-hust.github.io"
```

Settings → Pages 的 Source 保持 Deploy from a branch，Branch 为 main，目录为 / root。不要添加 .nojekyll；当前网站依赖 Jekyll 将资料文件转换成网页。

日常内容修改不需要改 HTML 或 CSS。需要新增栏目、调整布局或改变展示逻辑时，再修改 _pages/about.html、_includes 或 _sass/_homepage.scss。
