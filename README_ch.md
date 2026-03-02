<div align="center">
  <img src="https://i.imgur.com/v0Tx6am.png" alt="AI Code Guide" />
  <p align="center">
    作者 <a href="https://x.com/aut0mata">Vilson Vieira</a> 和
       <a href="https://x.com/esrtweet">Eric S. Raymond</a>
  </p>
  <a href="https://discord.gg/NrDfXmtvw3">
     <img src="https://i.imgur.com/uqKVFHj.png" alt="加入我们的 Discord" height="48" />
  </a>
</div>
<br/>

> 关于使用 AI 辅助你编程和/或替你编码，你想了解的一切。

<div align="center" style="font-size: 30px">
  <a href="#vibe">TL;DR 直接告诉我怎么 vibe 编码 😎！</a>
</div>
<br /><br />

## 简介

我们与计算机交互、为其编写代码的方式正在改变。而且这是一场深刻的变化：从我们使用的工具，到编程方式以及对软件产品和系统的思考方式。

变化非常快！每周都有新的 LLM 模型发布。新工具、新编辑器、新的「vibe coding」实践、新协议，MCP、A2A、SLOP……很难跟上。一切都散落在不同的网站、仓库、YouTube 视频里。

所以我们决定写下这份指南。这是将相关内容集中起来、在一个地方、以易读形式呈现 **AI 编程** 或 **AI 辅助代码生成** 实践与工具的尝试。

- **如果你是程序员但还没在用 AI 代码助手**：本指南适合你，介绍了最新的工具和良好实践，帮助你在日常工作中发挥 AI 的作用，无论是让 AI 做你的副驾，还是你做 AI 智能体的副驾。

- **如果你从未编过程但对新的「vibe coding」感兴趣，想自己做 SaaS 等软件产品**：本指南也适合你。我们会尽量去掉晦涩的部分，保留起步所需的内容，同时分清真正重要的和只是炒作的东西。

好，我们开始吧！

📚 参考资源：

- Tim O'Reilly 的 [《我们所知的编程的终结》](https://www.oreilly.com/radar/the-end-of-programming-as-we-know-it)
- Santiago 的 [如何为开发和 AI 的未来做准备](https://www.youtube.com/watch?v=BP54GqVK3JA)
- Steve Yegge 的 [初级开发者的复仇](https://sourcegraph.com/blog/revenge-of-the-junior-developer)
- Geoffrey Huntley 的 [Dear Student: Yes, AI is here, you're screwed unless you take action...](https://ghuntley.com/screwed/)
- Thorsten Ball 的 [如何构建智能体](https://ampcode.com/how-to-build-an-agent)
- Simon Willison 的 [使用 LLM 编写代码](https://simonwillison.net/2025/Mar/11/using-llms-for-code/)
- Addy Osmani 的 [70% 问题：AI 辅助编程的残酷真相](https://addyo.substack.com/p/the-70-problem-hard-truths-about)
- Mary Rose Cook 的 [成为 AI 增强型工程师](https://maryrosecook.com/blog/post/become-an-ai-augmented-engineer)
- Amp 团队的 [Raising an Agent 播客](https://ampcode.com/podcast)
- Andrej Karpathy 的 [软件正在再次改变](https://www.youtube.com/watch?v=LCEmiRjPEtQ)
- Vilson Vieira 的 [用 AI 编程一年的心得](https://hackable.substack.com/p/what-i-learned-using-ai-to-code-for)
- Steve Yegge 的 [固执开发者的消亡](https://steve-yegge.medium.com/the-death-of-the-stubborn-developer-b5e8f78d326b)
- Steve Yegge 的 [软件生存 3.0](https://steve-yegge.medium.com/software-survival-3-0-97a2a6255f7b)

## AI 编程？Vibe 编码？

这些术语大同小异。AI 编程指的是使用 AI 模型（尤其是当今的 LLM）及其相关工具来辅助编写软件。也叫「AI 代码生成」或简写为「code gen」。这个领域从 1950 年代用 Lisp 生成代码就开始了，现在 LLM 是主要引擎，也开始出现神经符号混合方法的研究。AI 编程也是一种实践：如果你用 Cursor 通过 tab-tab-tab 获取补全，就是在「AI 编程」；如果你全面使用 Cursor 的 Agent 模式，也是「AI 编程」。总之：任何用 AI 模型辅助生成代码的方式都算。这类用户通常已经会编程。

Vibe 编码是把 AI 编程开到最大 :-) 你不太关心生成了什么代码，只给出提示，让 AI 帮你把代码都写完。这个词是 [Karpathy 在 2025 年创造的](https://x.com/karpathy/status/1886192184808149383)，已经很流行。我认为它有助于让从未想过编程的人也能参与进来！

所以，无论你是用 AI 讨论软件想法，还是只帮你补全已有代码库的一部分，还是在做完整的 vibe 编码，都是在用 AI 辅助生成代码。我们就统称为 AI 编程吧。

## 怎么用？

AI 编程有很多种用法，概括来说：

- **AI 是你的副驾**：你用 AI 模型增强自己，提高生产力。比如用 ChatGPT  brainstorm SaaS 想法，或用 Cursor 补全文档字符串。这里能获得很多收益，尤其在创意探索和自动化枯燥工作上。

- **AI 是主驾**：这时你是副驾。这里就是「vibe 编码」发生的地方。你打开 Cursor Agent 的 YOLO 模式，完全信任智能体生成的代码。自动化能力很强，但需要在系统设计、驾驭智能体、以及在不熟悉的代码里排错等方面有良好实践。

两种方式都要学习和练习！

但随着项目复杂度上升，要多做副驾式合作，少做纯 YOLO vibe 编码。越可能有其他人（或几个月后的你）要维护代码，这一点就越重要。

# 🗺️ 路线图

## 如何起步？

- 如果不会编程、只想玩玩，我们建议从 [Bolt](https://bolt.new)、[Replit](https://replit.com)、[v0](https://v0.dev) 或 [Lovable](https://lovable.dev) 这类网页工具开始。

- 如果已经会编程，可以安装 [Claude Code](https://claude.com/product/claude-code)、[Codex](https://openai.com/codex/)、[Cursor](https://cursor.com/)、[Amp](https://ampcode.com) 或 [Windsurf](https://windsurf.com/)。可以先从免费版开始，再升级到每月 $20 的计划。Claude Code Pro、Codex 和 Cursor 都挺划算，能用到大量最新 LLM 的 token。VSCode 也有自己的 [Agent 模式](https://code.visualstudio.com/blogs/2025/02/24/introducing-copilot-agent-mode)，与 GitHub Copilot 配合，用智能体工作流做修改和编辑。其他编辑器也纷纷加入类似功能，可在各自官网上查看。这些功能通常只在 Beta 或 Insider 版本中提供。

- 如果想用更开源的选择，可以试试 [Pi](https://pi.dev/)、[OpenCode](https://opencode.ai/) 或 [OpenHands](https://github.com/All-Hands-AI/OpenHands)。

> 建议：强烈建议在 OpenRouter 注册账号，很容易就能用上最新 LLM，甚至有免费版本。

> 重要提示：Claude Code 目前很贵！一天轻松花掉 $50。请注意用量。因此建议先用 Cursor，不用太担心费用。

📚 参考资源：

- [Replit 的 Vibe Coding 101](https://www.deeplearning.ai/short-courses/vibe-coding-101-with-replit/)
- [Cursor AI 初学者教程 [2025 版]](https://www.youtube.com/watch?v=3289vhOUdKA)

## 如何写代码提示？也就是如何 vibe 编码？<a id='vibe'></a>

装好这些工具、玩了一阵子之后，你会发现它们会幻觉、陷入 endless 循环反复修错。学会写好提示很重要。一些建议：

- 不要把一切都塞进一个提示里。只说「帮我做一个宠物店应用」对软件工程师没用，对 AI 更是如此 :-) 先理解项目，用 LLM  brainstorm，写一份 PRD（产品需求文档），做计划并拆成任务。下面会给出用 ChatGPT 生成 PRD 的步骤。
- 提供细节。如果你清楚要什么，就说清楚。如果你知道想用的编程语言、技术栈、目标用户，都加进提示里。
- 用 Markdown 或其他轻量文本格式（如 asciidoc）对 LLM 来说都 OK，最终都会被编码成 token。但要突出某些部分，建议用 [XML 标签](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/use-xml-tags) 等符号。
- 把项目拆成任务和子任务。
- 不同目标用不同模型试试。
- 用不同模型互相验证输出。
- LLM 容易说「yes」，所以要保留批判性思维。

下面的示例我们使用 .md 扩展名和 Markdown。如果你更喜欢 asciidoc（对结构化文档支持更好），可以换成 .adoc。LLM 无所谓，都能处理。

这里是一种通常效果不错的方法/流程/策略：

1. 用 `ChatGPT`、Codex 或 Claude Code 输入以下提示：

```
你是一位资深软件工程师。我们要一起为项目写 PRD。

非常重要：
- 一次只问一个问题
- 每个问题要基于之前的回答
- 对每个重要细节深入追问

想法：
<在这里粘贴你的想法>
```

2. 你会进入几轮问答。尽量详细回答。觉得够了之后，发送下面的提示让模型整理成 PRD（也叫 SDD，或规范驱动开发）：

```
将以上内容整理成一份 PRD。使用 markdown 格式。需包含以下部分：

- 项目概述
- 核心需求
- 核心功能
- 核心组件
- 应用/用户流程
- 技术栈
- 实施计划
```

3. 将生成内容复制保存到项目目录下的 `docs/specs.md`
4. 创建任务列表，可这样问：

```
根据生成的 PRD，创建详细的、分步实施计划。
然后将计划拆解为相互依赖的小任务。
再把任务拆成更小的子任务。
确保每一步足够小、能一次完成，但整体足以成功交付项目。
采用软件开发和项目管理最佳实践，避免复杂度跳跃。建立任务依赖关系，不要有孤立任务。

非常重要：
- 使用 markdown 或 asciidoc
- 每个任务和子任务都是可勾选的清单项
- 每项任务提供足够上下文，让开发者能实现
- 每个任务有编号
- 每个任务列出依赖的任务 id
```

5. 保存为项目目录下的 `docs/todo.md`

[这里有一个示例](https://chatgpt.com/share/67f8e8c6-c92c-8007-8fe0-76bdc73f9812)，是用 ChatGPT 4o 为简单 CLI 工具做的 brainstorm/规划，可供参考。

接下来在本地建项目文件夹，记得执行 `git init` 做版本控制。

这样你就有了 PRD 和任务列表！接下来打开 Cursor（或其他 AI 代码编辑器），指向这些文件，然后问：

```
你是一位资深软件工程师。请阅读 @docs/specs.md，并实现 @docs/todo.md 中尚未完成的部分。
每次实现一项任务，遵循任务和子任务的依赖关系。完成一项后勾选，再继续下一项。
```

第一次让 Cursor Agent 执行命令时开启 YOLO 模式，之后在提示里接受或输入 `continue` 即可。

Cursor 有时会因 LLM 限制而要求重试，重试后继续即可。对，这就是 vibe 编码 :-)

基于这一流程，大约 10 分钟构建的 CLI 工具示例仓库：https://github.com/automata/localbiz

> 重要：虽然「vibe 编码」很酷，但了解自己在做什么也同样重要 :-) 审查智能体生成的代码，能帮助你在出错时（肯定会有！）更快定位，也能提升你的代码审查能力（不仅针对 AI 生成的代码，也包括你自己和其他人的代码）。

📚 参考资源：

- Geoffrey Huntley 的 [你可能在用错 Cursor AI...](https://ghuntley.com/stdlib/)：介绍用 Cursor 规则 stdlib 的想法
- Geoffrey Huntley 的 [从设计文档到代码：Groundhog AI 编程助手（及新的 Cursor vibe 编码元流程）](https://ghuntley.com/specs/)：上一篇文章的第二部分，建议用 LLM 自动构建规范（PRD）和 Cursor 规则
- Harper Reed 的 [我目前的 LLM 代码生成工作流](https://harper.blog/2025/02/16/my-llm-codegen-workflow-atm/)
- Harper Reed 的 [LLM 代码生成英雄之旅](https://harper.blog/2025/04/17/an-llm-codegen-heros-journey/)
- Anthropic 的 [Claude Code：智能体编码最佳实践](https://www.anthropic.com/engineering/claude-code-best-practices)：虽然针对 Claude Code，但对任意 LLM 的 AI 编码工作流都有参考价值
- Google Lee Boonstra 的 [提示工程](https://www.kaggle.com/whitepaper-prompt-engineering)：70 页文档，包含代码生成相关提示技巧
- Anthropic 的 [提示工程指南](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering)
- OpenAI 的 [GPT 4.1 提示指南](https://cookbook.openai.com/examples/gpt4-1_prompting_guide)
- [RepoPrompt](https://repoprompt.com/)：帮助从项目组装上下文的工具。建议看 [RepoPrompt 工作流](https://www.youtube.com/watch?v=fm3VreCt-5E) 概览视频，学会在 vibe 编码提示中更好地利用这些工具
- Simon Willison 的 [并非所有 AI 辅助编程都是 vibe 编码（但 vibe 编码很棒）](https://simonwillison.net/2025/Mar/19/vibe-coding/)

## 该用哪个 LLM 模型？

LLM 的训练和对齐目标不同。ChatGPT 或 Claude 这类模型被训练成对话里的通用知识助手。另一些则是在长时间会话（从几分钟到几小时）中，用模型运行工具、对工具输出进行「推理」的结果作为奖励信号，对原始模型做特定任务对齐。Claude Opus、Sonnet 或 OpenAI Codex 的任务就是编程。所以一定要选针对编程训练/对齐且支持工具的模型。

LLM 每天都在变，很难推荐某个具体版本。能做的是建议你考虑哪些「家族」。目前 Claude Opus 和 OpenAI GPT Codex 是 AI 编程的 SotA 专有模型；开源方面有 Kimi、Minimax、GLM 等，紧跟专有模型，差距越来越小。

具体选哪个版本，一般选最新版即可，或参考以下排行榜：

- [OpenRouter 模型](https://openrouter.ai/models?categories=programming&fmt=table)：将分类设为 `programming`，并过滤支持 `tools` 的模型，一般能较好筛选 AI 辅助编程模型
- [Models.dev](https://models.dev)：开源 AI 模型数据库
- [Agent Leaderboard](https://huggingface.co/spaces/galileo-ai/agent-leaderboard)

## 遇到「rate limit」怎么办？

换个模型。

至少有两种情况：一是请求太重，超出模型的输入/输出 token 上限；二是服务器集群压力大时会被限流。错误信息往往不透明。更详细说明见[这里](https://platform.openai.com/docs/guides/rate-limits)。

不同模型 token 限制差异很大。例如截至 2025 年 4 月底，gpt-4.1-mini 比 gpt-4.1 慷慨得多。可以多准备几个 API key（按量付费成本不高），并查看各家的 rate limit 说明，例如 [Anthropic](https://console.anthropic.com/settings/limits)。

## 如何设置项目级规则？

可以在 LLM 上下文中「注入」规则或约定，让它们应用于整个项目。不同编辑器有不同做法：

- 在 Cursor 中，在 `.cursor/rules/` 目录下创建 markdown 文件，Cursor 会在与 LLM 的所有交互中应用这些规则。
- 在 Aider 中，创建包含[规则/约定](https://aider.chat/docs/usage/conventions.html)的 markdown 文件（如 `rules.md`），并在 `.aider.conf.yml` 中添加：`read: rules.md`。

很多工具还支持在用户主目录配置全局规则文件。例如在 Aider 中，可以在 `~/.global_conventions.md` 中写全局约定，然后在 `.aider.conf.yml` 中添加 `read: [~/.global_conventions.md, rules.md]`。

可以把 PRD 的一部分作为规则，比如技术栈或代码格式、风格指南。

规则非常强大，甚至可以让 AI 帮你生成规则！[可参考 Geoff 的方法](https://ghuntley.com/specs/)。

📚 参考资源：

- [Cursor 规则文档](https://docs.cursor.com/context/rules-for-ai)
- [Windsurf 规则文档](https://windsurf.com/editor/directory)
- [Aider 约定文档](https://aider.chat/docs/usage/conventions.html)
- [Aider 约定合集](https://github.com/Aider-AI/conventions)：社区贡献的 Aider 约定文件合集
- [Awesome Cursor Rules](https://github.com/PatrickJS/awesome-cursorrules)：精选 .cursorrules 文件列表，用于增强 Cursor AI 体验

## 如何减少幻觉？PRD 是什么？

PRD 是什么？工程里有个说法：解决复杂问题的最佳方式就是发明一个新缩写 :-) 开玩笑……PRD 是 Product Requirements Document（产品需求文档）的缩写。基本上就是描述软件项目需求和其他细节的文档（可以是一份或多份）。

如果给 LLM 的自由太多、上下文太少，它很容易快速产生幻觉。要用 PRD 来约束它。

PRD 的好处是对所有人都适用：从从未编程的人，到资深工程师或产品经理。你不需要任何背景，只要有一个应用想法就可以开始写 PRD。

如何使用 LLM 生成 PRD 见<a href="#vibe">此处</a>。

## 保留提示日志

记录你发送的每一条提示，并附上（很重要）你当时在想什么、遇到了什么意外。这份提示日志就是你的设计意图记录；对任何没参与过项目的人（包括六个月后已经忘掉当初想法的你）都很有价值。

目前还没有统一的文件名约定，可以用 `vibecode.adoc` 或 `history.md` 之类的。

[aider](https://aider.chat/) 等工具会记录你和 LLM 的对话。一种做法是设置下列环境变量，并把历史文件纳入版本控制：

```bash
# 历史文件：

## 指定聊天输入历史文件（默认：.aider.input.history）
#AIDER_INPUT_HISTORY_FILE=.aider.input.history

## 指定聊天历史文件（默认：.aider.chat.history.md）
#AIDER_CHAT_HISTORY_FILE=.aider.chat.history.md

## 将 LLM 对话记录到此文件（例如 .aider.llm.history）
#AIDER_LLM_HISTORY_FILE=.aider.llm.history
```

有了这些文件，可以在过程中加入你自己的注释。以后回看时，你（和别人）都能更了解项目，也能发现可复用的模式和技巧。

## 如何启动项目？

### Web 应用（前端）

现代 Web 开发信息量很大。JavaScript/TypeScript 框架、CSS 框架等太多，很难决定用什么。在搭建了不少前端之后，我目前的组合是：

- Next.js：可以部署到 Vercel，生态好用（但可能很快变贵）
- 纯 React + React Router：可部署到任意平台
- TanStack 或 Remix：路由支持好，也能部署到任意平台
- FastHTML：如果你偏好 Python，更关注暴露核心后端（如数据分析、AI/ML 流水线），而不是超炫 UI

Lovable 这类基于网页的 AI 编码平台用 React，v0 用 Next.js。

一个技巧是：在 Lovable 上启动项目（免费计划每天 5 条消息），配置把项目输出到 GitHub，再克隆到本地，用 Cursor 继续 AI 编码。然后可以部署到 Render、Fly.io、CloudFlare 等。特别适合后端有更复杂逻辑的情况。

如果你同时做前后端，建议在 Git 仓库根目录分别建 `frontend` 和 `backend` 文件夹，或前后端用不同仓库，在 Cursor 中打开同一 workspace（这样可以在前端智能体中引用后端文件，反之亦然）。

为避免过早把前端接进后端，可以指示 AI 智能体先使用 mock/假数据，等后端实现后再替换。

另一个技巧是用好 MCP 工具，把编码智能体和 playwright 或 browser-use 集成。这样 AI 可以控制浏览器、抓截图和错误信息，减少在浏览器和 AI 之间来回复制粘贴错误的时间。

如果要用 3D 内容且使用 React，建议用 React Three Fiber，而不是直接使用 three.js。R3F 把 three.js 对象包装成 React 组件，更方便处理状态。

### 后端

Lovable 这类网页工具对后端支持一般，大概率需要用 Claude Code、Codex 或其他非网页工具。

Python + FastAPI 是很好的选择。如果前后端都想用 JavaScript/TypeScript，可以用 Node.js + Express。

后端很适合做端到端测试，可以让智能体为每个新功能及其子任务写测试并运行。

后端完成后，可以把文档（尤其是 HTTP 接口）作为前端智能体的输入，这样就能把前端从 mock 数据切换到真实后端数据。

### 游戏

小型游戏可以用单个 .js 文件的纯 JS，3D 用 threejs，2D 用 pixijs。

游戏很依赖素材，可以考虑 Tripo AI、Anything World 等服务生成 3D 资源并做骨骼和动画。

## 如何排查错误和 Bug？

关于编程和软件，有一点要知道：肯定会出错。不管怎么预防都会发生。先接受这一点，和错误、Bug 做朋友。

第一招是学工程师的做法：看解释器/编译器给出的错误信息，试着理解。把错误复制粘贴回 LLM，让它修复。另一个好办法是加入适合调试的 MCP 工具，比如 [BrowserTools](https://browsertools.agentdesk.ai/)。

## MCP、SLOP、A2A 是什么？怎么用？

MCP 是 Model Context Protocol（模型上下文协议）的缩写。由 Anthropic 开发，OpenAI GPT、Google Gemini 等也在考虑采用。它和 function/tool calling（函数/工具调用）关系密切。

工具调用是 LLM 调用工具或函数执行操作的一种方式，可以让 LLM 的知识窗口（基于过去的数据训练）获得新信息，并与外部工具和接口集成。例如要搜索网页，可以指示 LLM 使用一个搜索工具（如「 Hey，如果需要搜索，用这个工具：search(term)」）。这样 LLM 会调用工具、获取结果、用于后续预测，而不是消耗大量 token、多轮迭代和解析。

MCP 把这一思路标准化。我们可以写 MCP 服务器，把资源（如数据库）或工具（执行计算并返回结果的软件）暴露给 LLM。

这不就是 API 吗？用 REST API + 一些解析不行吗？类似，SLOP（Simple Language Open Protocol）就是这么想的。但有了 MCP 这样的标准，可以更容易保证 LLM 原生支持，不需要在客户端做额外解析和 hack。

A2A（Agent to Agent Protocol）比较新，由 Google 提出，作为 MCP 的补充：MCP 侧重 LLM 与工具，A2A 侧重多智能体通信。

> 重要：现在有很多 MCP 服务器，Cursor 等编辑器也支持。目前只有 Anthropic Claude LLM 支持，使用 MCP 工具时请用 Claude。

Anthropic 维护的 MCP 服务器列表：https://github.com/modelcontextprotocol/servers

📚 参考资源：

- [MCP](https://modelcontextprotocol.io/)
- [SLOP](https://github.com/agnt-gg/slop)
- [SLOP 介绍](https://russell.ballestrini.net/introducing-slop/)
- [MCP vs SLOP](https://mcpslop.com/)
- [A2A](https://google.github.io/A2A/)

## 从零开始还是从模板开始？

一般来说，LLM 从零开始表现更好。但也可以从 boilerplate（ starter kit：包含项目骨架、配置等的初始文件夹）开始，并在上下文窗口中加入规则，让 LLM 遵守模板结构。

另一个做法是用 Cursor 的索引功能，或用 [repomix](https://repomix.com/)、[files-to-prompt](https://github.com/simonw/files-to-prompt) 等工具，为项目建索引。

## 绿地/全新项目 vs 现有代码库

如果有现有代码库，建议用 [repomix](https://repomix.com/) 或 [files-to-prompt](https://github.com/simonw/files-to-prompt) 把项目打包进上下文窗口。

另一个技巧是按任务级别而不是项目级别提需求。例如聚焦于要实现的某一个功能，让 Cursor Agent 去实现，并给出该功能的 mini-PRD。就像在指导一位初级开发者完成某个 GH ticket :-)

📚 参考资源：

- [Karpathy 关于 AI 辅助编程方式的推文](https://x.com/karpathy/status/1915581920022585597)
- [在 Cursor 中处理大型代码库](https://docs.cursor.com/guides/advanced/large-codebases)

## 结构化提示对应结构化设计

截至 2025 年 4 月，LLM 已经能生成可运行的代码，但在生成结构良好的代码（合理的分层、职责分离）方面还不够。良好的结构对可读性和可维护性很重要，也能降低缺陷率。

先想好设计，再通过一系列提示让 LLM 产出好的结构。例如在以数据库为中心的应用中，可以先指定记录类型，再引导 LLM 构建封装访问逻辑的 manager 类或模块，最后才提示业务逻辑。

更一般地说，在提示时要考虑把引擎代码和政策代码分离，并按顺序发布提示，引导 LLM 做到这一点。

在项目规则中应加入一条：禁止 LLM 违反分层；如果需要新的引擎方法，应在封装层添加，而不是让低层实现和业务逻辑混在一起。

另一个做法是先从项目核心开始，花时间把主要功能实现并组织好。甚至可以自己写类和函数骨架，再让 LLM 填细节。有了良好基础和完善测试后，再扩展到 CLI、REST API、未来 Web 应用等消费者。

## 该用 TDD 或其他测试吗？

是的，测试比以往更重要。在 2025 年的技术现状下，LLM 能生成干净、正确的代码，但有时会幻觉，而且更关键的是，可能误解需求并生成「正确但做了错事」的代码。即便将来出现人类水平的 AGI，这一点可能也不会变——人类也经常误解需求。语言的歧义性决定了测试在未来仍然重要。

用 TDD 先写出期望的测试骨架，能有效引导 LLM 实现被测试的代码。指示 LLM 编写并运行测试也是好做法：它能把错误和失败的测试纳入上下文并尝试修复。

测试是与 LLM 一起扩展代码库的基础，只有在所有测试通过时才继续推进。

与 LLM 工作时，基于属性的测试很有用。对一整个域/范围做测试，而不是只测几个你想到的例子，可以保证智能体生成的代码在后续变更触发你事先没想到的边界情况时仍然有效。各语言都有不错的库，如 Python 的 [hypothesis](https://hypothesis.readthedocs.io/en/latest/)、JavaScript/TypeScript 的 [fast-check](https://fast-check.dev/)。

在让 LLM 编写或修复测试时，也要仔细检查其生成的代码：有时它甚至会生成硬编码输出，只为让测试通过 :-)

## 如何保证安全？

非 AI 辅助编程中的规则和最佳实践同样适用于这里。多了解并应用到代码中。以下是一份初步检查清单：

- 不要盲目信任 AI 生成的代码，总要验证。记住，AI 不会为你的线上代码负责，负责的是你！
- 不要把 API key 或其他密钥以硬编码字符串存储，尤其不要在前端
- 查询 API 时始终使用 HTTPS
- 创建 HTML 表单时，要做输入验证和清洗
- 不要把敏感数据存在 `localStorage`、`sessionStorage` 或 cookie 中
- 对依赖包运行校验和漏洞扫描

## 如何在 Claude Code 中使用其他 LLM？

想用 Kimi K2 或其他 LLM 的 Claude Code CLI？可以用 claude-code-router，让 Claude Code CLI 通过本地代理路由到 OpenRouter 上的任意模型。下面的步骤适用于 Kimi K2，但可改成其他模型。

首先在 OpenRouter 注册并获取 API key。

确保已安装 Claude Code CLI：

```
npm install -g @anthropic-ai/claude-code
```

然后安装 claude-code-router：

```
npm install -g @musistudio/claude-code-router
```

在 `~/.claude-code-router/config.json` 中添加以下内容，将 `OPENROUTER_API_KEY` 替换为 OpenRouter 的 API key：

```
{
  "Providers": [
    {
      "name": "kimi-k2",
      "api_base_url": "https://openrouter.ai/api/v1/chat/completions",
      "api_key": "OPENROUTER_API_KEY",
      "models": [
        "moonshotai/kimi-k2"
      ],
      "transformer": {
        "use": ["openrouter"]
      }
    }
  ],
  "Router": {
    "default": "kimi-k2,moonshotai/kimi-k2"
  }
}
```

然后通过 router 运行 Claude Code：

```
ccr code
```

应能看到 Claude Code 显示 `API Base URL: http://127.0.0.1:3456`，表示正在使用 claude-code-router 创建的本地代理。完成！

如果只用 Kimi K2 或 Moonshot 的其他模型，也可以用 Moonshot 官方提供的方案：
https://github.com/LLM-Red-Team/kimi-cc/blob/main/README_EN.md

## 如何创建自己的 AI 编程智能体？

我们正在编写相关教程，敬请关注。最好的入门是 Thorsten 的[这篇实践教程](https://ampcode.com/how-to-build-an-agent)，用 Go 一步步构建一个只使用最基础工具（`list_files`、`read_file`、`edit_file`）的简单智能体。

想深入的话，Gerred 的[开源书籍系列](https://gerred.github.io/building-an-agentic-system)是很好的起点。

## 多智能体编排是什么？

2024–2025 年左右，大家开始尝试用不只一个、而是一组智能体完成编码任务。到 2025 年底，Steve Yegge 等人实现了第一批方案。[Gas Town](https://github.com/steveyegge/gastown) 可能是目前最知名的。在 Gas Town 中有一个 Mayor 智能体，接收用户任务、拆分成任务（存储在 Yegge 的另一个工具 [Beads](https://github.com/steveyegge/beads) 中，类似「给智能体用的 GitHub issues」）。Mayor 通过消息与其他智能体（如 Polecats 等 worker）通信，每个智能体有自己的收件箱，收到消息后行动。

还有其他多智能体编排实现，如 [Claude Flow](https://github.com/ruvnet/claude-flow) 和 [Loom](https://github.com/ghuntley/loom)，但整体还很早期，不确定未来是否会成为主流开发方式。建议多玩玩、理解原理，但要提醒：运行 Gas Town 等编排系统很费资源，并行运行的智能体可能在几秒内消耗大量 token。

- [欢迎来到 Gas Town](https://steve-yegge.medium.com/welcome-to-gas-town-4f25ee16dd04)
- [编码智能体的未来](https://steve-yegge.medium.com/the-future-of-coding-agents-e9451a84207c)
- [Gas Town 应急用户手册](https://steve-yegge.medium.com/gas-town-emergency-user-manual-cf0e4556d74b)

# ✨ 特定工具与智能体的技巧

## Claude Code

- [Claude Code 指南](https://github.com/zebbern/claude-code-guide)：涵盖 Claude Code 的已知命令，包括许多基础教程中未提及的功能

# 🛠️ 工具

这里列出 AI 编程相关的主要工具，并附上我们测试时的真实感受。

## 编辑器 / IDE

- [Cursor](https://cursor.com)
- [Windsurf](https://windsurf.com)
- [Cline](https://cline.bot/)
- [OpenHands](https://github.com/All-Hands-AI/OpenHands)
- [Devin](https://devin.ai)
- [VSCode + GitHub Copilot](https://code.visualstudio.com/docs/copilot/setup)
- [Amp](https://ampcode.com)
- [Kiro](https://kiro.dev)

## CLI

- [Claude Code](https://github.com/anthropics/claude-code)
- [OpenAI Codex](https://github.com/openai/codex)
- [Pi](https://pi.dev)
- [opencode](https://github.com/opencode-ai/opencode)
- [Gemini CLI](https://github.com/google-gemini/gemini-cli)
- [Aider](http://aider.chat/)
- [Claude Engineer](https://github.com/Doriandarko/claude-engineer)
- [Roo Code](https://github.com/RooVetGit/Roo-Code)
- [Codebuff](https://www.codebuff.com/)

## Web 应用

- [Bolt](https://bolt.new)
- [v0](https://v0.dev)
- [Replit](https://replit.com)
- [Lovable](https://lovable.dev)
- [Firebase Studio](https://firebase.studio/)

## 后台/远程智能体

- [ZenCoder](https://zencoder.ai/)
- [CodeRabbit](https://www.coderabbit.ai/)
- [Factory AI](https://www.factory.ai/)
- [OpenAI Codex](https://chatgpt.com/codex)

## 实用工具

- [Specstory](https://specstory.com/)
- [Claude Task master](https://github.com/eyaltoledano/claude-task-master)
- [CodeGuide](https://www.codeguide.dev/)
- [repomix](https://repomix.com/)
- [files-to-prompt](https://github.com/simonw/files-to-prompt)
- [repo2txt](https://github.com/donoceidon/repo2txt)
- [stakgraph](https://github.com/stakwork/stakgraph)
- [Repo Prompt](https://repoprompt.com/)
- [Uzi](http://uzi.sh/)
- [Claudia](https://claudia.asterisk.so/)

# 🤗 值得关注的人

在 AI 编码模型/工具上做实现或自己项目中重度使用的人：

- [Addy Osmani](https://x.com/addyosmani)
- [Andrej Karpathy](https://x.com/karpathy)
- [Armin Ronacher](https://x.com/mitsuhiko)
- [Beyang Liu](https://x.com/beyang)（Amp）
- [Cat Wu](https://x.com/_catwu)（Claude Code）
- [Eric S. Raymond](https://x.com/esrtweet)
- [Eyal Toledano](https://x.com/EyalToledano)（TaskMaster）
- [Geoffrey Huntley](https://x.com/GeoffreyHuntley)
- [Gerred Dillon](https://x.com/devgerred)
- [Harper Reed](https://x.com/harper)
- [Mario Zechner](https://x.com/badlogicgames)（pi）
- [Nathan Wilbanks](https://x.com/NathanWilbanks_)（agnt，SLOP）
- [Pietro Schirano](https://x.com/skirano)
- [Quinn Slack](https://x.com/sqs)（Amp）
- [Sandeep Pani](https://x.com/skcd42)（Aider，AgentFarm）
- [Simon Willison](https://x.com/simonw)
- [Steve Yegge](https://x.com/Steve_Yegge)（Gas Town）
- [Vilson Vieira](https://x.com/aut0mata)
- [Thorsten Ball](https://x.com/thorstenball)（Amp）
- [Xingyao Wang](https://x.com/xingyaow_)（OpenHands，AllHands）

# 💖 致谢

本指南受 Maxime Labonne 的 [llm-course](https://github.com/mlabonne/llm-course) 启发。

特别感谢：

- [Gabriela Thumé](https://github.com/gabithume) 所做的一切 ❤️
- [Albert Espín](https://github.com/albert-espin) 的反馈和首批错误修正
- [Geoffrey Huntley](https://x.com/GeoffreyHuntley) 提出基于属性的测试建议，以及他在自主智能体方面的大量教程和实验
- ChatGPT 4o 生成本文顶部的横幅，灵感来自艺术家 [Deathburger](https://citadel9.com/)

# ⭐ 贡献

如需贡献修正、反馈或补充工具、参考，欢迎提交 PR、开 issue，或联系 [Eric](https://x.com/esrtweet) 或 [Vilson](https://x.com/aut0mata)。

如果觉得这份指南有用，欢迎 star ⭐ 并关注后续更新！

## Star 历史

[![Star History Chart](https://api.star-history.com/svg?repos=automata/aicodeguide&type=date&legend=top-left)](https://www.star-history.com/#automata/aicodeguide&type=date&legend=top-left)

# ⚖️ 许可证

MIT
