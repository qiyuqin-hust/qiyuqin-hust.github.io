# 个人资料填写指南

主页直接维护在 **main**。以下均为格式说明，网页只读取 `_config.yml` 和 `_data/*.yml`；这里的示例不会显示到网页。

请整理一版简历和照片，之后可一次性补齐真实资料。未知字段留空，不需要填入占位邮箱或假链接。YAML 文本建议使用双引号；带冒号的文本务必加引号。

## 1. 基本信息：`_config.yml`

在 `author` 下填写：

```yaml
name: "你的英文姓名"
name_zh: "你的中文姓名"
initials: "姓名缩写"
avatar: "images/avatar.jpg"
bio: "你的当前身份"
employer: "你的院系与学校"
location: "城市，国家"
email: "你的公开学术邮箱"
github: "QinWHang"
googlescholar: "你的 Google Scholar 完整 URL"
orcid: "你的 ORCID 完整 URL"
cv: "files/cv.pdf"
```

这些字段位于 `author:` 下面，需要保留两空格缩进。同时更新顶层 `title` 和 `description`。姓名暂依据仓库名写为 Qiyu Qin，收到简历后按本人署名统一。

照片上传到 `images/avatar.jpg`，公开简历上传到 `files/cv.pdf`。也可以使用其他文件名，再同步修改配置。未上传前保持 `avatar` / `cv` 为空；不要提前开启失效链接。

## 2. 简介和经历：`_data/profile.yml`

`intro` 支持 Markdown，可用 `**文字**` 加粗，用 `[导师姓名](https://...)` 插入真实链接。

```yaml
intro: >-
  在这里填写当前身份、学校、导师及研究目标。
  多行文字会合并为一个段落。
research_interests:
  - "真实研究方向一"
  - "真实研究方向二"
news:
  - date: "YYYY.MM"
    text: "一条真实学术动态。"
education:
  - institution: "学校名称"
    degree: "学位与专业"
    date: "YYYY.MM – Present"
    url: ""
    details: "导师等可选信息"
experience:
  - institution: "机构或实验室"
    role: "职位"
    date: "YYYY.MM – YYYY.MM"
    details: "一句话介绍真实项目及个人贡献。"
awards:
  - "奖项名称，颁奖单位，年份"
service:
  - "Reviewer: 会议或期刊，年份"
```

没有内容的列表保持 `[]`。动态、科研经历、奖项和服务会自动隐藏；Education 保留简洁的待更新提示。请按时间倒序整理。

## 3. 论文：`_data/publications.yml`

删除文件中的 `[]`，然后每篇填写一组，按时间倒序排列。**仅填写已核实的论文，不要原样提交以下示例。**

```yaml
- title: "论文真实标题"
  authors: "**Qiyu Qin**, 其他作者，按正式署名顺序"
  venue: "会议 / 期刊 / arXiv"
  year: 2026
  note: ""
  paper: "论文完整 URL"
  code: ""
  project: ""
```

网页只呈现标题、作者、发表信息及实际存在的 Paper / Code / Project 链接。`note` 可填写真实的 Oral、Spotlight 等信息，没有则留空。不需要摘要、配图、引用次数或 BibTeX。

## 可直接发来的资料

- 中文与英文姓名、当前身份、学校、院系、导师。
- 公开邮箱、Scholar、ORCID 等链接。
- 简短自我介绍与研究方向。
- 教育、科研经历、论文、奖项、学术服务。
- 个人照片、公开版 PDF 简历。
