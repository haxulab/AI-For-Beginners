# 通过翻译课程做贡献

我们欢迎对本教程中的课程进行翻译！

## 指导方针

在每个课程文件夹和课程介绍文件夹中都有包含翻译后的markdown文件的文件夹。

> 注意，请不要翻译代码示例文件中的任何代码；唯一需要翻译的是README、作业和测验。谢谢！

翻译文件应遵循以下命名约定：

**README._[language]__chs.md**

其中_[language]_是遵循ISO 639-1标准的两字母语言缩写（例如，西班牙语为`README.es_chs.md`，荷兰语为`README.nl_chs.md`）。

**assignment._[language]__chs.md**

类似于Readme，请也翻译作业。

**测验**

1. 通过在此处添加一个文件将您的翻译添加到quiz-app：https://github.com/microsoft/AI-For-Beginners/tree/main/etc/quiz-app/src/assets/translations，采用正确的命名约定（en.json，fr.json）。**但是请不要本地化'true'或'false'这两个词。谢谢！**

2. 将您的语言代码添加到quiz-app的App.vue文件中的下拉菜单中。

3. 编辑quiz-app的[translations index.js文件](https://github.com/microsoft/AI-For-Beginners/blob/main/etc/quiz-app/src/assets/translations/index.js)以添加您的语言。

4. 最后，编辑您翻译的README_chs.md文件中的所有测验链接，直接指向您翻译后的测验：https://red-field-0a6ddfd03.1.azurestaticapps.net/quiz/1 变为 https://red-field-0a6ddfd03.1.azurestaticapps.net/quiz/1?loc=id

**谢谢**

我们非常感谢您的努力！