# cloudflare

Cloudflare Pages 静态小站示例。这个仓库可以直接连接 Cloudflare Pages，发布到免费的 `*.pages.dev` 子域名。

## 文件说明

- `public/index.html`：页面结构和文案
- `public/styles.css`：页面样式
- `public/cloudflare-free-subdomain-guide.md`：Cloudflare 免费子域名申请说明
- `wrangler.jsonc`：Cloudflare Workers 静态资源部署配置

## Cloudflare Pages 部署配置

连接 GitHub 仓库后，构建设置可以这样填：

```text
Framework preset: None
Build command: 留空
Build output directory: public
Root directory: /
```

部署成功后会获得类似下面的免费地址：

```text
https://你的项目名.pages.dev
```

## Cloudflare Workers 部署配置

如果使用 Workers 静态资源部署，仓库里的 `wrangler.jsonc` 已经指定只上传 `public` 目录：

```jsonc
{
  "assets": {
    "directory": "./public"
  }
}
```

这样不会把 `.git`、`.idea` 等仓库或本地配置目录当成网站文件上传。
