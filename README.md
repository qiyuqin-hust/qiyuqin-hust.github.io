# Qiyu Qin — Academic Homepage

主页地址：**https://qiyuqin-hust.github.io/**

由个人账号 [QinWHang](https://github.com/QinWHang) 管理的 qiyuqin-hust 组织主页，直接维护在 **main** 分支。基于 [RayeRen/AcadHomepage](https://github.com/RayeRen/acad-homepage.github.io) 模板，布局参考 [Yichen Li 的学术主页](https://yichenli-hust.github.io/)。

保留模板的 Jekyll / Sass 结构、圆形头像、左侧个人信息栏和右侧正文，并适配手机屏幕。已录用论文展示方法图、标题、作者、会议或期刊及年份；预印本采用紧凑文字引用。公开论文链接直接放在标题上。

已填写个人资料、头像、研究方向、教育经历、论文、News 和奖项。简历链接可在后续上传 CV 后启用。

## 内容维护

| 内容 | 编辑位置 |
| --- | --- |
| 姓名、身份、单位、邮箱、GitHub、Scholar、头像、CV | `_config.yml` 中的 author |
| 简介、研究方向、动态、教育、经历、奖项、服务 | `_data/profile.yml` |
| 论文列表 | `_data/publications.yml` |
| 栏目模板 | `_pages/about.html` |
| 个性化样式 | `_sass/_homepage.scss` |

完整填写格式见 [PROFILE-TEMPLATE.md](PROFILE-TEMPLATE.md)。YAML 修改后会自动生成页面，无需同步编辑 HTML。

照片上传至 images/portrait.png，简历上传至 files/cv.pdf，再设置 _config.yml 中的 author.avatar 和 author.cv。空字段不生成链接；动态、经历、奖项、服务为空时自动隐藏。

## 本地预览

需要 Ruby（建议 3.2 或更高版本）、Bundler 和编译工具。

运行 bundle install，再运行 bash run_server.sh，打开 http://127.0.0.1:4000 。生成静态文件可运行 bundle exec jekyll build。源文件需要 Jekyll 构建，不能直接双击预览。

## GitHub Pages

仓库：qiyuqin-hust/qiyuqin-hust.github.io。

发布来源：Settings → Pages → Deploy from a branch → main / root。

_config.yml 的 url 为 https://qiyuqin-hust.github.io，baseurl 为空。不要添加 .nojekyll。

## 来源与许可

保留 AcadHomepage 的 MIT LICENSE、Minimal Mistakes 基础样式及 Font Awesome 图标。未复制参考作者的履历、论文或照片；未启用统计追踪或 Scholar 爬虫。
