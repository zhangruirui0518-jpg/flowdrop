# FlowDrop · 星语心流

单文件治愈系专注网页应用：把今晚的心愿写下来，看它化作星光粒子，
经倒置漏斗缓缓沉降，在底部堆成发光沙丘；游荡弹幕全程陪伴。

## 在线访问

GitHub Pages：https://zhangruirui0518-jpg.github.io/flowdrop/
（需在仓库 Settings → Pages → Source 选择 `main` 分支 `/root` 后生效）

## 文件

| 文件 | 说明 |
| --- | --- |
| `index.html` | 应用本体（HTML/CSS/JS 单文件，零依赖，无外部请求） |
| `background.mp3` | 背景音乐（必须与 index.html 放同一目录，相对路径 `./background.mp3`） |
| `dev-server.js` / `package.json` | 仅本地预览用（`npm run dev` → http://127.0.0.1:7100/），上线不需要 |

## 本地预览

```bash
npm run dev
# 打开 http://127.0.0.1:7100/
```

## 特性

- 文字像素解构为粒子云：动态采样率（软上限 2400），对象池复用，睡眠态零物理
- 第一层物理：几乎贯穿全屏的倒置漏斗漏沙，漏速严格跟随倒计时
- 第二层物理：底部沙丘真实碰撞（砸落反弹 / 向低处滚落 / 翻滚入睡，高度场 O(1) 碰撞查询）
- 游荡弹幕：9 组中英双语陪伴文案随机抽取，屏幕边缘与漏斗斜边物理反弹，动态频率（里程碑必触发 + 冲刺加速）
- 时间与速度联动：speedFactor = clamp(√(25÷分钟数), 1, 3)，倒计时越短剥离/重力/初速越快
- 防分心三件套：停滞三段提醒、切屏灰白 + 极轻柔合成叹息 + 扣 20% 粒子、beforeunload 拦截
- 音频：BGM 用相对路径 `./background.mp3`；叹息声与完成风铃为 Web Audio API 纯代码合成
