# Phishing Detective（钓鱼网址识别游戏）

这是 Lesson 2 的钓鱼网址识别小游戏。玩家每局会随机判断 10 个网址，答题后可立即看到解释。

> 注意：作业原文要求的文件名拼写为 `phising_url.json`（少一个 h），本项目按原要求保留了该名称。

## 文件说明

- `index.html`：完整的游戏界面、样式和逻辑，无需安装依赖。
- `phising_url.json`：20 道安全演示题目，包含合法网址和使用 `.example` 保留域名的钓鱼示例。

## 使用方法

### 方法一：直接双击（最简单）

1. 确保电脑可以访问 GitHub。
2. 双击 `index.html`，浏览器会从本仓库的 GitHub Raw 地址读取题库。
3. 点击“开始调查”，选择“安全网站”或“钓鱼陷阱”。

### 方法二：运行本地服务器（最稳定）

在本文件夹打开 PowerShell，执行：

```powershell
python -m http.server 8000
```

然后在浏览器打开 <http://localhost:8000>。结束时在 PowerShell 中按 `Ctrl+C`。

如果没有 Python，也可以使用 VS Code 的 **Live Server** 扩展打开 `index.html`。

### 方法三：GitHub Pages 在线发布

1. 打开 GitHub 仓库的 **Settings → Pages**。
2. 在 **Build and deployment** 中选择 **Deploy from a branch**。
3. Branch 选择 `main`，目录选择 `/ (root)`，点击 **Save**。
4. 等待约 1–3 分钟后，访问：<https://smallcarrotqwq.github.io/fishing_game/>

## 修改题库

编辑 `phising_url.json`，每道题必须包含：

```json
{
  "url": "https://example.com",
  "isPhishing": false,
  "explanation": "这里填写判断理由。"
}
```

- `isPhishing: true` 表示钓鱼网址。
- `isPhishing: false` 表示合法网址。
- 题库至少需要 10 道题。
- 请勿加入真实的恶意网址；建议使用 `.example` 保留域名制作教学示例。

修改并推送后，直接双击打开的版本和 GitHub Pages 版本都会读取最新题库。
