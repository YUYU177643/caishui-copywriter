# 财税文案神器 - GitHub Pages 免费部署教程

本教程教你如何把 `index.html` 免费部署到 GitHub Pages，生成一个 `https://你的用户名.github.io/仓库名` 的公网链接，手机和电脑都能打开，也能直接分享给团队。

> 新版功能：8 种文案风格、智能组合引擎、一键复制全部、语音输入降级提示、需求自适应。

## 前置准备

1. 一个 GitHub 账号（免费注册：https://github.com/signup）
2. 已经下载好的 `index.html`、`README.md`、`DEPLOY.md` 三个文件
3. 一个大模型 API 密钥（可选，后面会讲怎么免费领）

---

## 第一步：注册 GitHub 账号

1. 打开 https://github.com/signup
2. 用邮箱注册，按提示完成验证
3. 记住你的用户名，比如 `zhangsan`

---

## 第二步：创建仓库

1. 登录 GitHub 后，点击右上角 `+` → `New repository`
2. Repository name 填：`caishui-copywriter`
3. 选择 `Public`（公开仓库才能用免费 GitHub Pages）
4. 勾选 `Add a README file`
5. 点击 `Create repository`

---

## 第三步：上传网页文件

1. 进入刚创建的仓库
2. 点击 `Add file` → `Upload files`
3. 把 `caishui-copywriter-web.html` 文件拖进去
4. 页面拉到底，点击 `Commit changes`

> 注意：文件名必须是 `caishui-copywriter-web.html`，如果 GitHub 自动改名了请改回来。

---

## 第四步：开启 GitHub Pages

1. 在仓库页面点击 `Settings`（顶部标签）
2. 左侧菜单找到 `Pages`
3. 在 `Build and deployment` 下面：
   - Source 选择 `Deploy from a branch`
   - Branch 选择 `main`，文件夹选择 `/(root)`
4. 点击 `Save`
5. 等 1-3 分钟，页面顶部会出现绿色提示：
   ```
   Your site is live at https://zhangsan.github.io/caishui-copywriter/
   ```
   这个链接就是你的公网地址。

---

## 第五步：配置大模型 API 密钥

网页打开后，点击 `API 设置 / 飞书同步 / 演示模式`，填入以下信息：

### 推荐方案 A：字节豆包/火山引擎（国内速度快）

1. 打开 https://console.volcengine.com/
2. 注册账号并实名认证
3. 进入「方舟大模型」控制台
4. 创建 API Key，复制密钥
5. 接口地址填：`https://ark.cn-beijing.volces.com/api/v3`
6. 模型名称填：`doubao-seed-2-1-pro-260628`（具体 Model ID 以方舟控制台「模型广场」页面显示为准）

> 新用户有免费额度，足够日常用。

### 推荐方案 B：阿里云通义千问

1. 打开 https://dashscope.aliyun.com/
2. 用支付宝/淘宝账号登录
3. 进入「API-KEY 管理」，创建 API Key
4. 接口地址填：`https://dashscope.aliyuncs.com/compatible-mode/v1`
5. 模型名称填：`qwen-plus`

> 通义千问新用户也有免费额度。

### 推荐方案 C：智谱 AI

1. 打开 https://open.bigmodel.cn/
2. 注册并获取 API Key
3. 接口地址填：`https://open.bigmodel.cn/api/paas/v4`
4. 模型名称填：`glm-4-flash`

> 有免费模型可用。

填好后点击「保存设置」，然后点「立即生成文案」就能用了。

---

## 第六步：分享给团队

1. 把 `https://你的用户名.github.io/caishui-copywriter/` 这个链接发到微信群/钉钉/飞书
2. 团队成员打开后，在自己的浏览器里填入 API 密钥即可使用
3. 如果担心每个人都填一遍麻烦，可以让一个人填好后，把浏览器页面收藏或保存为书签（密钥存在浏览器本地）

---

## 常见问题

### 1. 语音输入不能用？

GitHub Pages 是 HTTPS，已经满足大部分浏览器的语音识别要求。如果还是不行：

- 用 Chrome 浏览器或微信内置浏览器
- 确保允许了麦克风权限
- 苹果 Safari 对 Web Speech API 支持不好，建议换 Chrome
- 点击页面上的「按住说话」时，如果浏览器弹出权限请求，必须点「允许」

### 2. 飞书同步失败？

- 检查飞书 App ID 和 App Secret 是否填对
- 检查飞书自建应用是否开通了「创建及编辑新版文档」权限
- 部分浏览器会拦截跨域请求，换 Chrome 再试

### 3. 打开页面是 404？

- 检查仓库是否公开
- 检查文件名是否为 `caishui-copywriter-web.html`
- GitHub Pages 开启后需要等 1-3 分钟才能访问

### 4. 不想用 GitHub Pages，还有其他免费方案吗？

有，最推荐 **Netlify Drop**，不需要注册账号：

#### Netlify Drop（无需账号，30 秒搞定）

1. 打开 https://app.netlify.com/drop
2. 把 `caishui-copywriter-web.html` 文件直接拖进页面
3. 等 10 秒左右，会自动生成一个 `https://xxx.netlify.app` 的链接
4. 复制这个链接，发到微信即可

> 注意：Netlify Drop 的链接是永久的（只要不长期没人访问），不需要 GitHub 账号，也不需要实名认证。

其他方案：
- **Vercel**：需要绑定 GitHub 账号
- **Cloudflare Pages**：需要绑定 GitHub 账号

这些平台的部署方式大同小异。

---

## 团队内部快速使用（不公开部署）

如果你不想部署到公网，只想把工具发给团队几个人用，可以用预填密钥的版本：

- `caishui-copywriter-web-team.html`：API 密钥已预填，打开就能直接生成文案
- 适合通过微信/钉钉/邮件发给团队成员
- **不要把这个版本上传到 GitHub 公开仓库或任何公开链接**

如果要把工具放到公网上，请用 `caishui-copywriter-web.html`，让每个人自己填密钥。

---

## 安全提示

- API 密钥只保存在用户自己浏览器的 localStorage 中，不会上传到 GitHub 或任何服务器
- 不要把密钥写在 HTML 文件里再上传到公开仓库，否则别人能看到
- 如果密钥泄露，请到对应平台立刻重置
