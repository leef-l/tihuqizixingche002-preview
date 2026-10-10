# 鹈鹕骑自行车002 · 静态展示页

一个零依赖的纯静态展示页，用来展示「鹈鹕骑自行车」的 SVG 插画，并提供深浅色主题切换与插画下载。

## 用途

- 在浏览器中直接预览 `pelican-on-bicycle.svg` 插画。
- 支持深浅色主题切换，自适应桌面与手机（竖屏 / 横屏）。
- 提供「下载 SVG」按钮，可直接保存原始矢量文件。

## 文件结构

```
.
├── index.html                 # 展示页：内联样式与内联脚本，无外部 CDN 依赖
├── pelican-on-bicycle.svg     # 主插画（由插画模块产出，页面通过 ./pelican-on-bicycle.svg 外链引用）
└── README.md                  # 本说明
```

说明：

- 主展示始终使用对 `./pelican-on-bicycle.svg` 的外链引用。
- `index.html` 另内置一份内联 SVG 占位示例，主插画文件缺失时页面不会空白。
- 当前仓库中的 `pelican-on-bicycle.svg` 是最小占位插画；插画模块产出正式插画后，直接替换同名文件即可，页面无需改动。

## 本地预览

在仓库根目录执行：

```bash
python3 -m http.server 8000
```

然后在浏览器访问（地址占位，按本机实际端口替换）：

- 页面：`http://localhost:8000/`
- 插画：`http://localhost:8000/pelican-on-bicycle.svg`

用 `curl` 快速确认两者可访问：

```bash
curl -sI http://localhost:8000/ | head -1
curl -sI http://localhost:8000/pelican-on-bicycle.svg | head -1
```

## 说明

- 页面无构建步骤，直接把 `index.html` 和 `pelican-on-bicycle.svg` 放在同一目录即可。
- 不引用任何网络字体、脚本或图片，离线可用。
