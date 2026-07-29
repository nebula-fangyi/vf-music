# 蔬菜水果小百科 · 歌单

一个**纯静态、零依赖**的网页音乐播放器，收录 68 首蔬菜水果主题儿歌 / 科普音频（「蔬菜水果小百科」）。

- 播放器页面：`index.html`
- 音频资源：`music/`（68 个 `.mp3`）
- 歌单列表：`playlist.md`

## 功能特性

- 🎵 单文件播放器，无需后端、无需构建，双击即可用
- 🔍 实时搜索（按歌名，如「辣椒」「苹果」）
- ⏮⏯⏭ 上一首 / 播放暂停 / 下一首
- 🔁 三种循环模式：列表循环 · 单曲循环 · 顺序播放
- ☁️ 音频通过 [jsDelivr](https://www.jsdelivr.com/) CDN 从本仓库加速分发

## 在线试听

播放页由网页托管服务（返回 `text/html`）提供，直接打开即可播放（音频仍走 jsDelivr CDN，需联网）：

> https://3818c03d07a64fb7a47ca1d6bfa206c1.gz1.agentos-app.net

> ⚠️ 不要把 `index.html` 放到 jsDelivr 的 `/gh/` 路径托管——它会以 `Content-Type: text/plain` 返回，浏览器只显示源码、无法播放。音频（`.mp3`）走 CDN 不受影响。如需自有域名/更稳定的托管，可改用 GitHub Pages 或对象存储静态网站。

## 目录结构

```
vf-music/
├── index.html      # 播放器页面（由 gen_player.py 生成）
├── music/          # 68 个 mp3 音频文件
├── playlist.md     # 歌单列表（曲序 / 曲名）
├── LICENSE         # 许可证
└── README.md       # 本文件
```

## 本地使用

直接用浏览器打开 `index.html` 即可（音频走 CDN，需联网）。

## 重新生成播放器

`index.html` 由本地脚本 `gen_player.py` 扫描 `music/` 目录生成（按文件名序号排序，约定 `NNN-名称.mp3`）：

```bash
python gen_player.py
```

脚本会输出带搜索框与循环模式的播放器页面，写入 `index.html`。

## 音频 CDN

音频通过 jsDelivr 从本仓库分发，单文件地址格式：

```
https://cdn.jsdelivr.net/gh/nebula-fangyi/vf-music@main/music/<文件名>
```

> 说明：国内访问 jsDelivr 偶有波动属正常现象，可多次刷新或挂代理。

## 许可证

见 [LICENSE](LICENSE)。
