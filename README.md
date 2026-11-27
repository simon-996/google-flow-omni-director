# Google Flow Omni 导演 Skill

把一句创意、剧本或现有分镜整理成能拿去 Google Flow 制作的方案。Skill 负责剧本和分镜、人物场景道具规划、逐镜提示词、文件归档和回片质检。你在 Flow 里选模型、加素材、核对积分并生成。

- 正式名称为 `google-flow-omni-director`，Skill 目录与 `SKILL.md` 内的名称一致。
- 当前 Flow 参考基线是 **Omni Flash 1.2**。每个项目按实际模型、套餐和界面核对。
- 仓库是纯 Markdown。使用时需要可读取上游材料的对话环境。实际保存文件、制作图片或生成工作簿时使用当前环境提供的对应工具。

## 快速开始

### 在 Codex 中使用

在本仓库的聊天里直接说「读取 `SKILL.md`，按 Google Flow Omni 导演流程帮我制作下面的短片」。日常跨项目使用时，把名为 `google-flow-omni-director` 的 Skill 目录放到 Codex 用户 Skill 搜索路径，例如 `~/.agents/skills/`。安装后可输入 `$google-flow-omni-director` 显式调用。[OpenAI Skill 文档](https://learn.chatgpt.com/docs/build-skills)

### 在 ChatGPT 中使用

账号或工作区提供 Skill 上传入口时，可按界面提示添加 Skill 及其配套 Markdown。也可在 ChatGPT 项目中把 [SKILL.md](SKILL.md) 的正文填入项目指令，并上传 `references/`、`templates/` 下的文档。项目指令中提醒模型按同名文件读取参考。需要范例时上传 `examples/` 中的文档。云端生成的项目文件下载后再放入本地项目目录。[ChatGPT Skills 帮助](https://help.openai.com/en/articles/20001066-skills-in-chatgpt)

### 开场示例

~~~text
帮我规划一支 30 秒竖屏便利店悬疑短片。我的 Flow 是无订阅档。
我有店员和店内两张参考图，人物和场景沿用参考。请先给剧情草案与分镜方案。
默认无字幕，包装可以有字，背景音乐后期添加。试拍先验证那一句中文对白。
确认后输出制作文档和一份可逐镜复制的 Flow 提示词总表。
~~~

## 日常工作流

1. **定剧本与镜头目标。** 告诉 Skill 片长、画幅、故事、Flow 套餐和你已有的素材。
2. **确认人物、场景和道具。** 每项可以选只写生图词、直接生图或根据参考图编辑。确认后登记正式版本。
3. **打开 `05_Flow逐镜提示词与素材引用.md`。** 全片提示词都在这里。每镜一个可复制代码块，时长、模式、素材和验收要求都写在块外。
4. **在 Flow 试拍。** 优先验证关键角色、难动作或对白。Flow 的生成时长和剪进成片的时长分别记录。
5. **回片后返工。** 把视频、截图或时间点交给 Skill。根据实际问题改对应镜头，保留旧文档与旧素材供追溯。

## 字幕、画面文字和音乐

| 设置 | 默认处理 |
|---|---|
| 字幕 | Flow 镜头默认无对白字幕和说明字幕 |
| 场内文字 | 招牌、包装和屏幕文字按剧情需要可出现。可能乱码、变形或跨镜漂移，必须准确的字后期加 |
| 全画面无文字 | 可以对项目或单镜开启。可直接说「第 3 镜全画面无文字」 |
| 声音 | 可安排对白、旁白、环境声和动作音效。背景音乐后期加 |

## 项目保存

Windows 本地默认保存到 `D:\workplace\omni-flow-projects\YYYY-MM-DD_片名\`，也可指定其他目录。项目根目录放 `00` 到 `07` 八份制作文档与 `asset-manifest.xlsx`。原始文件进 `inputs/`，参考资产进 `assets/`，Flow 回片进 `flow-renders/`，后期文件进 `post/`，成片进 `exports/`。

每个实际使用的内容目录都有自己的 `backup/`，包括根目录和单镜回片目录。修改前保存旧版，新版留在正常目录。例如：

| 当前文件 | 对应的旧版 |
|---|---|
| `05_Flow逐镜提示词与素材引用.md` | `backup/05_Flow逐镜提示词与素材引用_V01.md` |
| `assets/characters/CHAR-001-sheet-V02.png` | `assets/characters/backup/CHAR-001-sheet-V01.png` |

镜头提示词在总表内有独立版本。回片命名如 `flow-renders/SHOT-003/SHOT-003-PROMPT-V02-TAKE-01.mp4`。同镜同版每生成一次增加 TAKE。选定新回片时才归档被替换的回片。已有素材和历史回片通过资产清单里的版本与相对路径追溯。

## 仓库内容

| 文档 | 用途 |
|---|---|
| [SKILL.md](SKILL.md) | Skill 入口与全局规则 |
| [制作流程](references/production.md) | 需求、剧本、三种资产模式、分镜和质检 |
| [Flow 能力与提示词](references/flow.md) | 模式选择、时长、支持边界和官方来源 |
| [目录、命名与备份](references/project-files.md) | 项目目录、资产命名、归档和追溯 |
| [项目交付模板](templates/project-documents.md) | 八份制作文档和资产工作簿字段 |
| [30 秒样例](examples/30秒样例.md) | 一份可照着写的提示词总表与返工示例 |
