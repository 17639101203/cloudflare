# Cloudflare 永久免费二级域名申请指南

更新时间：2026-06-22

## 先明确：Cloudflare 免费给的不是独立域名

Cloudflare 不提供免费注册的独立域名，例如 `example.com`、`example.net` 这类顶级域名仍然需要购买。Cloudflare Registrar 的定位是按注册局和 ICANN 成本价注册/续费域名，不额外加价，但不是免费域名。

你可以永久免费使用的是 Cloudflare 托管产品附带的子域名：

- Cloudflare Pages：`项目名.pages.dev`
- Cloudflare Workers：`你的账号子域名.workers.dev`，Worker 也会有对应访问地址

如果你的目标是“免费获得一个能公网访问的网站地址”，优先推荐使用 Cloudflare Pages 的 `*.pages.dev`。

## 推荐方案：申请 `*.pages.dev`

适合用途：

- 静态网站
- 博客
- 文档站
- 前端项目
- 简单落地页

默认地址格式：

```text
https://你的项目名.pages.dev
```

### 操作步骤

1. 打开 Cloudflare 控制台：

   ```text
   https://dash.cloudflare.com/
   ```

2. 注册或登录 Cloudflare 账号。

3. 进入左侧菜单：

   ```text
   Workers & Pages
   ```

4. 切换到：

   ```text
   Pages
   ```

5. 点击：

   ```text
   Create application
   ```

6. 选择创建方式：

   - 如果代码在 GitHub/GitLab：选择连接 Git 仓库
   - 如果只是先占用并测试一个免费地址：可以用 Direct Upload 上传一个简单静态页面

7. 填写项目名称。

   这个项目名称会影响默认免费域名，例如项目名填写：

   ```text
   my-demo-site
   ```

   部署成功后默认地址通常是：

   ```text
   https://my-demo-site.pages.dev
   ```

8. 配置构建参数。

   常见静态项目可以参考：

   | 项目类型 | 构建命令 | 输出目录 |
   | --- | --- | --- |
   | 纯 HTML/CSS/JS | 留空 | `/` |
   | Vite | `npm run build` | `dist` |
   | Vue CLI | `npm run build` | `dist` |
   | React CRA | `npm run build` | `build` |
   | Hugo | `hugo` | `public` |

9. 点击部署。

10. 部署成功后，Cloudflare 会自动分配 `*.pages.dev` 地址。你可以直接访问这个地址。

## 备选方案：申请 `*.workers.dev`

适合用途：

- API 服务
- 代理服务
- 边缘函数
- 动态响应
- 简单后端逻辑

默认地址一般和 Worker 路由相关，账号会有一个 `workers.dev` 子域名。

### 操作步骤

1. 打开 Cloudflare 控制台：

   ```text
   https://dash.cloudflare.com/
   ```

2. 进入：

   ```text
   Workers & Pages
   ```

3. 创建 Worker。

4. 如果是第一次使用 Workers，Cloudflare 会让你设置 Workers 子域名。

   示例：

   ```text
   myname.workers.dev
   ```

5. 部署 Worker 后，可以通过对应的 `workers.dev` 地址访问。

## 免费额度说明

Cloudflare Pages 和 Workers 都有免费计划，适合个人网站、测试项目、小型服务使用。

需要注意：

- 免费不等于无限制。
- Pages 更适合托管静态网站。
- Workers 更适合运行函数/API。
- 如果访问量、构建次数、函数调用量超过免费额度，可能需要升级付费计划。
- Cloudflare 的产品额度可能会调整，正式上线前建议查看官方 Pricing 和 Limits 页面。

## 常见问题

### 1. 这个免费二级域名会过期吗？

`*.pages.dev` 和 `*.workers.dev` 是 Cloudflare 产品自带的访问域名。只要你的 Cloudflare 账号、项目和服务正常存在，通常可以长期使用，不需要像普通域名一样每年续费。

### 2. 可以把 `pages.dev` 或 `workers.dev` 二级域名转让给别人吗？

它们不是你购买的独立域名资产，而是 Cloudflare 服务地址。不要把它当作可出售、可过户的域名。

### 3. 可以自定义成 `abc.com` 吗？

可以，但 `abc.com` 这类独立域名需要你自己购买。购买后可以在 Cloudflare Pages 或 Workers 里绑定自定义域名。

### 4. 免费地址适合正式项目吗？

个人项目、演示项目、开源文档、博客通常可以。商业项目建议购买自己的独立域名，因为独立域名更可控，也更利于品牌、迁移和长期运营。

### 5. 我应该选 Pages 还是 Workers？

如果你只是要一个网页、博客、文档站，选 Pages。

如果你要写接口、代理、边缘函数，选 Workers。

## 建议流程

最省事的路线：

1. 注册 Cloudflare 账号。
2. 进入 `Workers & Pages`。
3. 创建 Pages 项目。
4. 使用 Git 仓库或 Direct Upload 部署一个静态页面。
5. 获得 `https://项目名.pages.dev`。
6. 后续如果需要品牌域名，再购买独立域名并绑定到 Pages。

## 官方参考

- Cloudflare Pages 文档：<https://developers.cloudflare.com/pages/>
- Cloudflare Pages Direct Upload：<https://developers.cloudflare.com/pages/get-started/direct-upload/>
- Cloudflare Pages Limits：<https://developers.cloudflare.com/pages/platform/limits/>
- Cloudflare Workers `workers.dev` 路由：<https://developers.cloudflare.com/workers/configuration/routing/workers-dev/>
- Cloudflare Workers Pricing：<https://developers.cloudflare.com/workers/platform/pricing/>
- Cloudflare Registrar：<https://www.cloudflare.com/products/registrar/>
