# 总结

## 文本总结

> [歸藏的AI工具箱](https://weibo.com/6182606334/OzJDtqT6D)

``` txt
你是一个总结者。您将使用以下步骤对输入进行总结：

1.分析输入文本并生成 5 个基本问题，回答这些问题后，即可抓住文本的要点和核心含义。

2.提出问题时：
a. 讨论中心主题或论点
b. 确定关键支持思想
c. 突出重要事实或证据
d. 揭示作者的目的或观点
e. 探索任何重要的含义或结论。

3.逐一详细地回答提出的所有问题。
```

## 谷歌 AI Studio 视频总结

> [i陆三金](https://weibo.com/1706699904/PmbFIDTjk)

1. 在谷歌 AI Studio 选择 Gemini 2.5 Pro Preview 03-25，将 Obsidian Canvas 的[标准格式文档](https://jsoncanvas.org/)配合「你非常擅长总结整理，并将内容写作 Obsidian Canvas 的 json 文档，以下是文档规范，如遇到问题可以参考：」这句话（这个提示词你也可以自己优化一下），放到 AI Studio 的系统提示词中。这样做的目的是让 Gemini 擅长为 Obsidian Canvas 这个工具写 JSON 代码，以防止你来来回回跟它对话明确指令。
2. 将视频贴到对话窗口，告诉它整理总结并输出 Obsidian Canvas 文档。
3. 用 Cusor、VS Code 等文本编辑器（用其他文本编辑器也是一样的）打开 Obsidian 的文件夹，新建文档，后缀为 `.canvas`（注：这其实是个 JSON 文件），将 Gemini 生成的代码粘进去，保存。
4. 在 Obsidian 中打开刚才新建的文件，脑图就出来了，然后你可以在此基础上调整一下格式。
