<div align="center">
<img src="./assets/logo.png" width="80" alt="预览"/>

<h1 align="center">WeWe RSS</h1>

免费、开源的微信公众号订阅方式。


![主界面](./assets/preview1.png)

</div>

## 环境变量

### Server服务端

#### `DATABASE_URL` （必填项）
Mysql 数据库地址，例如 `mysql://root:123456@127.0.0.1:3306/wewe-rss`。

#### `AUTH_CODE` （必填项）

服务端接口请求授权码，(`/feeds`路径不需要)。


#### `SERVER_ORIGIN_URL` （必填项）
服务端访问地址，用于RSS生成时使用。

#### `MAX_REQUEST_PER_MINUTE`
每分钟最大请求次数，默认 60。

### Web前端

#### `NEXT_PUBLIC_SERVER_ORIGIN_URL` （必填项）
服务端接口地址，一般跟 `SERVER_ORIGIN_URL` 一致即可。

### 本地开发


1. 安装 nodejs 18 和 pnpm；
2. 修改环境变量`cp ./apps/web/.env.local.example ./apps/web/.env`和`cp ./apps/server/.env.local.example ./apps/server/.env`
3. 执行 `pnpm install && pnpm dev` 即可。⚠️ 注意：此命令仅用于本地开发，不要用于部署！

## 部署

### 本地部署

如果你想本地部署，请使用 `pnpm install &&  pnpm run -r build && pnpm run -r start` 命令(可以配合 pm2 来守护进程，防止被杀死)。
