#  044：构建持续部署的容器化FastAPI微服务 🚀

![](img/50c9f232ee944eb90aa3fc906bfa4e50_0.png)

在本节课中，我们将学习如何将一个已有的NLP库代码，转化为一个可投入生产环境的、容器化的Web微服务。我们将使用FastAPI框架构建Web服务，使用Docker进行容器化，并最终将其部署到AWS云平台，实现一个具备持续部署能力的完整应用。

为了将我们的代码投入生产环境并使其可运行，我们需要构建一些额外的组件。首先，我们需要创建一个Dockerfile来将其容器化。其次，我们需要构建一个Web应用，这里我们将使用FastAPI框架。完成这些组件后，我们就可以将其推送到云端。AWS提供了一个名为Cloud 9的优秀开发环境，我们将使用它。此外，我们还可以使用一项名为App Runner的服务，这是一个在AWS生态系统中与容器配合良好的服务。因此，本节的核心逻辑是：我们有一个现成的NLP库代码，我们将把它转变为一个Web服务。

## 在AWS Cloud 9中设置开发环境 💻

![](img/50c9f232ee944eb90aa3fc906bfa4e50_2.png)

![](img/50c9f232ee944eb90aa3fc906bfa4e50_4.png)

首先，我将转到AWS控制台。在AWS服务中，我们找到Cloud 9。Cloud 9非常棒，因为它允许我们在最终将运行的环境中构建应用，操作系统和上下文环境都是一致的，角色等也是如此。

![](img/50c9f232ee944eb90aa3fc906bfa4e50_6.png)

我将创建一个新的环境，命名为“NLP Web Service Fast API”。添加一个简短的描述：“用于构建容器化、持续部署的FastAPI应用”。我将选择一个性能较强的机器类型，例如c5.xlarge，因为我需要构建容器。操作系统选择Amazon Linux，然后点击下一步。

![](img/50c9f232ee944eb90aa3fc906bfa4e50_8.png)

![](img/50c9f232ee944eb90aa3fc906bfa4e50_10.png)

![](img/50c9f232ee944eb90aa3fc906bfa4e50_0.png)

唯一必要的集成步骤是创建SSH密钥并将其添加到GitHub，这非常简单。在环境启动的同时，我可以去GitHub进行准备。进入GitHub设置，找到“SSH and GPG keys”，添加一个新的SSH密钥，将其命名为“cloud9_nlp”。

![](img/50c9f232ee944eb90aa3fc906bfa4e50_2.png)

当Cloud 9环境启动后，我立即在终端中输入 `ssh-keygen -t rsa` 来生成SSH密钥。然后，我将公钥复制并添加到刚才在GitHub创建的密钥中。

![](img/50c9f232ee944eb90aa3fc906bfa4e50_4.png)

![](img/50c9f232ee944eb90aa3fc906bfa4e50_12.png)

![](img/50c9f232ee944eb90aa3fc906bfa4e50_14.png)

添加密钥后，我回到我的GitHub项目仓库，复制SSH克隆链接。在Cloud 9终端中，使用 `git clone` 命令克隆仓库。

![](img/50c9f232ee944eb90aa3fc906bfa4e50_16.png)

![](img/50c9f232ee944eb90aa3fc906bfa4e50_6.png)

![](img/50c9f232ee944eb90aa3fc906bfa4e50_18.png)

克隆完成后，我创建一个Python虚拟环境。命令是 `python -m venv venv`。然后激活虚拟环境：`source venv/bin/activate`。为了方便，我可以将这个激活命令添加到 `~/.bashrc` 文件中。打开一个新的终端标签页，虚拟环境就会自动激活。

![](img/50c9f232ee944eb90aa3fc906bfa4e50_20.png)

![](img/50c9f232ee944eb90aa3fc906bfa4e50_22.png)

现在，我可以看到我们所有的代码。接下来，我会立即运行 `make install` 或直接运行 `make all` 命令，它会执行安装、测试、代码格式化等一系列步骤。这能确保在新环境中一切运行正常，没有意外。这就是测试、代码规范和持续集成的优势——它减少了工作量，而非增加。

![](img/50c9f232ee944eb90aa3fc906bfa4e50_8.png)

运行顺利，代码还进行了一些格式化调整。我将这些更改提交到Git仓库：`git add .`， `git commit -m “Initial commit”`。提交信息可以随意一些，因为我们只是在测试。

## 创建Dockerfile和FastAPI Web服务 🐳

![](img/50c9f232ee944eb90aa3fc906bfa4e50_24.png)

现在，我需要创建一个Dockerfile和一个Web服务。我可以从我的GitHub其他项目中找一个FastAPI模板，因为很多代码是样板文件，重用模板是个好主意。

![](img/50c9f232ee944eb90aa3fc906bfa4e50_26.png)

![](img/50c9f232ee944eb90aa3fc906bfa4e50_10.png)

![](img/50c9f232ee944eb90aa3fc906bfa4e50_28.png)

对于Dockerfile，我将使用一个基础镜像。这里我选择基于Amazon Linux的轻量版Lambda Python镜像。我需要确认有Python 3.9版本可用。搜索“lambda python”并排序，可以找到 `public.ecr.aws/lambda/python:3.9` 这个镜像。

![](img/50c9f232ee944eb90aa3fc906bfa4e50_30.png)

![](img/50c9f232ee944eb90aa3fc906bfa4e50_12.png)

Dockerfile的基本逻辑是：使用基础镜像，创建一个应用目录，将我们的代码复制进去，安装依赖，然后运行。这是一个简单的容器化过程。

![](img/50c9f232ee944eb90aa3fc906bfa4e50_32.png)

接下来，我创建Web服务的主文件 `main.py`。同样，我可以从其他项目复制一个FastAPI模板代码。

![](img/50c9f232ee944eb90aa3fc906bfa4e50_34.png)

![](img/50c9f232ee944eb90aa3fc906bfa4e50_14.png)

模板中导入了FastAPI和Uvicorn。我将应用命名为“Hello NLP”。现在需要构建核心逻辑，并正确导入我们的NLP库。这时，我们之前构建的命令行工具就派上用场了，因为它清楚地告诉我们该如何导入。

![](img/50c9f232ee944eb90aa3fc906bfa4e50_36.png)

我修改端点函数，让它接收一个字符串参数，比如叫 `wiki_phrase`。函数描述为“从Wikipedia名称生成名词短语”。函数内部直接调用我们NLP库中的 `get_phrases(name)` 函数。由于大部分工作已经完成，这里代码会很简单。

![](img/50c9f232ee944eb90aa3fc906bfa4e50_38.png)

![](img/50c9f232ee944eb90aa3fc906bfa4e50_40.png)

为了调试，我添加一个简单的 `print` 语句，当端点被调用时打印信息。

同时，我需要更新 `requirements.txt` 文件，添加 `fastapi` 和 `uvicorn` 依赖。然后再次运行 `make all` 来确保一切正常。

![](img/50c9f232ee944eb90aa3fc906bfa4e50_42.png)

理论上，现在可以通过运行 `python main.py` 来启动服务。在Cloud 9中，还可以使用“Preview”功能来预览运行中的应用。

![](img/50c9f232ee944eb90aa3fc906bfa4e50_44.png)

![](img/50c9f232ee944eb90aa3fc906bfa4e50_46.png)

![](img/50c9f232ee944eb90aa3fc906bfa4e50_16.png)

![](img/50c9f232ee944eb90aa3fc906bfa4e50_48.png)

![](img/50c9f232ee944eb90aa3fc906bfa4e50_50.png)

![](img/50c9f232ee944eb90aa3fc906bfa4e50_52.png)

![](img/50c9f232ee944eb90aa3fc906bfa4e50_54.png)

## 测试本地FastAPI服务 🧪

![](img/50c9f232ee944eb90aa3fc906bfa4e50_56.png)

服务启动后，我可以测试它。默认有一个 `/` 根路径返回“Hello NLP”。我们创建的端点是 `/wiki_phrases/{name}`。为了测试，我需要知道Wikipedia的页面命名格式。例如，“Los_Angeles_Lakers”可能带有下划线。我们可以先简单测试一下。

![](img/50c9f232ee944eb90aa3fc906bfa4e50_58.png)

![](img/50c9f232ee944eb90aa3fc906bfa4e50_60.png)

访问 `/docs` 路径，这是FastAPI自动生成的交互式API文档（Swagger UI）。这是一个杀手级功能。我可以在UI中点击我们的端点，选择“Try it out”，输入“Los_Angeles_Lakers”并执行。如果一切正常，应该能返回生成的短语。

![](img/50c9f232ee944eb90aa3fc906bfa4e50_18.png)

这表示我们已经拥有了一个功能完整的Web服务端点，取得了巨大进展。我将提交这些更改：`git add .`， `git commit -m “Adding FastAPI service”`，然后推送到GitHub。

## 部署到AWS：推送容器镜像 ☁️

现在开始部署到AWS。首先，我需要将Docker镜像推送到AWS Elastic Container Registry (ECR)。

在AWS控制台找到ECR服务，创建一个新的仓库，命名为 `nlp-wikipedia-fastapi`。

![](img/50c9f232ee944eb90aa3fc906bfa4e50_20.png)

![](img/50c9f232ee944eb90aa3fc906bfa4e50_62.png)

![](img/50c9f232ee944eb90aa3fc906bfa4e50_64.png)

创建仓库后，查看“Push commands”推送指令。我需要按顺序在Cloud 9终端中执行这些命令：
1.  登录ECR：`aws ecr get-login-password ... | docker login ...`
2.  构建Docker镜像：`docker build -t nlp-wikipedia-fastapi .`
3.  为镜像打上ECR仓库的标签：`docker tag nlp-wikipedia-fastapi:latest <仓库URI>:latest`
4.  推送镜像：`docker push <仓库URI>:latest`

![](img/50c9f232ee944eb90aa3fc906bfa4e50_66.png)

![](img/50c9f232ee944eb90aa3fc906bfa4e50_22.png)

因为使用了性能较强的机器，构建和推送过程会比较快。推送完成后，在ECR仓库中就能看到我们的镜像。为了后续演示方便，我将这个仓库设置为公开。

## 使用AWS App Runner进行部署 ⚡

![](img/50c9f232ee944eb90aa3fc906bfa4e50_68.png)

接下来是更有趣的部分：使用AWS App Runner服务进行部署。App Runner可以直接指向我们ECR中的容器镜像。

![](img/50c9f232ee944eb90aa3fc906bfa4e50_70.png)

在AWS控制台找到App Runner服务，点击“Create service”。选择源为“Container registry”，然后选择“Amazon ECR”。浏览并选择我们刚刚创建的 `nlp-wikipedia-fastapi` 镜像。

![](img/50c9f232ee944eb90aa3fc906bfa4e50_24.png)

部署设置有两个选项：手动和自动。自动部署非常方便，它意味着如果我将来更新了代码并推送了新镜像，构建系统（如AWS CodeBuild或GitHub Actions）可以自动触发部署。对于演示，我选择手动部署。

![](img/50c9f232ee944eb90aa3fc906bfa4e50_72.png)

配置服务名称，例如 `nlp-wikipedia-fastapi`。需要配置端口映射，我们的容器暴露的是8080端口，所以这里填8080。可以配置自动扩缩容、健康检查、安全网络和可观测性工具。对于演示，默认设置即可。

![](img/50c9f232ee944eb90aa3fc906bfa4e50_74.png)

![](img/50c9f232ee944eb90aa3fc906bfa4e50_26.png)

点击“Next”并创建服务。部署需要几分钟时间。App Runner会提供一个完整的HTTPS URL。在服务控制台，我们可以查看事件日志、部署日志、应用日志和监控指标（如请求数、2xx/4xx/5xx状态码）。如果开启了可观测性，还能查看服务拓扑图。这基本上是一个构建生产级Web服务的一站式解决方案。

![](img/50c9f232ee944eb90aa3fc906bfa4e50_76.png)

![](img/50c9f232ee944eb90aa3fc906bfa4e50_78.png)

## 本地验证与问题调试 🔧

在等待部署的同时，我们可以在本地验证容器。在Cloud 9中运行 `docker images` 列出镜像，找到我们刚构建的镜像ID。然后使用 `docker run -p 8080:8080 <镜像ID>` 在本地运行容器。通过Cloud 9的预览功能，可以像之前一样测试本地容器，访问 `/docs` 并尝试调用接口。

![](img/50c9f232ee944eb90aa3fc906bfa4e50_80.png)

![](img/50c9f232ee944eb90aa3fc906bfa4e50_28.png)

![](img/50c9f232ee944eb90aa3fc906bfa4e50_82.png)

![](img/50c9f232ee944eb90aa3fc906bfa4e50_84.png)

这时，我发现了一个问题。当我在生产环境的App Runner上测试“Los Angeles Lakers”时，返回了“Internal Server Error”。但在本地运行的容器中测试，却成功了。这帮助我们定位了一个Bug。

![](img/50c9f232ee944eb90aa3fc906bfa4e50_86.png)

检查本地容器的日志，发现错误信息提示缺少NLTK的数据集。问题在于Dockerfile中没有下载必要的NLTK数据。修复方法很简单：在Dockerfile的 `RUN` 指令中添加下载数据的命令，例如 `RUN python -m nltk.downloader punkt averaged_perceptron_tagger`。

![](img/50c9f232ee944eb90aa3fc906bfa4e50_88.png)

![](img/50c9f232ee944eb90aa3fc906bfa4e50_90.png)

![](img/50c9f232ee944eb90aa3fc906bfa4e50_30.png)

修改Dockerfile后，需要重新构建、标记并推送镜像到ECR。这正体现了拥有一个自动化构建服务器的价值。我们手动执行这些命令。

![](img/50c9f232ee944eb90aa3fc906bfa4e50_92.png)

## 重新部署并验证 ✅

镜像推送完成后，回到App Runner服务控制台，手动触发一次新的部署。部署状态会更新，我们可以从日志中观察进度：“Pulling image” -> “Start deploying” -> “Deployment succeeded”。

部署成功后，再次访问生产环境的 `/docs` 页面，测试“Los Angeles Lakers”。这次，请求成功并返回了名词短语列表。

![](img/50c9f232ee944eb90aa3fc906bfa4e50_32.png)

![](img/50c9f232ee944eb90aa3fc906bfa4e50_94.png)

![](img/50c9f232ee944eb90aa3fc906bfa4e50_96.png)

同时，我们可以在App Runner的“Logs” -> “Application logs”中看到我们添加的 `print` 调试语句的输出，这非常有助于监控和调试。

## 总结 📝

![](img/50c9f232ee944eb90aa3fc906bfa4e50_98.png)

本节课中，我们一起完成了一个完整的微服务生产化流程：
1.  **环境搭建**：在AWS Cloud 9中设置了与生产环境一致的开发环境。
2.  **服务开发**：使用FastAPI将现有的NLP库封装成RESTful Web服务端点。
3.  **容器化**：编写Dockerfile，将应用及其依赖打包成可移植的容器镜像。
4.  **镜像管理**：将Docker镜像推送至AWS ECR仓库进行存储和管理。
5.  **云部署**：利用AWS App Runner服务，轻松地将容器镜像部署为可自动扩缩容、带监控日志的生产级Web服务。
6.  **调试与迭代**：通过对比本地与生产环境，发现并修复了依赖缺失的问题，演示了真实的开发运维流程。

![](img/50c9f232ee944eb90aa3fc906bfa4e50_100.png)

![](img/50c9f232ee944eb90aa3fc906bfa4e50_102.png)

我们构建的这个系统具备了持续部署的潜力，只需配置自动化构建流水线，即可在代码更新时自动完成从构建、测试到部署的全过程。容器化技术确保了应用在不同环境中的一致性，是构建现代微服务的推荐方式。