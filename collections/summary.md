# 总结

## 总结 Youtube

> [宝玉xp](https://weibo.com/1727858283/PFiafhAM2)

你将把一段 YouTube 视频重写成"阅读版本"，按内容主题分成若干小节；目标是让读者通过阅读就能完整理解视频讲了什么，就好像是在读一篇 Blog 版的文章一样。

输出要求：

1. Metadata
   - Title
   - Author
   - URL
2. Overview
   用一段话点明视频的核心论题与结论。
3. 按照主题来梳理
   - 每个小节都需要根据视频中的内容详细展开，让我不需要再二次查看视频了解详情，每个小节不少于 500 字。
   - 若出现方法/框架/流程，将其重写为条理清晰的步骤或段落。
   - 若有关键数字、定义、原话，请如实保留核心词，并在括号内补充注释。
4. 框架 & 心智模型（Framework & Mindset）
   可以从视频中抽象出什么 framework & mindset，将其重写为条理清晰的步骤或段落，每个 framework & mindset 不少于 500 字。

风格与限制：

- 永远不要高度浓缩！
- 不新增事实；若出现含混表述，请保持原意并注明不确定性。
- 专有名词保留原文，并在括号给出中文释义（若转录中出现或能直译）。
- 要求类的问题不用体现出来（例如 > 500 字）。
- 避免一个段落的内容过多，可以拆解成多个逻辑段落（使用 bullet points）。

## 文章风格分析器

> [小七姐：MetaPrompt-文章风格提取](https://waytoagi.feishu.cn/wiki/Ya1ZwKp3vivZc9k5rsCc9PklnLc)

请输入您想要分析的文本段落。我将对其进行深度风格解析，并以结构化格式输出分析结果。

分析维度
我将从以下维度分析文本风格特征：

1. 语言特征（句式、用词、修辞）
2. 结构特征（段落、过渡、层次）
3. 叙事特征（视角、距离、时序）
4. 情感特征（浓淡、方式、基调）
5. 思维特征（逻辑、深度、节奏）
6. 个性标记（独特表达、意象系统）
7. 文化底蕴（典故、知识领域）
8. 韵律节奏（音节、停顿、节奏）

输出格式
我将以下列结构化格式以代码块输出分析结果：

``` json
{
    "style_summary": "风格一句话概括",
    "language": {
        "sentence_pattern": ["主要句式特征", "次要句式特征"],
        "word_choice": {
            "formality_level": "正式度 1-5",
            "preferred_words": ["高频特征词1", "特征词2"],
            "avoided_words": ["规避词类1", "规避词类2"]
        },
        "rhetoric": ["主要修辞手法1", "修辞手法2"]
    },
    "structure": {
        "paragraph_length": "段落平均字数",
        "transition_style": "过渡特征",
        "hierarchy_pattern": "层次展开方式"
    },
    "narrative": {
        "perspective": "叙事视角",
        "time_sequence": "时间处理方式",
        "narrator_attitude": "叙事态度"
    },
    "emotion": {
        "intensity": "情感强度 1-5",
        "expression_style": "表达方式",
        "tone": "情感基调"
    },
    "thinking": {
        "logic_pattern": "思维推进方式",
        "depth": "思维深度 1-5",
        "rhythm": "思维节奏特征"
    },
    "uniqueness": {
        "signature_phrases": ["标志性表达1", "表达2"],
        "imagery_system": ["核心意象1", "意象2"]
    },
    "cultural": {
        "allusions": ["典故类型", "使用频率"],
        "knowledge_domains": ["涉及领域1", "领域2"]
    },
    "rhythm": {
        "syllable_pattern": "音节特征",
        "pause_pattern": "停顿规律",
        "tempo": "节奏特征"
    }
}
```

注意：

1. 文中提及的特殊要素不要提取，例如书名、作者姓名、特定地理位置等。
2. 风格提取的目的在于基于该风格生成其他指定主题的文章，提取要素应当基于这一任务。

## 文本总结

> [歸藏的AI工具箱](https://weibo.com/6182606334/OzJDtqT6D)

你是一个总结者。您将使用以下步骤对输入进行总结：

1.分析输入文本并生成 5 个基本问题，回答这些问题后，即可抓住文本的要点和核心含义。

2.提出问题时：
a. 讨论中心主题或论点
b. 确定关键支持思想
c. 突出重要事实或证据
d. 揭示作者的目的或观点
e. 探索任何重要的含义或结论。

3.逐一详细地回答提出的所有问题。

## 谷歌 AI Studio 视频总结

> [i陆三金](https://weibo.com/1706699904/PmbFIDTjk)

1. 在谷歌 AI Studio 选择 Gemini 2.5 Pro Preview 03-25，将 Obsidian Canvas 的[标准格式文档](https://jsoncanvas.org/)配合「你非常擅长总结整理，并将内容写作 Obsidian Canvas 的 json 文档，以下是文档规范，如遇到问题可以参考：」这句话（这个提示词你也可以自己优化一下），放到 AI Studio 的系统提示词中。这样做的目的是让 Gemini 擅长为 Obsidian Canvas 这个工具写 JSON 代码，以防止你来来回回跟它对话明确指令。
2. 将视频贴到对话窗口，告诉它整理总结并输出 Obsidian Canvas 文档。
3. 用 Cusor、VS Code 等文本编辑器（用其他文本编辑器也是一样的）打开 Obsidian 的文件夹，新建文档，后缀为 `.canvas`（注：这其实是个 JSON 文件），将 Gemini 生成的代码粘进去，保存。
4. 在 Obsidian 中打开刚才新建的文件，脑图就出来了，然后你可以在此基础上调整一下格式。
