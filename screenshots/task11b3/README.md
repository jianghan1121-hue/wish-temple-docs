# 任务 11B-3 · B+C 阶段视觉验收截图

- 分支：`feature/11b-stage-a-wish-ritual`
- 提交：`c9d180c` `feat: rebuild incense visuals with bronze censer and lighting sequence`
- 采集：2026-11-22，本地 Vite dev 真实渲染，无头 Chrome，2x 采样

## 文件

| 文件 | 内容 | 说明 |
|---|---|---|
| `01-ignite-200ms.png` | 点燃 200ms | 香体已出现、火点尚未亮起 |
| `02-ignite-700ms.png` | 点燃 700ms | 火点由暗到亮、首缕烟开始出现 |
| `03-burning.png` | 稳定燃烧 | 完整形态：三足炉 / 香体 / 火点 / 烟 |
| `04-dialog-1440.png` | 弹层实景（桌面 1440） | 点燃步骤整体观感 |
| `05-quiet-static.png` | 静心步骤 | 静态终态（与 reduced-motion 终态一致） |
| `06-dialog-390.png` | 弹层实景（手机 390） | 移动端比例与位置 |

## 本次改动要点

- 香炉：传统三足鼎式（折沿 / 收颈 / 鼓腹 / 收底 / 锥形三足 + 足端），铜褐色 #6E5F4A 系，纯色分层
- 香头：三层同心（炭化 / 余烬 / 亮点），头身比由 3.56 倍降到 2.4 倍
- 烟雾：三条分离的 S 曲线，延伸至 viewBox 33%，仅有 1 个 blur(0.5px)
- 点燃：新增一次性动画（香体出现 320ms → 火点 260–1160ms → 首缕烟 520–1720ms → 稳定循环）
- 业务计时、onLit、ritualLit / hallLit 均未改动
