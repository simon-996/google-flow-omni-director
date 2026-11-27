# Google Flow 能力与提示词

以 Google Flow 正式帮助与用户当前界面为准。下表核验于 2026-11-27。换模型时重新核验，用途相近的其他 Google 产品不能替代 Flow 的能力来源。

## Omni Flash 1.2

| 模式 | 适用情况 | 已核验边界 |
|---|---|---|
| Text to Video | 仅文字即可描述的画面 | 横/竖屏，未订阅 3–10 秒，Plus/Pro/Ultra 3–15 秒 |
| Frames to Video | 有起始帧，或给定首尾帧引导过渡 | 同档位时间范围，网页端，确认地区、图像类型与实际输入 |
| Ingredients / References to Video | 需要人物、场景、道具、图片或视频的视觉参考 | 同档位时间范围，每项素材说明用途。用已确认的 Flow 项目名通过 `@` 引用 |
| Video to Video | 修改用户已有视频 | 同档位时间范围。上传最长 60 秒、1 GB，支持 MOV、MP4、AVI、WMV。大于 30 秒时在 Flow 裁到 30 秒，实际编辑片段最长 10/15 秒 |
| Omni Extend | 延续已有片段结尾 | Plus/Pro/Ultra，网页端，延长 3–10 秒，最多加 3 张参考图。延长后不能叠加 Insert、Remove、Camera 等编辑模式 |

- **官方支持**包括 360p、720p 生成。Omni 360p 可按套餐升频，Plus/Pro/Ultra 最高 1080p，Ultra 可到 4K。用界面检查当前模型、分辨率、积分和出片数量。把升频与原生生成分开记录。
- **声音参考**官方明确的是 Ingredients 的单说话人声音参考，支持预设声音和自定义声音。用户申请声音参考时先核对其界面入口。只有 Ingredients 生成支持声音参考。Text 和 Frames 可描述普通对白意图。
- **谨慎建议**包括共享同一份参考图，主体图用干净背景，场景图尽量避开无关人物。通用 Ingredients 按当时界面和素材必要性选择数量。
- **需要实测**包括中文对白与口型、多说话人一致性、复杂动作、相机轨迹、角色跨镜一致、单图约束完整空间和文字准确性。用自然语言写镜头运动。先用短样片检验要求最严格的镜头。

## 每镜怎么写

先写主体及主要动作，再写环境、构图、镜头运动、光照、风格、声音和延续关系。描述参考图提供的信息与作用，避免用文字覆盖已锁定的视觉特征。刚好有环境内文字时，明确只保留剧情所需的字样。默认无字幕，项目或单镜启用全画面无文字后以空白、遮挡、景深和构图给出可执行约束。音乐指令统一为无背景音乐，后期配乐建议写在文档相应字段。

把实际操作设置放在每个代码块外。用 `SHOT-003-PROMPT-V02` 等编号标注，写清剪辑区间、生成时长、画幅、当前模式、每项素材的实际名称/相对路径、用途、可用状态、验证点。模式仍依赖当前界面的字段标待确认。给每镜独立可复制的文本。需要操作补充时提醒用户按当前 UI 选择素材、设置输出，再自行确认积分并生成。

## 来源

- [Google Flow 模型与功能矩阵](https://support.google.com/flow/answer/16352836)
- [Google Flow 创建视频与声音参考](https://support.google.com/flow/answer/16353334)
- [Google Flow 编辑、延长与输入限制](https://support.google.com/labs/answer/16935718)
- [Google Flow 积分、生成与升频](https://support.google.com/flow/answer/16526234)
- [DeepMind Omni 1.2 Flash 模型卡](https://deepmind.google/models/model-cards/gemini-omni-1-2-flash/)
- [DeepMind Omni Flash 基础模型卡](https://storage.googleapis.com/deepmind-media/Model-Cards/Gemini-Omni-Flash-Model-Card.pdf)
