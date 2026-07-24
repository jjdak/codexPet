# Codex Pets

本仓库收录可直接加载到 Codex 的 v2 动画宠物。每个宠物位于 `outputs/<pet-directory>/`，角色介绍、预览、安装命令和验证信息均放在对应目录的 `README.md` 中。

## 仓库组成

```text
outputs/
└── <pet-directory>/
    ├── README.md             # 角色介绍、预览与安装说明
    ├── pet.json              # Codex 宠物清单
    ├── spritesheet.webp      # Codex v2 动画图集
    ├── contact-sheet*.png    # 动作预览（可选）
    ├── look-directions.png   # 16 方向预览（可选）
    └── validation*.json      # 图集验证结果（可选）
```

Codex 实际加载时只需要 `pet.json` 与 `spritesheet.webp`，并且二者必须放在同一个宠物目录中。

## 可用宠物

| 宠物 | 安装 ID | 仓库目录 | 说明 |
| --- | --- | --- | --- |
| 今汐（Jinhsi） | `jinhsi` | `outputs/jinhsi` | [角色介绍与预览](outputs/jinhsi/README.md) |
| Sparkscribe | `sparkscribe` | `outputs/sparkscribe-enhanced` | [角色介绍与预览](outputs/sparkscribe-enhanced/README.md) |

## 使用方法

先从上表选择宠物，记下它的“安装 ID”和“仓库目录”，再将目录中的两个核心文件复制到：

```text
~/.codex/pets/<安装 ID>/
├── pet.json
└── spritesheet.webp
```

### Windows PowerShell

在仓库根目录运行；以下以今汐为例：

```powershell
$source = "outputs\jinhsi"
$petId = "jinhsi"
$target = Join-Path $HOME ".codex\pets\$petId"

New-Item -ItemType Directory -Force -Path $target | Out-Null
Copy-Item "$source\pet.json" $target
Copy-Item "$source\spritesheet.webp" $target
```

### macOS / Linux

在仓库根目录运行；以下以今汐为例：

```bash
source_dir="outputs/jinhsi"
pet_id="jinhsi"
target="$HOME/.codex/pets/$pet_id"

mkdir -p "$target"
cp "$source_dir/pet.json" "$target/"
cp "$source_dir/spritesheet.webp" "$target/"
```

复制完成后重启 Codex，并在宠物列表中选择对应角色。每个角色目录的 README 也提供了可直接复制的专用安装命令。

## 格式要求

- `pet.json` 中的 `spriteVersionNumber` 必须为 `2`
- 图集尺寸为 `1536 x 2288`
- 单元格尺寸为 `192 x 208`
- 图集布局为 8 列 × 11 行
- 图集必须保留透明通道
- `spritesheetPath` 应指向同目录下的 `spritesheet.webp`
