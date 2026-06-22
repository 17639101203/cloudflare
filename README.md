# cloudflare

Cloudflare Pages 静态小站示例。这个仓库可以直接连接 Cloudflare Pages，发布到免费的 `*.pages.dev` 子域名。

## 文件说明

- `index.html`：页面结构和文案
- `styles.css`：页面样式
- `cloudflare-free-subdomain-guide.md`：Cloudflare 免费子域名申请说明

## Cloudflare Pages 部署配置

连接 GitHub 仓库后，构建设置可以这样填：

```text
Framework preset: None
Build command: 留空
Build output directory: /
Root directory: /
```

部署成功后会获得类似下面的免费地址：

```text
https://你的项目名.pages.dev
```
