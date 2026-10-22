<div align="center">

# Visual DNA

### Aesthetic Extractor · Get Prompt From Images · Keep a Series Consistent

**从参考图中提取视觉 DNA，让灵感成为可复用的设计规范。**

Analyze references → Extract design rules → Write original visual prompts → Review the series

[快速开始](#快速开始) · [核心能力](#核心能力) · [安装](#安装) · [使用示例](#使用示例) · [English](#english)

</div>

## 让“这种感觉”变成可执行的规则

你找到了喜欢的参考图，却很难说明：它为什么可爱？为什么换个姿势就不像同一个角色？为什么单张好看，放在一起却不像一个系列？

Visual DNA 是一个面向原创商业 IP、吉祥物、插画、图标与品牌视觉的 AI Skill。它分析 1–N 张参考图，把几何、比例、配色、线条与质感提取成 `STYLE_DNA.md`，再用这份规范编写系列提示词，并对实际成图检查视觉漂移。

它适合 image-to-prompt 与 aesthetic extraction 的工作流，也让提取出的规则能继续服务于多角色、多姿势、多场景的长期设计。

```text
参考图片 R01 … RN
        ↓ 逐图观察、聚类、对比
STYLE_DNA.md       可复用的风格规则
        +
CHARACTER_DNA.md   具体角色的身份规则（需要时）
        ↓ 固定规则 + 可变任务
PROMPTS.md         每条都能独立使用的提示词
        ↓ 在可用的图像工具中生成
实际成图
        ↓ 逐张检查 + 跨系列对比
QA_REPORT.md       问题定位 → 定向修订 → 复查
```

## 核心能力

| 能力 | 你会得到什么 |
| --- | --- |
| 单图 / 多图风格提取 | 逐图证据、共性、差异与冲突；不把不兼容风格直接混合 |
| 几何与五官分析 | 头身比、头部形状、眼距、眼位、嘴部位置、轮廓与负空间 |
| 完整视觉语言 | 配色角色与占比、线宽与端点、光影、材质、纹理、构图与留白 |
| 结构化风格规范 | 带编号、来源、置信度、适用范围和检查方法的 `STYLE_DNA.md` |
| 原创 IP 身份设计 | 用独立 `CHARACTER_DNA.md` 管理角色轮廓、面部布局、标记与专属配件 |
| 系列提示词 | 同一角色换动作、同风格不同角色、系列插画与图标等任务 |
| Do / Don't 约束 | 把“简洁、可爱、高级”等抽象形容词转换为可观察的约束 |
| 视觉 QA 与迭代 | 逐图和跨系列检查、失败规则定位、针对性修改与版本记录 |

## 风格与角色身份，分开管理

**STYLE_DNA** 描述可复用的设计语言：圆润的几何、低位五官、克制的配色、统一的深色描边等。

**CHARACTER_DNA** 描述具体角色是谁：独特轮廓、脸部布局、标记、专属配件及其组合。

- 同一个角色换姿势：同时锁定风格和身份。
- 同一种风格设计新角色：保留风格规则，重新设计角色身份。
- 原创 IP：明确哪些参考角色身份特征不继承；仅换颜色不足以证明角色已有明显区别。

比例采用定义明确的归一化坐标；视觉估计会标注近似范围。观察、推断与新设计提案分别记录，避免把猜测写成事实。

## 安装

这是一个包含 `SKILL.md` 的本地技能包，无需为技能本身安装运行依赖。实际图片分析需要宿主能够查看图像；实际出图需要宿主提供图像生成工具。

### 方式一：下载并复制

1. 下载此仓库的 ZIP 并解压。
2. 将 `skills/visual-dna` 整个文件夹复制到 `~/.agents/skills/`。
3. 确认入口路径为 `~/.agents/skills/visual-dna/SKILL.md`。
4. 在 Codex 中调用 `$visual-dna`。如果未出现，重启 Codex 后再试。

若已安装同名技能，先备份旧版，再决定是否替换；避免叠加复制产生混合版本。

### 方式二：使用 Codex Skill Installer

在具有 Skill Installer 的 Codex 中发送：

```text
$skill-installer install https://github.com/yuhengwong/visual-dna/tree/main/skills/visual-dna
```

本地发现路径与使用方式参见 [OpenAI 官方技能文档](https://learn.chatgpt.com/docs/build-skills)。其他支持 `SKILL.md` 的宿主可按其安装机制使用；本仓库未对所有宿主做兼容性测试。

## 快速开始

上传参考图，然后发送：

```text
$visual-dna
分析这些参考图，为原创商业 IP 建立 STYLE_DNA.md。
R01 是主要风格参考，其余图片作为补充；只提取风格，不继承参考角色身份。
重点分析几何、头身比、五官比例、色彩、线条与质感。
标明证据、不确定性、do/don't，以及跨系列验证方法。
先输出分析文件，不生成图片。
```

不指定主参考也能开始：技能会先聚类并说明暂定方向。一张图可用于初步分析；未见角度与系列一致性会标为未验证。

## 使用示例

### 1. Get Prompt From Images：从图片获得可复用提示词

```text
$visual-dna
从这 4 张图中提取统一风格，并输出 STYLE_DNA.md 和 PROMPTS.md。
为一个全新的云朵邮差角色写 3 条独立可用提示词。
每条完整展开固定风格规则，分别表现站立、挥手与送信。
这是原创角色，参考图只用于风格。
```

### 2. 同一个 IP，扩展多种表情和动作

```text
$visual-dna
沿用附件中的 STYLE_DNA 和 CHARACTER_DNA。
A01 是我已选定的角色基准图。
输出开心、困惑、惊讶、挥手、奔跑、拿信件共 6 条提示词。
保持角色轮廓、五官布局、色彩位置与专属配件一致。
```

### 3. 同一种设计语言，创建一组新角色

```text
$visual-dna
使用这份 STYLE_DNA 设计 3 个不同的原创吉祥物。
保留家族级的形状、配色与描边规则，分别设计新的轮廓、面部标记和身份线索。
先交付各角色的 CHARACTER_DNA 与提示词，不生成图片。
```

### 4. 系列图标与品牌视觉

```text
$visual-dna
分析这些参考图，建立 8 个服务图标的视觉规范与提示词。
使用统一网格、光学大小、线宽、圆角和留白，五官比例标为不适用。
附小尺寸可读性和跨图标一致性检查计划。
```

### 5. 检查系列成图有没有“跑风格”

```text
$visual-dna
检查这组实际成图，使用附件中的 DNA 规范；A01 是我选定的基准图。
逐张检查轮廓、比例、五官、配色、线宽与质感，并比较整个系列。
输出 QA_REPORT.md，指出失败规则、图中位置、严重程度和修订提示词。
本轮仅诊断，不重新生成。看不清的项目标为不确定。
```

## 交付文件

| 文件 | 用途 |
| --- | --- |
| `STYLE_DNA.md` | 项目风格规范、参考图证据、视觉规则与 do/don't |
| `CHARACTER_DNA.md` | 需要保持身份一致的角色规范 |
| `PROMPTS.md` | 固定风格块、身份块、任务变量与完整提示词 |
| `QA_REPORT.md` | 查看实际成图后，记录逐图和跨系列检查结果 |

按任务交付需要的文件。技能模板是空白框架，不代表对任何参考图的预先分析；项目文件应另存，避免覆盖已安装的模板。

## 仓库结构

```text
skills/visual-dna/
├── SKILL.md
├── agents/openai.yaml
├── references/
│   ├── analysis.md
│   ├── prompts.md
│   └── visual-qa.md
└── assets/
    ├── STYLE_DNA.template.md
    ├── CHARACTER_DNA.template.md
    └── QA_REPORT.template.md
```

## 能力边界

Visual DNA 提供分析与工作流指引。它没有内置图像生成模型，不会把提示词检查称为实际视觉 QA，也不会保证每次生成完全一致。

图片中的比例与颜色在未经测量时会标为估计。精确尺寸、透明背景、可编辑矢量和生产适用性，需要检查实际输出。参考风格分析与原创设计决策不构成权利清理或法律结论。

当前发布包完成了静态元数据、内部链接与目录结构检查；尚未提供真实图像的端到端示例或生成效果基准。欢迎通过 Issue 提交具体输入、预期规则、实际偏差与使用的工具版本；分享前请移除私人或未获授权的素材。

## English

**Visual DNA is an aesthetic extraction and image-to-prompt skill for original character and visual-system design.**

Analyze one or more reference images, extract a structured `STYLE_DNA.md`, write self-contained prompts, and review actual outputs for drift across a series. Designed for mascots, original IP, illustrations, icons, and brand visuals.

The workflow separates reusable style from character identity. Evidence, inference, and proposed design choices are labeled separately. Geometry and facial proportions use defined measurement frames; uncertain or unseen details remain uncertain.

Install `skills/visual-dna` in your host's local skill directory. In Codex, use `~/.agents/skills/visual-dna`, then invoke `$visual-dna` with your images. The skill is instruction-only; image generation depends on tools available in the host. Consistency, rights clearance, and production readiness are not guaranteed.
