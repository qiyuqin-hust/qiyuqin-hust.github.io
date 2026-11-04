# Qiyu Qin — Academic Homepage

基于 [RayeRen/AcadHomepage](https://github.com/RayeRen/acad-homepage.github.io) 模板，布局参考 [Yichen Li 的学术主页](https://yichenli-hust.github.io/)。保留模板的 Jekyll / Sass 结构、圆形头像、左侧个人信息栏和右侧正文，针对移动端调整排版。

网站直接维护在 **main** 分支。Publications 使用紧凑文字列表，仅包含标题、作者、会议或期刊、年份及可选资源链接，不显示论文配图、摘要或引用统计。个人简历、照片和学术资料尚待本人提供，网站未填入示例论文或虚构经历。

## 内容维护

| 内容 | 编辑位置 |
| --- | --- |
| 姓名、身份、单位、邮箱、GitHub、Scholar、头像、CV | `_config.yml` 中的 `author` |
| 简介、研究方向、动态、教育、经历、奖项、服务 | `_data/profile.yml` |
| 论文列表 | `_data/publications.yml` |
| 主体栏目模板 | `_pages/about.html` |
| 个性化样式 | `_sass/_homepage.scss` |

完整填写格式见 [PROFILE-TEMPLATE.md](PROFILE-TEMPLATE.md)。修改 YAML 后，Jekyll 自动生成页面，不需要同步编辑 HTML。

### 上传照片和简历

1. 将照片上传至 `images/avatar.jpg`，将简历上传至 `files/cv.pdf`。
2. 在 `_config.yml` 设置 `author.avatar: "images/avatar.jpg"` 和 `author.cv: "files/cv.pdf"`。
3. 提交到 `main`。头像会替换当前字母占位，侧栏会出现 CV 链接。

照片、CV 或社交字段为空时不会生成失效链接。News、Research Experience、Honors & Awards 和 Academic Service 为空时自动隐藏，导航同步隐藏。

## 本地预览

需要 Ruby（建议 3.2 或更高版本）、Bundler 和编译工具：

```sh
bundle install
bash run_server.sh
```

打开 `http://127.0.0.1:4000`。本地脚本覆盖 `baseurl`；生产配置仍保留 GitHub 项目站点路径。此版本需要 Jekyll 构建，不能通过双击源文件预览。

```sh
bundle exec jekyll build
```

## GitHub Pages

仓库为 `QinWHang/qiyuqin.github.io`，因此默认项目站点地址为：

**https://qinwhang.github.io/qiyuqin.github.io/**

GitHub Pages 使用 `main` 分支的根目录（Settings → Pages → Deploy from a branch → main / root）。如果尚未启用 Pages，需要先启用。不要添加 `.nojekyll`，源文件需要 Jekyll 渲染。若未来改为用户站点仓库或绑定域名，请同步更新 `_config.yml` 的 `url`、`baseurl`。

## 来源与许可

- 模板：[RayeRen/AcadHomepage](https://github.com/RayeRen/acad-homepage.github.io)，MIT；保留原 `LICENSE`。
- 基础样式继承 Minimal Mistakes；图标沿用模板中的 Font Awesome。
- 未复制参考主页作者的履历、论文或照片；未启用统计追踪或 Scholar 爬虫。
