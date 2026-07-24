# 今汐（Jinhsi）

今汐是以《鸣潮》角色今汐为灵感制作的 Q 版人形贴纸风 Codex 宠物。造型保留白金长发、青绿色服饰、龙角与飘带等辨识特征，并为 Codex 的待机、移动、挥手、跳跃、失败、等待、执行和审阅状态制作了完整动画。

![今汐动作预览](contact-sheet.png)

## 特点

- Codex v2 宠物格式，`spriteVersionNumber: 2`
- 9 组标准状态动画和 16 个顺时针观察方向
- Q 版人形贴纸风，透明背景
- `1536 x 2288` RGBA WebP 精灵表
- 已通过尺寸、透明度、单元格完整性与方向语义验证

## 安装

安装时只需要下面两个文件：

```text
outputs/jinhsi/
├── pet.json
└── spritesheet.webp
```

### Windows PowerShell

在仓库根目录运行：

```powershell
$target = Join-Path $HOME ".codex\pets\jinhsi"
New-Item -ItemType Directory -Force -Path $target | Out-Null
Copy-Item "outputs\jinhsi\pet.json" $target
Copy-Item "outputs\jinhsi\spritesheet.webp" $target
```

### macOS / Linux

在仓库根目录运行：

```bash
mkdir -p ~/.codex/pets/jinhsi
cp outputs/jinhsi/pet.json ~/.codex/pets/jinhsi/
cp outputs/jinhsi/spritesheet.webp ~/.codex/pets/jinhsi/
```

安装完成后重启 Codex，在宠物列表中选择“今汐”。

## 文件说明

| 文件 | 用途 |
| --- | --- |
| `pet.json` | 宠物名称、描述、格式版本及精灵表路径 |
| `spritesheet.webp` | Codex 实际加载的 v2 动画图集 |
| `contact-sheet.png` | 11 行状态动画的完整预览 |
| `look-directions.png` | 16 个观察方向的标注预览 |
| `validation.json` | 图集尺寸、透明度和单元格验证结果 |

## 动作映射

| 行 | 状态 | 帧数 | 表现 |
| --- | --- | ---: | --- |
| 0 | `idle` | 6 | 安静待机与细微呼吸 |
| 1 | `running-right` | 8 | 向右移动 |
| 2 | `running-left` | 8 | 向左移动 |
| 3 | `waving` | 4 | 挥手问候 |
| 4 | `jumping` | 5 | 跳跃 |
| 5 | `failed` | 8 | 失败或取消反应 |
| 6 | `waiting` | 6 | 等待用户输入 |
| 7 | `running` | 6 | 专注执行任务 |
| 8 | `review` | 6 | 仔细审阅结果 |
| 9-10 | `look` | 16 | 从 `000` 到 `337.5` 顺时针观察 |

## 验证

- 尺寸：`1536 x 2288`
- 单元格：`192 x 208`
- 布局：8 列 × 11 行
- 格式：RGBA WebP
- 透明 RGB 残留：0
- 验证错误：0

更多细节见 [validation.json](validation.json)，16 方向效果见 [look-directions.png](look-directions.png)。
