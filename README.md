# AI 个人概念学习资料生成 Skill 仓库

> 课程作业 1：用 AI 构建一个可复用、可迭代的「概念学习资料生成 Skill」，并产出由该 Skill 生成、经本人核查的学习资料。

## 一、仓库作用

本项目制作一个**可重复使用**的 AI 概念自学资料生成工具：给它任意一个 AI / 计算机概念，它就按统一框架产出一份结构化的 HTML 学习网页（含学习目标、核心机制、应用案例、概念辨析、自测与可核查来源）。仓库既保存 Skill，也保存由其生成的学习资料，可作为后续课程项目的个人工具基础与作品集。

## 二、提交信息（学习通填写用）

- **姓名**：马旭英
- **GitHub 仓库链接**：<https://github.com/Healer926/ai-self-study-skill>

> 说明：以上为学习通作业提交所需信息。仓库仅含作者姓名与公开学习资料，不含任何 API Key、密码或隐私文件（详见 `.gitignore`）。

## 三、Skill 存放路径（项目级）

```
.workbuddy/skills/concept-learner-skill/SKILL.md
```

- 项目级 Skill：仅对**本仓库**生效，随仓库提交与分享。
- 用户级 Skill（对比）：存放于 `~/.workbuddy/skills/`，对所有项目全局可用。

## 四、在 WorkBuddy 中如何调用

1. 用 WorkBuddy 打开本仓库文件夹。
2. 在对话中输入（以学习 “RAG” 为例）：
   ```
   @concept-learner-skill RAG
   ```
3. Agent 会读取 `SKILL.md` 的框架，生成 `learning-materials/rag.html`。  
   本仓库已有的 `agent.html` / `llm-context.html` / `skill.html` 即按此 Skill 生成。

## 五、已生成的学习资料

| 文件                                             | 概念          | 内容要点                                             |
| ---------------------------------------------- | ----------- | ------------------------------------------------ |
| `learning-materials/agent.html`                | Agent       | 个人化解释、组成（规划/模型/工具/记忆）、周报案例、与 Prompt/脚本的辨析        |
| `learning-materials/llm-context.html`          | 大模型的上下文     | token 与窗口、注意力机制、合同问答案例、与“记忆”的辨析                  |
| `learning-materials/skill.html`                | Skill       | 工作手册比喻、项目级 vs 用户级、调用示例、与 Prompt/Agent 的辨析        |
| `learning-materials/concept-relationship.html` | 三者关系        | 角色比喻、Mermaid 流程图、对比表、上下文如何影响 Agent、Skill 如何沉淀知识  |
| `learning-materials/concept-relationship.md`   | 三者关系（文本版）   | 同上内容的 Markdown 版本，便于 GitHub 直接阅读                 |
| `learning-materials/rag.html`                  | RAG（检索增强生成） | 用**同一 Skill** 生成的额外概念，证明 Skill 可学习本作业三个核心概念之外的内容 |

> 三份核心资料（`agent.html` / `llm-context.html` / `skill.html`）均统一包含：个人化解释、核心机制、应用案例、**概念边界与易混淆知识点辨析**、**开放自测题 + 参考答案（可展开）**、**互动选择题（点击即出反馈、自动计分）**，以及已逐条核实可达的真实参考链接。
>
> `index.html` 为学习导航首页，链接上述资料。其中 `rag.html` 是用**同一个 Skill** 对“RAG”这一额外概念生成的，直接证明该 Skill 可复用于本作业三个核心概念之外的内容（符合“Skill 越可复用，成绩越高”的要求）。

## 六、我使用 AI 后的人工核查与修改

本作业用 AI 协助设计与生成，但我**逐条阅读、核实并修改**了内容，关键记录如下：

1. **来源核实（防伪造）**：AI 给出的参考链接我逐条验证可达性后再写入。最终采用已核实的权威源：
   - Anthropic《Building effective agents》
   - Lilian Weng《LLM Powered Autonomous Agents》
   - arXiv《Attention Is All You Need》(1706.03762)
   - WorkBuddy 官方文档《WorkBuddy 简介》  
     对在本环境无法核实或区域受限的站点（如部分 OpenAI / Claude 文档）**主动弃用**，不写猜测网址。
2. **改写避免照搬**：三份资料的概念解释为本人用“工作手册 / 工作台 / 执行员工”等类比重新组织，未整段复制 AI 对话结果；并补充了“使用边界 / 局限”，不只写优点。
3. **修正原有仓库的不准确处**：
   - 旧 README 把并不存在的 `agent.html / llm-context.html / skill.html` 列为“已完成”——本次**实际补齐**这三份资料并更正 README。
   - 旧 `index.html` 链接指向不存在的 `language.html / prompt.html / token.html / model.html`——本次重写为指向四份真实资料。
   - 旧 `.gitignore` 为空——本次补齐（排除 `.env`、密钥、日志、个人隐私等）。
4. **Skill 增强**：在原有 `SKILL.md` 基础上，显式补全「输出结构」「资料来源要求」「自检要求」三个板块，并强调其**可复用性**（接收任意概念，而非仅本次三个概念）。
5. **关系说明补强**：新增 `concept-relationship.md`（文本版），并在 HTML 版中加入 Mermaid 流程图与对比表，明确写出“上下文如何影响 Agent”和“Skill 如何沉淀可复用知识”两个重点。

**本轮补充与增强（第二轮，针对批改要点）**：

6. **参考链接补实**：三份资料各自补充 1–2 条真实可打开的权威链接并逐条核实可达——Agent 增加 arXiv《ReAct》(2210.03629)；上下文增加 Wikipedia《Large language model》；Skill 增加 Anthropic《Building effective agents》。所有链接均为真实公开地址，无伪造、无猜测网址。
7. **概念边界与易混淆辨析强化**：三份资料的 ⑥ 板块均扩充为“概念辨析 + 使用边界 + 易混淆知识点”，明确区分 Agent/Workflow/RAG/工具、上下文/记忆/Prompt/训练数据、Skill/Prompt/Plugin/宏 等高频混淆组合，并给出“一句话小结”便于记忆。
8. **自测题 + 参考答案**：三份资料在 ⑦ 开放自测题下新增“参考答案（可点击展开）”；`agent.html` 原有互动选择题保留，`llm-context.html` 与 `skill.html` 新增同款互动选择题（点击即出对错反馈与解析、底部自动计分），实现“做—评—学”闭环。
9. **关系说明新增考点速记表**：`concept-relationship.html` 增加 ⑦「考点速记表」，用一张表把三者的“定位 / 必考核心点 / 易混淆坑 / 相互关系”并列呈现，并给出“一句话串记”，强化考试重点。

## 七、项目文件结构

```
ai-self-study-skill/
├── .workbuddy/
│   └── skills/
│       └── concept-learner-skill/
│           └── SKILL.md
├── learning-materials/
│   ├── agent.html
│   ├── llm-context.html
│   ├── skill.html
│   ├── concept-relationship.html
│   ├── concept-relationship.md
│   └── rag.html
├── index.html
├── README.md
└── .gitignore
```

## 八、本地查看方式

直接用浏览器打开 `index.html` 即可浏览全部资料；或打开 `learning-materials/` 下任意 `.html`。

## 九、安全与版本说明

- `.gitignore` 已排除环境变量（`.env`）、密钥（`*.key` / `*.pem` / `secrets.json`）、日志与个人隐私文件，**不会提交敏感信息**。
- 全部内容通过 `git add` / `commit` 提交，并 `push` 到 GitHub 公开仓库。
- 后续可继续调用 Skill 新增概念资料（如 RAG、Fine-tuning），形成持续积累。

## 十、如何把更新提交到 GitHub（命令行）

本仓库文件已准备就绪。在**能访问 GitHub 的电脑**上执行（Windows PowerShell / Git Bash 均可）：

```bash
# 1) 在任意目录克隆现有仓库（保留提交历史）
git clone https://github.com/Healer926/ai-self-study-skill.git ai-self-study-skill-tmp
cd ai-self-study-skill-tmp

# 2) 用本作业生成的文件覆盖（保留 .git，不删远程独有文件）
#    Windows:
robocopy "C:\Users\zhuyu\WorkBuddy\2026-09-10-11-10-12" "." /E /XO
#    macOS / Linux 则改用：
#    cp -r /你的/本作业文件夹/. .

# 3) 提交并推送
git add -A
git commit -m "feat: 补充 Agent/上下文/Skill 三份资料，完善 SKILL/README/关系说明/.gitignore"
git push origin main
```

> 说明：本环境（WorkBuddy 沙箱）的出网代理屏蔽了 github.com，无法在此直接 clone / push；请在你的本机终端执行上述命令。若 `git push` 报错“non-fast-forward”，先 `git pull --rebase origin main` 再 `git push`。
