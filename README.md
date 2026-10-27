# 枯木逢春（Raw to Clear Deconstructor）

一个 Codex 技能（Skill）：当用户的提示词不够文雅、表达粗糙甚至夹带情绪时，
帮助 AI 维持体面、清晰、准确的文本输出，而不是跟着一起变得粗疏。

## 初衷

很多时候，用户并不是不会好好说话，只是着急、疲惫或者图省事，
提示词里会带着口语、俚语、情绪化的措辞。

这个技能的初衷，是让 AI 在这种情况下仍然守住表达的分寸：

- 不模仿用户的粗俗用语；
- 不被情绪带着走；
- 把粗糙的输入还原成清楚的问题，再给出体面、专业、可执行的回答。

项目名“枯木逢春”，取的是把干枯、凌乱的表达重新理顺、让它重新长出枝叶的意思；
英文名 Raw to Clear Deconstructor 则强调这个过程：
拆解原始表达（Raw），还原真实意图，最后输出清晰（Clear）的结果。

## 它解决什么问题

- 用户表达含糊、夹带口头语时，AI 仍然能抓住核心问题。
- 用户语气不客气时，AI 不跟着变得轻佻或对抗。
- 技术分析保持逻辑完整、步骤清楚，同时措辞得体。
- 总结和结论凝练，不堆砌辞藻，也不为了“接地气”牺牲语言质量。

## 目录结构

```text
raw-to-clear-deconstructor/
├── SKILL.md
├── agents/
│   └── openai.yaml
└── README.md
```

- `SKILL.md`：技能主体，包含核心原则、执行细则与禁忌。
- `agents/openai.yaml`：界面显示信息与隐式调用策略。

## 安装方式

把整个 `raw-to-clear-deconstructor` 文件夹复制到 Codex 的技能目录：

```powershell
Copy-Item -Recurse .\raw-to-clear-deconstructor "$env:USERPROFILE\.codex\skills\"
```

安装后，新开一轮对话即可使用。

## 触发方式

- 用户要求进行清晰分析时。
- 用户明确偏好文雅、正式、得体的表达时。
- `agents/openai.yaml` 中已开启 `allow_implicit_invocation: true`，
  满足条件时可被隐式调用。

## 使用示例

```text
用枯木逢春（raw-to-clear-deconstructor）的方式，帮我分析一下这个方案的取舍。
```

```text
请保持文雅、准确的表达，拆解这段代码的问题。
```

```text
我这段话说得比较乱，你先帮我理清问题，再给出正式一点的结论。
```

