# Whaleal 品牌 Logo 资产

## 设计说明

基于用户提供的**鲸鱼跃浪**设计母版，二次创作为可缩放矢量图形：

- **图形**：鲸鱼跃浪 + 向上箭头，象征数据吞吐与增长
- **主色**：深蓝 `#1a3a5c` / `#143252`、青蓝 `#2eb8d4`、浅蓝 `#7dd3e8` / `#a8e8f5`
- **母版位图**：`whaleal-logo-design.png`（1024×999，保留作参考与导出源）

## 矢量（推荐）

| 文件 | 用途 |
|------|------|
| **`whaleal-icon.svg`** | 方形 icon 标记（favicon、App icon） |
| **`whaleal-logo.svg`** | 横版 icon + Whaleal 字标（导航栏） |
| `../images/whaleal-logo.svg` | 导航引用副本 |
| `../favicon/favicon.svg` | 浏览器矢量 favicon |

## Favicon / PWA（`static/favicon/`）

**已生成并随仓库提交**，`npm run develop` / `npm run build` **不会**重新生成。

| 文件 | 尺寸 | 用途 |
|------|------|------|
| `favicon.png` | 512 | 主 icon、Gatsby manifest、OG 分享图 |
| `favicon-16/32/48…` | 多尺寸 | 浏览器标签 |
| `apple-touch-icon.png` | 180 | iOS 主屏 |
| `favicon.svg` | 矢量 | 现代浏览器（真 SVG，与 `whaleal-icon.svg` 同步） |
| `../favicon.ico` | 16/32/48 | 传统浏览器 `/favicon.ico` |
| `../site.webmanifest` | — | PWA manifest |

**仅当更换品牌母版时**手动重生成并提交：

```bash
FORCE=1 npm run generate:favicons
```

（生成 `.ico` 需本地 `.venv-favicon` + Pillow，见脚本内提示）

## 位图（兼容 / PWA manifest）

| 文件 | 尺寸 | 用途 |
|------|------|------|
| `whaleal-logo-design.png` | 1024×999 | 设计母版位图 |
| `whaleal-icon.png` | 512 | manifest / 社交分享 fallback |
| `whaleal-icon-192.png` | 192 | PWA |
| `whaleal-icon-32.png` | 32 | 小尺寸参考 |
| `../favicon/favicon.png` | 512 | Gatsby manifest（需 PNG） |
| `../favicon/apple-touch-icon.png` | 180 | iOS 主屏 |

## 更新流程

1. 改矢量：编辑 `whaleal-icon.svg`，同步 `whaleal-logo.svg` 内 `<g>` 与 `favicon.svg`
2. 改位图母版：替换 `whaleal-logo-design.png` 后 `sips -Z <px> ...` 重导出 PNG
3. 导航 / SEO 优先用 SVG；manifest 仍用 `favicon.png`
