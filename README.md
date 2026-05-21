# Alpha-Beta vs Minimax 对比可视化

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.0-3178C6?logo=typescript&logoColor=white)](https://www.typescriptlang.org/)
[![Vite](https://img.shields.io/badge/Vite-7.0-646CFF?logo=vite&logoColor=white)](https://vite.dev/)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-4.0-06B6D4?logo=tailwindcss&logoColor=white)](https://tailwindcss.com/)
[![Single File](https://img.shields.io/badge/Deploy-Single_HTML-22c55e?logo=googlechrome&logoColor=white)](https://pages.github.com/)
[![Zero Dependencies](https://img.shields.io/badge/Runtime-Zero_Dependencies-f59e0b?logo=nodedotjs&logoColor=white)]()

交互式 Alpha-Beta 剪枝与 Minimax 算法对比可视化工具。双面板同步步进，直观展示剪枝如何减少搜索量。

## 在线预览

拉取后使用浏览器直接打开 `index.html` 即可运行，无需服务器。

## 功能

### 双算法对比

- **左面板**：Alpha-Beta 剪枝算法（翠绿色标识）
- **右面板**：Minimax 完整搜索算法（琥珀色标识）
- 底部对比指标条：总步骤、节点访问数、剪枝数、效率提升百分比

### 交互式博弈树编辑

- 点击节点下方的 `+` 添加子节点
- 悬停节点后点击右侧 `+` 添加兄弟节点
- 悬停节点后点击右上角 `×` 删除节点
- 双击叶子节点数值可直接编辑

### 算法动画

- **运行对比**：两侧同步自动播放算法步骤
- **单步执行**：逐步推进，观察每一步的变化
- **速度调节**：滑块控制播放速度
- **步骤日志**：每个面板独立日志，点击任意步骤可跳转
- **可拖动分割线**：自由调节左右面板宽度

### 快捷键

| 快捷键 | 功能 |
|--------|------|
| `Space` / `R` | 运行对比 |
| `→` / `N` | 单步执行 |
| `Esc` | 重置 |

## 默认博弈树

```
MAX(A)
├── MIN(B)
│   ├── MAX(C) = 6
│   └── MAX(D)
│       ├── MIN(E) = 9
│       └── MIN(F) = 8
├── MIN(G) = 9
└── MIN(H)
    ├── MAX(I)
    │   ├── MIN(K) = 10
    │   └── MIN(L)
    │       ├── MAX(P) = 8
    │       └── MAX(Q) = 14
    └── MAX(J)
        ├── MIN(M)
        │   ├── MAX(R) = 5
        │   ├── MAX(S) = 8
        │   └── MAX(T) = 1
        ├── MIN(N) = 10
        └── MIN(O)
            ├── MAX(U) = 8
            └── MAX(V) = 12
```

5 层 21 节点，Alpha-Beta 剪枝可跳过多个分支，与 Minimax 的步骤数差异明显。

## 视觉编码

| 元素 | 颜色 | 说明 |
|------|------|------|
| MAX 节点 | `#3b82f6` 蓝色 | 取大层 |
| MIN 节点 | `#f59e0b` 琥珀色 | 取小层 |
| 活跃节点 | `#22c55e` 翠绿发光 | 当前正在求值 |
| 剪枝节点 | `#64748b` 灰色虚线 | 被剪掉，无需搜索 |
| Alpha-Beta 面板 | 翠绿 `#10b981` | 左侧标识 |
| Minimax 面板 | 琥珀 `#f59e0b` | 右侧标识 |

## 技术栈

- Vite 7 + TypeScript
- Tailwind CSS
- 手写 SVG 渲染
- 零外部依赖（单文件部署）

