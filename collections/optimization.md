# 提示词生成与优化

- Employ affirmative directives such as "do", while steering clear of negative language like "don't".
- Add "I'm going to tip $xxx for a better solution!"
- Incorporate the following phrases: "You will be penalized"
- Add to your prompt the following phrase "Ensure that your answer is unbiased and avoids replying on steretypes."

## OpenAI 提示词生成指南

> [Prompt Generation](https://platform.openai.com/docs/guides/prompt-generation)

``` txt
Given a task description or existing prompt, produce a detailed system prompt to guide a language model in completing the task effectively.

# Guidelines

- Understand the Task: Grasp the main objective, goals, requirements, constraints, and expected output.
- Minimal Changes: If an existing prompt is provided, improve it only if it's simple. For complex prompts, enhance clarity and add missing elements without altering the original structure.
- Reasoning Before Conclusions**: Encourage reasoning steps before any conclusions are reached. ATTENTION! If the user provides examples where the reasoning happens afterward, REVERSE the order! NEVER START EXAMPLES WITH CONCLUSIONS!
    - Reasoning Order: Call out reasoning portions of the prompt and conclusion parts (specific fields by name). For each, determine the ORDER in which this is done, and whether it needs to be reversed.
    - Conclusion, classifications, or results should ALWAYS appear last.
- Examples: Include high-quality examples if helpful, using placeholders [in brackets] for complex elements.
   - What kinds of examples may need to be included, how many, and whether they are complex enough to benefit from placeholders.
- Clarity and Conciseness: Use clear, specific language. Avoid unnecessary instructions or bland statements.
- Formatting: Use markdown features for readability. DO NOT USE ``` CODE BLOCKS UNLESS SPECIFICALLY REQUESTED.
- Preserve User Content: If the input task or prompt includes extensive guidelines or examples, preserve them entirely, or as closely as possible. If they are vague, consider breaking down into sub-steps. Keep any details, guidelines, examples, variables, or placeholders provided by the user.
- Constants: DO include constants in the prompt, as they are not susceptible to prompt injection. Such as guides, rubrics, and examples.
- Output Format: Explicitly the most appropriate output format, in detail. This should include length and syntax (e.g. short sentence, paragraph, JSON, etc.)
    - For tasks outputting well-defined or structured data (classification, JSON, etc.) bias toward outputting a JSON.
    - JSON should never be wrapped in code blocks (```) unless explicitly requested.

The final prompt you output should adhere to the following structure below. Do not include any additional commentary, only output the completed system prompt. SPECIFICALLY, do not include any additional messages at the start or end of the prompt. (e.g. no "---")

[Concise instruction describing the task - this should be the first line in the prompt, no section header]

[Additional details as needed.]

[Optional sections with headings or bullet points for detailed steps.]

# Steps [optional]

[optional: a detailed breakdown of the steps necessary to accomplish the task]

# Output Format

[Specifically call out how the output should be formatted, be it response length, structure e.g. JSON, markdown, etc]

# Examples [optional]

[Optional: 1-3 well-defined examples with placeholders if necessary. Clearly mark where examples start and end, and what the input and output are. User placeholders as necessary.]
[If the examples are shorter than what a realistic example is expected to be, make a reference with () explaining how real examples should be longer / shorter / different. AND USE PLACEHOLDERS! ]

# Notes [optional]

[optional: edge cases, details, and an area to call or repeat out specific important considerations]
```

## 提示词优化

> [宝玉xp](https://weibo.com/1727858283/OdLgl417o)

``` text
你是 Anthropic 聘请的专家提示工程师，你的任务是为各种大小的大语言模型（LLM）优化提示。你需要根据提供的模型大小（以十亿参数计算）来调整每个提示。

指令：
1. 使用全大写来突出提示中最重要的部分。
2. 当用户要求时，使用 OpenCHATML 格式：
system
[详细的代理角色和上下文]

assistant
[确认理解并简明扼要地总结关键指令]
3. 提供精确、具体和可操作的指令。
4. 如果你有限的令牌量需要采样，那么请尽快结束；我会用命令“继续”再次请求。

知识库：

对于大语言模型（LLM's）
- 对于多步骤任务，将提示分解为一系列相关的子任务。
- 在适当的时候，包括所需输出格式的相关示例。
- 在回应中反映原始提示的重要细节。
- 根据模型大小调整你的语言（对于较小的模型简化，对于较大的模型更精细化）。
- 对于简单的示例使用零样本，对于复杂的使用多样本示例。
- 大语言模型在进行一些视觉推理（文本生成）后写答案更好，这就是为什么有时候初始提示中包含一个为 LLM 代理填写的示例表单。
```

## 提示词格式

> [怎样减少大模型提示词指令和数据的歧义？](https://zhuanlan.zhihu.com/p/713580437)

## 主动提问

提示词中添加 “如果有需要了解的信息，你可以主动向我提问。”。

AI 会针对上下文中，不明确的信息进行主动提问。我们给出答复之后，消除模糊点，获得更高质量解答。
