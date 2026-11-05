# 令牌全表

按三层组织结构：基础色 → 语义令牌 → 用途分档。所有色值取自实际样式表，可直接复制。

---

## 一、浅色界面完整令牌

### 背景

```css
--paper:    #ffffff;   /* 主内容区 */
--paper-2:  #fcfcfc;   /* 标题栏、工具栏 */
--paper-3:  #f5f5f5;   /* 侧栏 */
--scrim:    #00000080; /* 遮罩 50% */
--scrim-heavy: #000000e5; /* 重遮罩 90% */
```

三层纸色的明度差只有 1 到 3 个百分点。层次不靠底色拉开，靠描边与阴影。

### 文字四级

```css
--text-primary:    #1c1c1c;    /* 100%  对比度 17.04 */
--text-secondary:  #1c1c1cad;  /* 68%   对比度 5.83  */
--text-tertiary:   #1c1c1c8f;  /* 56%   对比度 3.95  */
--text-quaternary: #1c1c1c66;  /* 40%   对比度 2.49  */
```

### 图标四级

```css
--icon-primary:    #1c1c1ceb;  /* 92% */
--icon-secondary:  #1c1c1ca8;  /* 66% */
--icon-tertiary:   #1c1c1c85;  /* 52% */
--icon-quaternary: #1c1c1c52;  /* 32% */
```

整体比文字低一档，因为图形块的视觉重量大于笔画。

### 描边四级

```css
--border-primary:   #1c1c1c3d;  /* 24% */
--border-secondary: #1c1c1c1f;  /* 12% */
--border-tertiary:  #1c1c1c14;  /* 8%  */
--border-quaternary:#1c1c1c0f;  /* 6%  */
```

### 阴影

```css
--shadow-card:      #1c1c1c09;  /* 最轻，卡片 */
--shadow-secondary: #1c1c1c12;
--shadow-control:   #1c1c1c1f;
--shadow-popover:   #1c1c1c1a;
--shadow-modal:     #1c1c1c1a;
--shadow-window:    #1c1c1c8f;  /* 最重，窗口投影 */
```

### 高光

```css
--specular-primary:    #ffffff8f;  /* 56% */
--specular-secondary:  #ffffff29;  /* 16% */
--specular-tertiary:   #ffffff1f;  /* 12% */
--specular-quaternary: #ffffff0f;  /* 6%  */
```

---

## 二、语义色派生矩阵

每个色家族按同一模板展开。以 accent 为例，完整十二个令牌：

```css
/* 填充 */
--accent-primary:          #1680f3;   /* 对比度 3.88 */
--accent-primary-hover:    #126fd4;   /* 暗 12% */
--accent-primary-disabled: #1680f32b; /* alpha 17% */
--accent-secondary:        #1e86fc17; /* alpha 9% */
--accent-secondary-hover:  #1e86fc2b; /* alpha 17% */
--accent-bright:           #1e86fc;   /* 高饱和，用于需要跳出的点 */

/* 文字 */
--text-accent-primary:     #0b6dd3;   /* 对比度 5.07 */
--text-accent-quaternary:  #1e86fc2b;

/* 图标与描边 */
--icon-accent-primary:     #1680f3;
--border-accent-primary:   #1680f3;
--border-accent-quaternary: #1e86fc2b;
```

### 四个状态家族的取值

| 家族 | 填充 | hover | 文字 | 文字对比度 |
|---|---|---|---|---|
| accent | `#1680f3` | `#126fd4` | `#0b6dd3` | 5.07 |
| danger | `#e72e3b` | `#c82532` | `#cd2834` | 5.32 |
| success | `#10ab61` | `#0d9655` | `#00854a` | 4.71 |
| warn | `#da830e` | `#c2730b` | `#aa6300` | 4.67 |

规律：hover 比基础暗约 12%，文字比填充暗一档，disabled 用 alpha 17%，secondary 用 alpha 9%。

### 扩展色家族

除状态色外还有 blue、green、cyan、orange、yellow、red、magenta、purple、brown，同一模板。用于标签、分类、图表辅助色。

```css
--green:  #10ab61;   --green-bright:  #14c16f;
--cyan:   #10a693;   --cyan-bright:   #13b7a2;
--orange: #ee620d;   --orange-bright: #fd690f;
--yellow: #da830e;   --yellow-bright: #f59312;
--red:    #e72e3b;   --red-bright:    #fb2b3e;
```

---

## 三、图表色板

### 浅色主题

```css
--series-0: #1084FE;  /* 蓝  H211 */
--series-1: #C24E00;  /* 橙  H24  */
--series-2: #9159FE;  /* 紫  H260 */
--series-3: #009957;  /* 绿  H154 */
--series-4: #FF309B;  /* 粉  H329 */
--series-5: #C27400;  /* 琥珀 H36 */
--series-6: #008F7E;  /* 青  H173 */
--series-7: #97683D;  /* 棕  H29  */

--series-other:        #777777;
--series-negative:     #C21D2E;
--series-single-rest:  #B5D9FF;   /* 首色 #1084FE 的浅版 */
--area-alpha:          24;        /* 14% */
--band-alpha:          40;        /* 25% */
```

白底对比度：3.65 / 4.79 / 4.15 / 3.69 / 3.42 / 3.63 / 4.02 / 4.81。图表色块按图形标准（3.0）评估，全部通过。

### 深色主题

```css
--series-0: #1084FE;  /* 保持不变 */
--series-1: #FF6700;  /* 提亮 */
--series-2: #9159FE;  /* 保持不变 */
--series-3: #00C972;  /* 提亮 */
--series-4: #FF309B;  /* 保持不变 */
--series-5: #FF9800;  /* 提亮 */
--series-6: #00BCA6;  /* 提亮 */
--series-7: #97683D;  /* 保持不变 */

--series-negative:    #FF263C;
--series-single-rest: #084382;
```

在 `#181818` 上对比度：4.86 / 6.08 / 4.28 / 8.12 / 5.20 / 8.24 / 7.39 / 3.69。

只有不足的四个被提亮，达标的保持原值。这是验算后的结果，不是整体调色。

### 取用顺序

```
定义 0 1 2 3 4 5 6 7
取用 0 5 3 4 2 1 6 7
```

换算：蓝 → 琥珀 → 绿 → 粉 → 紫 → 橙 → 青 → 棕。

相邻色相差：175 / 118 / 175 / 69。

默认顺序的前四位是蓝紫相邻（差 49 度），两三条线时难以区分。重排后前四位冷暖交替，最小间隔提到 69 度。

### 连续色阶

```css
/* 浅色：值越大越深 */
--sequential: #D6EAFF, #80BEFE, #459FFE, #1084FE, #0C64C1, #084382;

/* 深色：值越大越浅 */
--sequential: #052A51, #084382, #0C64C1, #1084FE, #459FFE, #80BEFE;
```

### 双向色阶

```css
/* 浅色：中点 #E8E8E8 = 背景色 */
--diverging: #C21D2E, #FF8C98, #E8E8E8, #80BEFE, #0C64C1;

/* 深色：中点 #262626 = 背景色 */
--diverging: #FF5667, #82131F, #262626, #084382, #459FFE;
```

中点必须是背景色，零值才会融入。

---

## 四、深色界面令牌

```css
--chrome: #141414;
--pane:   #181818;
--raised: #242424;

--text:   #f0f0f0;   /* 对比度 15.58 */
--muted:  #a0a0a0;

--accent:  #599ce7;  /* 6.20 */
--success: #3fa266;  /* 5.56 */
--danger:  #fc6b83;  /* 6.40 */
--warn:    #f1b467;  /* 9.69 */
--brand:   #f54e00;  /* 5.05 */
```

### 语法高亮

```css
--syntax-bg:        #181818;
--syntax-fg:        #d6d6dd;   /* 12.28 */
--syntax-keyword:   #82d2ce;
--syntax-string:    #e394dc;
--syntax-function:  #efb080;
--syntax-number:    #ebc88c;
--syntax-constant:  #f8c762;
--syntax-link:      #87c3ff;
--syntax-comment:   #e4e4e45e; /* 37% alpha，对比度 2.96 */
```

注释刻意低对比。长时间读代码时，注释不该与代码争夺注意力。

### 终端 16 色（Nord 派生）

```css
--ansi-black:#242424;   --ansi-red:#fc6b83;     --ansi-green:#3fa266;
--ansi-yellow:#d2943e;  --ansi-blue:#81a1c1;    --ansi-magenta:#b48ead;
--ansi-cyan:#88c0d0;    --ansi-white:#f0f0f0;
--ansi-bright-black:#f0f0f099; --ansi-bright-red:#fc6b83;
--ansi-bright-green:#70b489;   --ansi-bright-yellow:#f1b467;
--ansi-bright-blue:#87a6c4;    --ansi-bright-magenta:#b48ead;
--ansi-bright-cyan:#88c0d0;    --ansi-bright-white:#f0f0f0;
```

饱和度普遍低于常见终端主题，因为深色背景下高饱和色会刺眼。

---

## 五、组件级用法

| 组件 | 用色规则 |
|---|---|
| 页面底 | `--paper` |
| 侧栏 | `--paper-3`，右侧加 `--border-tertiary` 分隔 |
| 卡片 | `--paper` + `--border-secondary` + `--shadow-card` |
| 卡片悬浮 | 阴影升到 `--shadow-control`，描边升到 `--border-primary` |
| 主按钮 | `--accent-primary` 底 + 白色文字 |
| 次按钮 | `--accent-secondary` 底 + `--text-accent-primary` 文字 |
| 危险操作 | `--danger` 底 + 白字；文字形态用 `--text-danger` |
| 标签/胶囊 | `--*-secondary` 底 + `--text-*-primary` 文字 |
| 表头 | `--text-secondary`，不加背景 |
| 表格分隔 | `--border-tertiary` 单线，不用斑马纹 |
| 焦点环 | `--accent` 2px，不用外发光 |
| 禁用态 | 背景 `--*-disabled`，文字 `--text-quaternary` |
| 占位符 | `--text-quaternary` |
| 遮罩 | `--scrim`，重模态用 `--scrim-heavy` |

### 卡片组合示例

```css
.card {
  background: var(--paper);
  border: 1px solid var(--border-secondary);
  border-radius: 12px;
  box-shadow: 0 1px 3px var(--shadow-card);
}
.card:hover {
  border-color: var(--border-primary);
  box-shadow: 0 4px 12px var(--shadow-control);
}
```

### 深色卡片

```css
.card-dark {
  background: linear-gradient(180deg, #121a2b 0%, #182338 100%);
  border: 1px solid #243049;
  border-radius: 16px;
  box-shadow: 0 10px 30px rgba(0, 0, 0, .25);
}
```

---

## 六、迁移到其他色相

把浅色体系换成冷蓝底（如 `#0b1220`），只需三步：

1. 三个纸色替换为同色相的三档：`#0b1220 / #121a2b / #182338`，色相误差不超过 5 度
2. 墨色 `#1c1c1c` 换成纸白 `#e8eefc`，alpha 档位不变
3. 语义色取深色主题那一列

其余规则全部适用：alpha 派生、填充与文字分离、系列色重排、中点为背景色。
