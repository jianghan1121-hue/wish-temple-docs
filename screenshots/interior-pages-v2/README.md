# 任务 08A 内页视觉统一 · 验收截图

- 项目：A Place for Wishes and Kindness
- 分支：`feat/interior-pages-foundation`（基于 main `0e2e302`）
- 采集时间：2026-11-15
- 采集方式：本地 `vite preview` 真实渲染 + 无头 Chrome 截图（非设计稿、非模拟图）
- 截图比例：桌面 1440×900 / 手机 390×844（整页截图）
- 说明：五页均无横向溢出（`scrollWidth == clientWidth`）

## 页面清单

| 页面 | 路由 | 桌面 | 手机 |
|---|---|---|---|
| 关于这里 | `/about` | [about-1440x900.png](about-1440x900.png) | [about-390x844.png](about-390x844.png) |
| 主殿 | `/temple` | [temple-1440x900.png](temple-1440x900.png) | [temple-390x844.png](temple-390x844.png) |
| 我的祈愿 | `/my/wishes` | [my-wishes-1440x900.png](my-wishes-1440x900.png) | [my-wishes-390x844.png](my-wishes-390x844.png) |
| 隐私与使用说明 | `/legal` | [legal-1440x900.png](legal-1440x900.png) | [legal-390x844.png](legal-390x844.png) |
| 404 | `/unknown-route` | [404-1440x900.png](404-1440x900.png) | [404-390x844.png](404-390x844.png) |

## 本轮修复的核心问题

修改前：`.page__body` 与 `.page__title` 被写进同一条 CSS 规则，正文容器因此继承
**衬线字体 + 32px 字号 + 1.3 行高**，并且丢失了 `max-width`，正文实际宽度约 **1120px**（近乎满屏）。

修改后（浏览器计算样式实测）：

| 元素 | 字体 | 字号 | 宽度 | 行高 |
|---|---|---|---|---|
| `.page__body` | Noto Sans SC | 16px | 860px（390 视口 350px） | 28.8px（1.8） |
| `.page__text` | Noto Sans SC | 16px | 同上 | 28.8px |
| `.page__title` | Noto Serif SC | 24–32px | — | 1.3 |

## 各页看点

- **关于这里**：阅读列 860px、无衬线正文、章节标题与段落节奏；列表圆点为木色；末尾两个按钮在手机端满宽。
- **主殿**：两段说明包进「状态块」（surface 底 + hairline + 3px 木色左竖线），只表达"建设中"，无按钮、无伪造功能。
- **我的祈愿**：空状态为白底细边卡片，隐私说明语气平实；无登录/注册/邮箱入口。
- **隐私与使用说明**：草案提示为木色左竖线提示条；章节间 hairline 分隔；`#privacy` / `#terms` 锚点可用。
- **404**：居中版式，说明限宽 46ch，按钮居中且手机端满宽。

## 直接查看图片（raw 链接）

```
https://raw.githubusercontent.com/jianghan1121-hue/wish-temple-docs/main/screenshots/interior-pages-v2/about-1440x900.png
https://raw.githubusercontent.com/jianghan1121-hue/wish-temple-docs/main/screenshots/interior-pages-v2/about-390x844.png
https://raw.githubusercontent.com/jianghan1121-hue/wish-temple-docs/main/screenshots/interior-pages-v2/temple-1440x900.png
https://raw.githubusercontent.com/jianghan1121-hue/wish-temple-docs/main/screenshots/interior-pages-v2/temple-390x844.png
https://raw.githubusercontent.com/jianghan1121-hue/wish-temple-docs/main/screenshots/interior-pages-v2/my-wishes-1440x900.png
https://raw.githubusercontent.com/jianghan1121-hue/wish-temple-docs/main/screenshots/interior-pages-v2/my-wishes-390x844.png
https://raw.githubusercontent.com/jianghan1121-hue/wish-temple-docs/main/screenshots/interior-pages-v2/legal-1440x900.png
https://raw.githubusercontent.com/jianghan1121-hue/wish-temple-docs/main/screenshots/interior-pages-v2/legal-390x844.png
https://raw.githubusercontent.com/jianghan1121-hue/wish-temple-docs/main/screenshots/interior-pages-v2/404-1440x900.png
https://raw.githubusercontent.com/jianghan1121-hue/wish-temple-docs/main/screenshots/interior-pages-v2/404-390x844.png
```
