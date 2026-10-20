# 需求访谈 · Requirements Interview

把 APP、网页或小工具的初步想法，通过每轮少量提问，逐步整理成可以指导开发的说明文档。

作者：[不二何](https://github.com/youngerweb2026)。适合不熟悉开发、希望由 Agent 主动提问并补齐需求的人。

## 复制这段话即可请求安装

把下面整段文字发给 Codex，或具备联网与文件操作能力、支持 Skills 的其他 Agent：

```text
请帮我安装「需求访谈」（requirements-interview）Skill：
https://github.com/youngerweb2026/requirements-interview/tree/main/skills/requirements-interview

如果你是 Codex，优先使用内置 Skill Installer，仓库为 youngerweb2026/requirements-interview，技能路径为 skills/requirements-interview。其他支持 Skills 的 Agent 请按自身的技能安装方式处理。
请完整安装该目录，保留 SKILL.md、agents/ 和 references/ 的结构。已有同名技能时先比较内容；相同则保留，不同则先备份再更新。完成后检查文件完整性，并告诉我安装位置和调用方法。
```

安装后的识别时机遵循当前 Agent 的技能加载机制；不支持 Skills 的普通聊天环境无法通过这段话安装。

## 使用方式

在 Codex 中调用：

```text
使用 $requirements-interview（需求访谈）。
我想做一个……，目前的初步想法是……
```

也可以直接说：

```text
使用「需求访谈」Skill。我想做一个整理灵感图片的小工具，
现在图片散落在很多文件夹里，经常记得画面却找不到文件。
请先通过分轮提问帮我完善需求，最后生成开发说明文档。
```

其他 Agent 的显式调用语法以该工具为准。

## 它会如何工作

1. 理解当前想法和已有材料，找出最影响方向的缺口。
2. 每轮只问 1—3 个关键问题，等待你的真实回答，并根据回答继续追问。
3. 用具体场景和易懂的选项解释取舍，专业技术选择由 Agent 提出建议。
4. 区分已确认需求、建议或暂定假设，以及待决定或待验证事项。
5. 信息足够时收敛，生成开发说明；已有清楚需求时可直接出稿。

访谈阶段只做需求澄清和文档。后续开发、发布或上架按用户实际授权处理。

## 开发说明包括什么

- 产品目标、目标用户和典型使用场景。
- 第一版范围、以后再做与明确不做的功能。
- 核心流程、页面与交互、功能规则和数据保存行为。
- 必要的异常处理、权限和外部依赖。
- 可实际检查的验收标准。
- 推荐的技术方向、开发顺序及待验证问题。

默认保存为当前项目中的 Markdown 文档，按项目规模裁剪内容。具体行为以 [SKILL.md](skills/requirements-interview/SKILL.md) 为准；文档组织参考见 [development-spec.md](skills/requirements-interview/references/development-spec.md)。

本技能默认使用简体中文，网页需求默认先按本地电脑端考虑；明确提出的手机 APP、移动网页、响应式或上线目标按实际需求处理。

## 文件结构

```text
skills/requirements-interview/
├── SKILL.md
├── agents/
│   └── openai.yaml
└── references/
    └── development-spec.md
```

技能本身由文本文件组成，无需配置 API Key、安装服务或运行额外脚本。Codex 的显示名称是“需求访谈”，技能标识是 `requirements-interview`；`agents/openai.yaml` 提供 Codex 界面信息，其他工具可按自身能力使用。

## 许可

采用 [MIT License](LICENSE)，可以使用、修改和分享；再分发时保留许可证及版权声明。
