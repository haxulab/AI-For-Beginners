# 测验

这些测验是 AI 课程的课前和课后测验，链接如下：https://aka.ms/ai-beginners

## 添加翻译后的测验集

通过在 `assets/translations` 文件夹中创建相应的测验结构来添加测验翻译。规范的测验在 `assets/translations/en` 中。测验按课程分成若干组。请确保将编号与适当的测验部分对齐。在整个课程中总共有 40 个测验，从 0 开始计数。

编辑翻译完成后，编辑翻译文件夹中的 index.js 文件，以按 `en` 中的惯例导入所有文件。

编辑 `assets/translations` 中的 `index.js` 文件以导入新的翻译文件。

然后，编辑该应用程序中的 `App.vue` 文件中的下拉菜单以添加您的语言。将本地化缩写与您的语言文件夹名称匹配。

最后，如果存在已翻译的课程，请编辑其中的所有测验链接，以将本地化作为查询参数包含在内: 例如 `?loc=fr`。

## 项目设置

```
npm install
```

### 编译并热重载开发环境

```
npm run serve
```

### 编译并压缩生产环境

```
npm run build
```

### 修复文件中的代码样式问题

```
npm run lint
```

### 自定义配置

请参见 [配置参考](https://cli.vuejs.org/config/)。

致谢: 感谢此测验应用程序的原始版本：https://github.com/arpan45/simple-quiz-vue

## 部署到 Azure

以下是帮助您快速入门的分步指南：

1. 派生 GitHub 仓库
确保您的静态 web 应用代码在您的 GitHub 仓库中。派生这个仓库。

2. 创建一个 Azure 静态 Web 应用
- 创建一个 [Azure 账号](http://azure.microsoft.com)
- 前往 [Azure 门户](https://portal.azure.com)
- 点击“创建资源”，然后搜索“静态 Web 应用”。
- 点击“创建”。

3. 配置静态 Web 应用
- 基础：订阅：选择您的 Azure 订阅。
- 资源组：创建一个新的资源组或使用现有的资源组。
- 名称：为您的静态 Web 应用提供一个名称。
- 区域：选择离您的用户最近的区域。

- #### 部署详情：
- 来源：选择“GitHub”。
- GitHub 帐户：授权 Azure 访问您的 GitHub 帐户。
- 组织：选择您的 GitHub 组织。
- 仓库：选择包含您的静态 Web 应用的仓库。
- 分支：选择要部署的分支。

- #### 构建详情：
- 构建预设：选择构建应用程序所用的框架（例如，React，Angular，Vue 等）。
- 应用位置：指定包含您的应用代码的文件夹（例如，如果在根目录，则为 /）。
- API 位置：如果有 API，请指定其位置（可选）。
- 输出位置：指定生成输出的文件夹（例如，build 或 dist）。

4. 审核和创建
审核您的设置并点击“创建”。Azure 将设置必要的资源并在您的仓库中创建一个 GitHub Actions 工作流。

5. GitHub Actions 工作流
Azure 将自动在您的仓库中创建一个 GitHub Actions 工作流文件（.github/workflows/azure-static-web-apps-<name>.yml）。该工作流将处理构建和部署过程。

6. 监控部署
前往您的 GitHub 仓库中的“Actions”标签。
您应会看到一个正在运行的工作流。该工作流将构建并部署您的静态 Web 应用到 Azure。
工作流完成后，您的应用将会在提供的 Azure URL 上上线。

### 示例工作流文件

这是 GitHub Actions 工作流文件的示例：
名称：Azure 静态 Web 应用 CI/CD
```
on:
  push:
    branches:
      - main
  pull_request:
    types: [opened, synchronize, reopened, closed]
    branches:
      - main

jobs:
  build_and_deploy_job:
    runs-on: ubuntu-latest
    name: Build and Deploy Job
    steps:
      - uses: actions/checkout@v2
      - name: Build And Deploy
        id: builddeploy
        uses: Azure/static-web-apps-deploy@v1
        with:
          azure_static_web_apps_api_token: ${{ secrets.AZURE_STATIC_WEB_APPS_API_TOKEN }}
          repo_token: ${{ secrets.GITHUB_TOKEN }}
          action: "upload"
          app_location: "etc/quiz-app # 应用源代码路径"
          api_location: ""API 源代码路径可选
          output_location: "dist" #生成的应用内容目录 - 可选
```

### 其他资源
- [Azure 静态 Web 应用文档](https://learn.microsoft.com/azure/static-web-apps/getting-started)
- [GitHub Actions 文档](https://docs.github.com/actions/use-cases-and-examples/deploying/deploying-to-azure-static-web-app)
