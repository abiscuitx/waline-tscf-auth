# waline-tscf-auth

[waline-tscf](https://github.com/abiscuitx/waline-tscf)的OAuth认证后端，支持多种社交平台登录：GitHub
、Twitter、Facebook、Google、微博 (Weibo)、QQ。

> waline-tscf：一个基于 [Waline](https://github.com/walinejs/waline) 的评论系统，专为 [腾讯云函数 SCF](https://cloud.tencent.com/product/scf) 部署场景优化，增强后端性能能力，优化个人博客的前端样式。

## 快速部署

部署到 Vercel ：

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/import/project?template=https://github.com/abiscuitx/waline-tscf-auth)

## 环境变量配置

运行前需要根据使用的社交平台配置相应的环境变量：

### GitHub 登录
```
GITHUB_ID=你的GitHub应用ID
GITHUB_SECRET=你的GitHub应用密钥
```

### Twitter 登录  
```
TWITTER_ID=你的Twitter应用ID
TWITTER_SECRET=你的Twitter应用密钥
LEAN_ID=LeanCloud应用ID
LEAN_KEY=LeanCloud应用Key
```

### Facebook 登录
```
FACEBOOK_ID=你的Facebook应用ID
FACEBOOK_SECRET=你的Facebook应用密钥
```

### Google 登录
```
GOOGLE_ID=你的Google应用ID
GOOGLE_SECRET=你的Google应用密钥
```

### 微博登录
```
WEIBO_ID=你的微博应用ID
WEIBO_SECRET=你的微博应用密钥
```

### QQ 登录
```
QQ_ID=你的QQ应用ID
QQ_SECRET=你的QQ应用密钥
```

## 如何调用


### 登录重定向
```
GET /<平台名>?redirect=<回调地址>&state=<状态参数>
```

### 获取用户信息
```
GET /<平台名>?code=<授权码>
```

例如：
- GitHub: `GET /github?code=authorization_code`
- 微博: `GET /weibo?code=authorization_code`

## 注意事项

1. **Twitter 特殊要求**：Twitter 认证需要额外配置 LeanCloud 存储服务
2. **回调地址**：需要在各社交平台的开发者控制台中正确配置回调地址
