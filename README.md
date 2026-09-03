# Big Data & AI Coursework

大数据与人工智能课程作业仓库

本仓库用于归档《大数据与人工智能》课程的各项作业、实验代码与学习笔记；
同时承载一个"概念学习资料生成"的自定义 **Agent Skill** 及其产物（概念学习 HTML 与关系图）。

> ⚠️ **人工核查声明**
> 本仓库中的**自定义 Skill、及其调用产物（概念学习 HTML、`concept-relationship.md`）均由作者本人做过人工核查**：
> 生成结果由作者逐份审阅确认，来源链接与关键论断均已核对，确认无误后再归档使用。
> 在使用任何 Skill / 第三方资源时，仍请以官方最新文档为准，并按需再次自行核验。

---

## 目录结构

```
bigdata-ai-coursework/
├── README.md                  # 本文件：仓库总览（含 Skill 说明与调用方法）
├── .gitignore                 # 忽略缓存、虚拟环境、大数据文件等
├── docs/                      # 课程讲义、参考资料、学习笔记
├── assignments/               # 作业归档（每份作业一个文件夹）
│   ├── README.md              # 作业提交清单与自检表
│   └── hw01-.../              # 各次作业（按需添加）
├── .workbuddy/
│   └── skills/
│       └── concept-learning-skill/   # ⬅ 自定义概念学习 Skill 存放路径
│           └── SKILL.md              #    元数据(name/description) + 7 章节生成流程
└── learning-materials/        # Skill 调用产物
    ├── concept-agent.html            # 概念学习：Agent
    ├── concept-llm-context.html      # 概念学习：大模型的上下文
    ├── concept-skill.html            # 概念学习：Skill
    └── concept-relationship.md       # Agent·上下文·Skill 关系图（Mermaid）
```

---

## Skill 存放路径

本项目使用**项目级（project-level）Skill**，统一放在：

```
.workbuddy/skills/<skill-name>/SKILL.md
```

当前已安装的 Skill：

| Skill | 路径 | 作用 |
|---|---|---|
| `concept-learning-skill` | `.workbuddy/skills/concept-learning-skill/SKILL.md` | 接收任意单一新概念，产出固定 7 章节的可溯源学习资料 |

> 说明：`.workbuddy/` 是 WorkBuddy 项目数据目录，**不要删除**。若希望 Skill 跨所有项目可用，
> 可改用用户级目录 `~/.workbuddy/skills/`。

---

## Skill 调用方法

`concept-learning-skill` 用于把任意单一概念转化为深度学习资料。**在 WorkBuddy 会话内**，直接
用自然语言点名概念并请求学习即可触发（Agent 会根据 SKILL.md 的 `name`/`description` 自动匹配调用）：

- 示例（会触发本 Skill）：
  - "用 concept-learning-skill 帮我学习一下『反向传播』"
  - "给我讲清楚什么是『因果推断』，我要能复述"
  - "整理一份关于『向量数据库』的学习资料"

产物为一篇**固定 7 章节**的文档（可输出为 HTML/Markdown 等）：
个人解释 → 核心机制 → 应用场景 → 边界辨析 → 来源链接 → 学习路径 → 自测与常见误区。
其特点：概念无关、来源可溯源（关键论断带真实可复现 URL）、输出前按自检清单逐项核对。

---

## 环境与依赖

- Python: 3.x
- 每份作业如依赖第三方库，请在对应文件夹内提供 `requirements.txt`
  或注明依赖，便于复现运行环境。

---

## 提交规范

1. 每完成一份作业，在 `assignments/` 下新建对应文件夹（如 `hw01-data-analysis/`），
   放入代码、说明与必要数据。
2. 提交前先在 `assignments/README.md` 中登记，确认满足作业要求。
3. 提交信息（commit message）简明扼要，说明本次作业完成的内容。
4. 大数据量文件（如原始数据集）不要直接提交，说明来源或下载方式即可。

---

## 作者

DingXxxYyy
