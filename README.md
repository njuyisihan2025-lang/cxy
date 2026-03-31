# 中国各省储能项目 IRR 地图页面（GitHub 小白保姆教程）

你不需要会编程，按下面步骤点点点就可以发布成公网网址。

---

## 0. 你最终会得到什么？

发布成功后，你会得到一个公网网址：

- `https://你的GitHub用户名.github.io/你的仓库名/`

比如用户名是 `zhangsan`，仓库名是 `energy-map`，网址就是：

- `https://zhangsan.github.io/energy-map/`

---

## 1. 先注册 GitHub 账号（只做一次）

1. 打开：`https://github.com/`
2. 点右上角 **Sign up**。
3. 按提示填写邮箱、密码、用户名。
4. 完成邮箱验证。

---

## 2. 在 GitHub 上新建一个仓库（Repository）

1. 登录 GitHub 后，点右上角 `+`，选择 **New repository**。
2. `Repository name` 填一个名字（例如：`energy-map`）。
3. 选择 **Public**（公开仓库，GitHub Pages 最省事）。
4. 点 **Create repository**。

> 创建后会看到仓库首页，地址形如：
> `https://github.com/你的用户名/energy-map`

---

## 3. 把本地项目上传到 GitHub（复制命令即可）

> 下面命令在你电脑的“终端/命令行”执行。`<...>` 部分替换成你自己的。

```bash
cd /workspace/cxy
git remote remove origin 2>/dev/null || true
git remote add origin https://github.com/<你的用户名>/<你的仓库名>.git
git push -u origin work
```

如果你报错“找不到 work 分支”，就用这组：

```bash
cd /workspace/cxy
git branch -M main
git push -u origin main
```

---

## 4. 开启 GitHub Pages（网页发布开关）

1. 进入你的仓库页面。
2. 点上方 **Settings**。
3. 左侧找到 **Pages**。
4. 在 `Build and deployment` 区域，把 `Source` 选成 **GitHub Actions**。

这个项目已经内置自动发布文件：

- `.github/workflows/deploy-pages.yml`

它会在你推送代码后自动发布网页。  

---

## 5. 等待自动发布完成（1~3 分钟）

1. 打开仓库的 **Actions** 标签页。
2. 你会看到一个工作流：`Deploy static site to GitHub Pages`。
3. 等它变成绿色对勾（成功）。

如果是红色叉：点进去查看失败步骤，截图发我，我继续带你修。

---

## 6. 打开公网网址

发布成功后，访问：

- `https://<你的用户名>.github.io/<你的仓库名>/`

这就是你要的公网可访问网址。

---

## 7. 常见问题（小白最容易卡住）

### Q1：提示没有权限 push？
A：你可能没登录 GitHub，或没配置令牌（Token）。最简单办法：
- 使用 GitHub Desktop 上传（图形界面，不用命令行）；
- 或按 GitHub 提示创建 Personal Access Token 当密码使用。

### Q2：页面是空白？
A：大多是网络拦截了 `cdn.jsdelivr.net`。可后续把 ECharts 依赖改成“本地静态文件”版本，彻底避免 CDN 问题。

### Q3：网址 404？
A：通常是 Pages 还在部署，等 1~3 分钟再刷新；或检查仓库是否为 Public、Pages Source 是否为 GitHub Actions。

---

## 8. 本地预览（可选）

如果你想先在本机看效果：

```bash
cd /workspace/cxy
python -m http.server 8765 --bind 127.0.0.1
```

浏览器打开：

- `http://127.0.0.1:8765/index.html`

---

## 9. 你的专属命令（用户名：`njuyisihan2025-lang`，仓库：`cxy`）

直接复制执行：

```bash
cd /workspace/cxy
git remote remove origin 2>/dev/null || true
git remote add origin https://github.com/njuyisihan2025-lang/cxy.git
git push -u origin work
```

如果提示没有 `work` 分支，则改用：

```bash
cd /workspace/cxy
git branch -M main
git push -u origin main
```

发布成功后你的网址就是：

- `https://njuyisihan2025-lang.github.io/cxy/`
