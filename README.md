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

直接打开下面的链接即可播放（需联网加载 CDN 音频）：

> https://cdn.jsdelivr.net/gh/nebula-fangyi/vf-music@main/index.html

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
