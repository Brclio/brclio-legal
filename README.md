# Brclio·AI·编程1v1辅导 · 政策页面

Brclio·AI·编程1v1辅导 的公开应用介绍、隐私政策与服务条款。服务用途为**编程、AI、AIGC 与 Codex、Claude 等工具的一对一教学**；AI 是教学主题。Google 数据权限**仅用于基础账号登录**，不使用 Google Cloud、BigQuery、Vertex AI、Cloud Storage 等数据权限。

纯静态 HTML/CSS，无安装、构建或数据库依赖。正文直接包含在 HTML 中，无需 JavaScript 或登录即可阅读。页面支持手机、键盘导航、页内目录和打印。

## 公开地址

| Google Auth Platform 字段 | 地址 |
| --- | --- |
| 应用首页 | https://pages.brclio.com/brclio-legal/ |
| 应用隐私权政策链接 | https://pages.brclio.com/brclio-legal/privacy.html |
| 应用服务条款链接 | https://pages.brclio.com/brclio-legal/terms.html |

应用名称：`Brclio·AI·编程1v1辅导`。支持邮箱：`aiyuechuang@gmail.com`。政策生效日期：2026-10-12。

**本应用的 OAuth 首页应填写上表的完整路径**，不要填写品牌站 `https://brclio.com` 或 Pages 根目录 `https://pages.brclio.com/`。Google 审核的是控制台所填首页；修改本仓库不会改变另一个网站的访问方式和内容。这个应用专用首页在静态 HTML 中直接提供中英文用途、登录流程、所需信息、维护方、联系邮箱和政策链接，无需登录或 JavaScript。

**域名一致性：** 三个地址都在 `pages.brclio.com`，授权域名填写并验证 `brclio.com`。组织 Pages 已绑定该自有域名；原 `brclio.github.io` 地址会重定向，因此配置时直接使用上表的 HTTPS 地址。

也可以为本仓库配置自有域名，并将 OAuth 的首页、隐私政策和条款地址一起改到该站点。需使用关联 Google Cloud 项目的 Owner/Editor 在 Google Search Console 验证相应域名。创建这两份文件不代表 Google 已验证应用或域名。

## 品牌验证问题修复

若改名后 Google 提示名称不一致、用途不足、隐私政策内容不足或首页不可公开读取：

1. 将品牌塑造 → 应用首页改为 `https://pages.brclio.com/brclio-legal/`，保存。
2. 核对政策地址与上表一致，且应用名称为 `Brclio·AI·编程1v1辅导`。
3. 用未登录的浏览器直接访问这三个地址，确认介绍和全文可阅读。
4. 在“查看问题”面板选择“我已解决相关问题”，重新运行品牌验证，以 Google 返回的最新状态为准；通过后发布新品牌草稿。

改名后的页面明确区分教学服务与 Google 登录用途。若仍出现 AI/NCII 条款提示，应核对实际服务和 Google 返回的具体结果，必要时提交真实教学用途说明申请人工复核；文案修改不等于已通过审核。

此改动无需修改 OAuth 客户端的回调地址、JavaScript 来源或登录凭据；不要将介绍页当作登录回调地址。

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

- `index.html`：完整应用名称、编程/AI/AIGC 教学用途、Google 登录用途与政策入口。
- `privacy.html`：登录信息、用途、Google 数据承诺、共享、保留、撤销与删除。
- `terms.html`：服务范围、账号使用、第三方服务、终止与用户权利。
- `assets/style.css`：共享的 Brclio 页面样式。

文案依据维护方确认的教学主题与基础登录用途制定，不代表对应用后端或授课工具的审计。维护方应将数据处理、支持与删除流程落实为页面中所述的行为；实际身份验证/存储处理商和留存机制明确后，应进一步补充。增加权限、内置 AI 对话或改变学习材料处理方式时，先确认实际数据流、处理商和保留机制，再更新政策、产品提示和授权请求，不可直接套用当前基础登录声明。

## 官方参考

- [Google 品牌验证与首页、隐私政策要求](https://developers.google.com/identity/protocols/oauth2/production-readiness/brand-verification)
- [Google OAuth 2.0 政策](https://developers.google.com/identity/protocols/oauth2/policies)
- [Google API Services User Data Policy](https://developers.google.com/terms/api-services-user-data-policy)
- [Google OpenID Connect](https://developers.google.com/identity/openid-connect/openid-connect)
- [管理 Google 账号第三方关联](https://myaccount.google.com/connections)

## 许可与设计来源

页面基于 [Brclio Design System](https://github.com/Brclio/brclio-design-system) 的教程模板、Sticky 目录布局及组件调整，采用品牌蓝、黄、红与暖色背景。设计与文案按 CC BY-NC-SA 4.0 提供，署名 Brclio；见 [LICENSE](LICENSE)。品牌标识权利不随该许可转让。
