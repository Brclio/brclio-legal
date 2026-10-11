# Brclio Auth · 政策页面

Brclio Auth 的公开服务介绍、隐私政策与服务条款。依据维护方确认的用途编写：**仅使用 Google 账号登录**，不使用 Google Cloud、BigQuery、Vertex AI、Cloud Storage 等数据权限。

纯静态 HTML/CSS，无安装、构建或数据库依赖。正文直接包含在 HTML 中，无需 JavaScript 或登录即可阅读。页面支持手机、键盘导航、页内目录和打印。

## 公开地址

| Google Auth Platform 字段 | 地址 |
| --- | --- |
| 应用首页 | https://brclio.github.io/brclio-legal/ |
| 应用隐私权政策链接 | https://brclio.github.io/brclio-legal/privacy.html |
| 应用服务条款链接 | https://brclio.github.io/brclio-legal/terms.html |

应用名称：`Brclio Auth`。支持邮箱：`aiyuechuang@gmail.com`。政策生效日期：2026-10-11。

**域名一致性：** 上面的三个地址使用同一个 GitHub Pages 域名。若 OAuth 首页继续填写 `https://brclio.com`，应把本仓库页面部署到该首页所在域，例如 `https://brclio.com/privacy.html` 和 `https://brclio.com/terms.html`，并在该首页介绍 Brclio Auth、加入政策链接。示例的 brclio.com 政策路径不是本仓库已经发布的地址。

也可以为本仓库配置自有域名，并将 OAuth 的首页、隐私政策和条款地址一起改到该站点。需使用关联 Google Cloud 项目的 Owner/Editor 在 Google Search Console 验证相应域名。创建这两份文件不代表 Google 已验证应用或域名。

## Google 权限配置

在 Google Auth Platform → 数据访问中，**仅保留**：

```text
openid
https://www.googleapis.com/auth/userinfo.email
https://www.googleapis.com/auth/userinfo.profile
```

删除其他已勾选的权限，包括截图中的 `iam.test` 及所有不用于登录的敏感/受限范围。截图仅展示了敏感权限的第一页，不能只删除截图可见的十项。此仓库不操作 Google Cloud 配置，控制台清理需在该项目中完成。

应用实际发起的授权请求也必须仅请求这三项范围。常见登录库可使用 `openid email profile` 别名；检查实际请求，不要只修改控制台声明。如果之前已授予过更广权限，应在 Google 账号第三方关联管理中撤销旧授权，再验证新的登录流程。

## 部署与本地预览

GitHub Pages 设置：Source 选择 **Deploy from a branch**，Branch 选择 `main`，Folder 选择 `/ (root)`。仓库包含 `.nojekyll`；每次推送到 `main` 后重新发布。

```bash
python3 -m http.server 4173 --bind 127.0.0.1
```

访问 `http://127.0.0.1:4173/`。可把仓库中三个 HTML 文件和 `assets/` 原样部署到其他静态托管服务；所有内部链接使用相对地址，支持子目录。

## 维护

- `index.html`：说明 Google 登录服务并链接两份政策。
- `privacy.html`：登录信息、用途、Google 数据承诺、共享、保留、撤销与删除。
- `terms.html`：服务范围、账号使用、第三方服务、终止与用户权利。
- `assets/style.css`：共享的 Brclio 页面样式。

文案按基础登录用途制定，不代表对应用后端的审计。维护方应将数据处理、支持与删除流程落实为页面中所述的行为；实际身份验证/存储处理商和留存机制明确后，应进一步补充。增加权限或改变用途时，先更新政策、产品提示和授权请求，不可直接套用当前基础登录声明。

## 官方参考

- [Google 品牌验证与首页、隐私政策要求](https://developers.google.com/identity/protocols/oauth2/production-readiness/brand-verification)
- [Google OAuth 2.0 政策](https://developers.google.com/identity/protocols/oauth2/policies)
- [Google API Services User Data Policy](https://developers.google.com/terms/api-services-user-data-policy)
- [Google OpenID Connect](https://developers.google.com/identity/openid-connect/openid-connect)
- [管理 Google 账号第三方关联](https://myaccount.google.com/connections)

## 许可与设计来源

页面基于 [Brclio Design System](https://github.com/Brclio/brclio-design-system) 的教程模板、Sticky 目录布局及组件调整，采用品牌蓝、黄、红与暖色背景。设计与文案按 CC BY-NC-SA 4.0 提供，署名 Brclio；见 [LICENSE](LICENSE)。品牌标识权利不随该许可转让。
