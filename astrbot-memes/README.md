# 臭企鹅表情包

给 AstrBot `mememanager` 插件用的表情包图库，人设是「臭企鹅 / 咕咕」。

## 目录结构

```
astrbot-memes/
├── manifest.json      ← 必须，插件靠它认图库
└── memes/             ← 分支文件夹，每个文件夹名 = 一个情绪分类
    ├── angry/
    ├── baka/
    ├── confused/
    ├── fool/
    ├── happy/
    ├── like/
    ├── sigh/
    ├── sleep/
    └── surprised/
```

图片直接丢进对应情绪文件夹，**文件名必须是纯 ASCII**（英文、数字、下划线、短横线），不要用中文、空格、括号。

推荐的命名：

```
happy/01.jpg
happy/02.png
angry/01.gif
```

## 分类说明

| 文件夹 | 什么时候用 |
| --- | --- |
| `angry` | 被怼烦了、翻白眼、开嘴炮。一天最多两次 |
| `baka` | 怼人但收着力，骂完对方笑了那种。不连击 |
| `confused` | 没听懂、装傻、看到离谱发言 |
| `fool` | 自嘲、抽象发疯、缓和气氛 |
| `happy` | 得意、整活成功、被夸 |
| `like` | 真心认同 |
| `sigh` | 无语、摆烂、看破红尘 |
| `sleep` | 犯困、想走、咕咕咕、躺平 |
| `surprised` | 抽象震惊、被离谱到 |

这几段描述会**直接喂给 AI**，决定它什么时候挑这张图。所以写的是「什么场合」，不是「这图长什么样」。

## 怎么装进 AstrBot

WebUI → 表情包插件 → 「从 GitHub 安装 · 使用自定义来源」：

| 表单项 | 填什么 |
| --- | --- |
| GitHub 仓库 | `你的用户名/astrbot-memes` |
| 分支或版本 | `main` |
| 包所在目录 | `.` |

## 加新分类

1. 在 `memes/` 下建文件夹
2. 在 `manifest.json` 的 `categories` 里加一条同名键 + description
3. 两边**必须同名**，少一边就不生效

## 支持格式

`.jpg` `.jpeg` `.png` `.gif` `.webp`

GIF 体积控制在 2MB 以内，太大会拖慢发送。
