# 色板配方全集

三套主配方，附场景变体与组件用法。所有色值可直接复制。

---

## 配方 A：深色数据看板

### 完整变量

```css
:root {
  /* 背景层级：同一色相 H220，明度递增 */
  --bg:       #0b1220;   /* 页面底   L8  */
  --panel:    #121a2b;   /* 卡片     L12 */
  --panel2:   #182338;   /* 卡片上层 L16 */
  --border:   #243049;   /* 描边     L21 */

  /* 文字 */
  --text:     #e8eefc;   /* 正文，对比度 16.11 */
  --muted:    #93a0b8;   /* 次要，对比度 6.59  */

  /* 语义 */
  --accent:   #4ea1ff;   /* 强调/交互，6.51 */
  --up:       #3dd68c;   /* 上涨/正向，9.27 */
  --down:     #ff6b7a;   /* 下跌/负向，6.32 */
  --warn:     #f5c542;   /* 警告 */

  /* 半透明分层（替代新增色值） */
  --line-strong:#ffffff1f;
  --line-soft:  #ffffff08;
}
```

### 背景光晕

大面积低对比径向渐变，制造纵深，不影响文字可读：

```css
body {
  background:
    radial-gradient(1200px 600px at 10% -10%, #1a2744 0%, transparent 55%),
    radial-gradient(900px 500px at 100% 0%, #1b1633 0%, transparent 45%),
    var(--bg);
}
```

### 卡片

```css
.card {
  background: linear-gradient(180deg, var(--panel) 0%, var(--panel2) 100%);
  border: 1px solid var(--border);
  border-radius: 16px;
  box-shadow: 0 10px 30px rgba(0,0,0,.25);
}
```

### 国内涨跌版

仅交换两个变量，其余不动：

```css
--up:   #ff5a6a;   /* 红涨，6.17 */
--down: #22c55e;   /* 绿跌，8.22 */
```

---

## 配方 B：浅色分析报告

### 完整变量

```css
:root {
  --bg:     #f5f6f8;   /* 页面底 H220 L97 */
  --card:   #ffffff;   /* 卡片 L100 */
  --border: #e5e6eb;   /* 描边 */
  --text:   #1f2329;   /* 正文 15.78 */
  --muted:  #646a73;   /* 次要 5.04 */
  --shadow: 0 1px 3px rgba(31,35,41,.08);
}
```

### 品牌色替换

只改 `--brand` 一个变量，其余保持。参考实测：

| 品牌 | 色值 | 白底对比度 | 建议用途 |
|---|---|---|---|
| 京东红 | `#e1251b` | 4.69 | 大号数值、页头渐变 |
| 深红 | `#c8161d` | 5.85 | 正文级文字 |
| 品牌蓝 | `#2563eb` | 5.17 | 链接、按钮 |
| 品牌绿 | `#16a34a` | 3.30 | 仅用于大字号或图标 |

对比度低于 4.5 的色值不要直接用于小字。

### 页头渐变

大面积聚焦区才用渐变，方向固定 135 度：

```css
.header {
  background: linear-gradient(135deg, var(--brand) 0%, #ff6a3d 100%);
  color: #fff;
}
```

### KPI 卡片

```css
.kpi {
  background: var(--card);
  border: 1px solid var(--border);
  border-radius: 12px;
  box-shadow: var(--shadow);
  padding: 14px 16px;
}
.kpi .label { color: var(--muted); font-size: 12px; }
.kpi .value { font-size: 22px; font-weight: 700; color: var(--brand-dark); }
```

用负 margin 让 KPI 卡上浮压住页头，是廉价但有效的层次手段：

```css
.kpis { margin-top: -36px; }
```

---

## 配方 C：中性工具界面

```css
:root {
  --chrome: #141414;   /* 外层 L8  */
  --pane:   #181818;   /* 主面板 L9 */
  --raised: #242424;   /* 悬浮层 L14 */
  --text:   #f0f0f0;   /* 正文 L94 */
  --muted:  #a0a0a0;
  --brand:  #f54e00;   /* 品牌橙 */
}
```

饱和度全为 0。适合编辑器、控制台、需要长时间注视的界面。特征是存在感低、不与内容争色。

---

## 图表多色序列

单系列图表用语义色即可。多系列必须有序，否则读者无法把图例和线条对应起来。

### 深色背景推荐序列

```css
--series-1:#4ea1ff;  /* 蓝 */
--series-2:#3dd68c;  /* 绿 */
--series-3:#f5c542;  /* 黄 */
--series-4:#b48ead;  /* 紫 */
--series-5:#ff9f68;  /* 橙 */
--series-6:#7fd6d6;  /* 青 */
```

排序原则：相邻两色在色相上至少差 40 度，明度交错（一深一浅），确保色盲用户也能区分前两条。

### 避免的做法

- 用同一色相不同明度做多系列 —— 图例难以对应
- 超过 8 个系列 —— 改用小多图（small multiples）
- 红绿同时作为前两位系列色 —— 与涨跌语义冲突

---

## 组件级用色规则

| 组件 | 用色规则 |
|---|---|
| 页头 | 渐变底 + 白字，仅此一处大面积彩色 |
| KPI 数值 | 强调色或品牌深色，不用语义色（除非本身就是涨跌指标） |
| 表格表头 | 次要文字色，不加背景 |
| 表格分隔 | `--border` 单线，不用斑马纹 |
| 排名徽章 | 浅色底 + 品牌色文字，如 `#fff1f0` + `#e1251b` |
| 状态胶囊 | 深底 + 亮字，如 `#052e1a` + `#86efac` |
| 焦点描边 | 强调色，2px，不用外发光 |
| 禁用态 | 正文色降到 40% 透明度 |
