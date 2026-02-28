#  045：在AWS上持续部署Hugo 🚀

![](img/da170456a3c63ef7fe9369037e261c69_0.png)

## 概述
在本节课中，我们将学习如何使用Hugo静态网站生成器，结合AWS云服务，建立一个能够持续部署的全球性网站。我们将从本地开发环境搭建开始，逐步完成代码推送、自动构建和部署到AWS S3与CloudFront的完整流程。这套方法能让你以极低的成本，高效地传播真实、准确的信息。

---

## 重新审视技术：为传播真实信息而战
过去一二十年，我们过于看重用户增长、参与度和估值等指标。这导致了错误信息和虚假信息的泛滥。现在是时候利用我们自己的资源来传播真实的事实了。

Hugo是一个开源工具，易于部署。你无需向托管服务商付费，可以亲手搭建一个网站，并持续向全球部署准确、有意义的信息。你可以建立一个像《华尔街日报》或《纽约时报》那样规模的网站。

我的挑战是：你可以通过传播信息来改变世界，而Hugo可以成为你使用的工具之一。

---

## Hugo网站持续部署流程总览
上一节我们介绍了Hugo的使命，本节中我们来看看在AWS上实现持续部署的具体架构流程。

让我们从源头开始审视这个流程。

![](img/da170456a3c63ef7fe9369037e261c69_0.png)

**1. 源代码管理**
首先，在源代码部分，我们可以建立一个本地服务器工作流。这个环境可以是AWS Cloud9、Github Codespaces或其他基于云的环境，也可以是你的本地桌面。我个人更喜欢使用基于云的开发环境。

我会先在本地运行所有内容，确保一切设置正确，并且能在模拟云环境中正常运行。Cloud9环境正是这样一个与后续运行环境完全一致的副本。

**2. 自动化构建与部署**
一旦我将代码推送到Github，构建服务器就会监听变化。每次Github中的代码发生更改，构建服务器都会触发一个新的部署流程。

这个过程的好处在于，使用AWS Cloud9环境，我可以在本地推送代码，用本地Hugo服务器测试更改，确保一切正常。或者，如果只是小的内容修改，我甚至可以直接在Github中编辑，这些更改会自动部署。

**3. AWS CodeBuild 与 基础设施即代码**
接下来就进入了AWS CodeBuild流程。CodeBuild可以执行一个**幂等的基础设施命令**。

这个命令可以用C#、Python或TypeScript等语言编写。这意味着你可以以编程方式、幂等地控制部署。**幂等性**意味着无论你部署多少次，每次更改产生的结果都是完全相同的。这能确保你的网站始终处于稳定、甚至只读的状态，从而难以被攻破。

然后，流程会构建你的Hugo网站，并将文件同步到S3存储桶中。这将成为你网站的基础。

**4. 最终配置**
最后一步是使用Route 53将域名指向S3存储桶，并配置AWS CloudFront（CDN）。这个工作流的妙处在于，你可以在几秒钟内部署一切。

---

## 实战演示：我的个人网站
让我们来看看如何实际操作。以下是我的个人网站 noahgift.com 的部署方式。

![](img/da170456a3c63ef7fe9369037e261c69_2.png)

核心思想是：每当我需要持续部署这个网站时，我只需要前往我的Github代码库，直接编辑网站内容、课程资料等。更改会自动部署到线上的网站。

为了展示其简单性，我甚至可以编辑README文件，只写上“bump deploy”来触发构建，而无需更改任何实际内容。

![](img/da170456a3c63ef7fe9369037e261c69_2.png)

![](img/da170456a3c63ef7fe9369037e261c69_4.png)

![](img/da170456a3c63ef7fe9369037e261c69_4.png)

我们可以看到部署成功，并且可以实时查看构建过程的详细日志。

---

![](img/da170456a3c63ef7fe9369037e261c69_6.png)

## 逐步搭建：创建开发环境
如果你想自己复现这个过程，应该怎么做呢？

![](img/da170456a3c63ef7fe9369037e261c69_7.png)

首先，我建议在AWS中创建一个新环境。

1.  进入AWS Cloud9。
2.  创建一个新环境，命名为“Hugo”。
3.  选择配置较高的机器（例如16GB RAM，8 CPU）以获得更快的响应速度。
4.  选择Amazon Linux 2操作系统（这与后续AWS CodeBuild环境一致）。
5.  设置30分钟无操作超时。
6.  创建环境。

![](img/da170456a3c63ef7fe9369037e261c69_9.png)

![](img/da170456a3c63ef7fe9369037e261c69_10.png)

![](img/da170456a3c63ef7fe9369037e261c69_6.png)
![](img/da170456a3c63ef7fe9369037e261c69_7.png)

这样，我就可以在一个与最终构建系统（将代码推送到S3的系统）完全相同的环境中开始开发。这是AWS Cloud9环境的一大优势。

---

![](img/da170456a3c63ef7fe9369037e261c69_12.png)

![](img/da170456a3c63ef7fe9369037e261c69_13.png)

## 在Cloud9中安装和配置Hugo
环境准备就绪后，我们开始安装Hugo。

这个环境提供了一个Bash Shell，并且通过基于角色的权限自动设置了AWS凭证，因此我可以与整个AWS生态系统交互，甚至直接将Hugo网站同步上去。

以下是安装步骤：

![](img/da170456a3c63ef7fe9369037e261c69_15.png)

1.  访问Hugo GitHub发布页，找到最新的64位tar.gz文件，复制链接地址。
2.  在Cloud9终端中，使用 `wget` 命令下载该文件。
    ```bash
    wget [复制的Hugo下载链接]
    ```
3.  解压下载的文件。
    ```bash
    tar -xzf hugo_*_Linux-64bit.tar.gz
    ```
4.  将Hugo二进制文件复制到系统路径。
    ```bash
    sudo cp hugo /usr/local/bin/
    ```
5.  清理下载的压缩包，并验证安装。
    ```bash
    rm hugo_*_Linux-64bit.tar.gz
    which hugo
    hugo version
    ```

![](img/da170456a3c63ef7fe9369037e261c69_16.png)

![](img/da170456a3c63ef7fe9369037e261c69_12.png)
![](img/da170456a3c63ef7fe9369037e261c69_13.png)

![](img/da170456a3c63ef7fe9369037e261c69_18.png)

![](img/da170456a3c63ef7fe9369037e261c69_19.png)

现在，Hugo已成功安装。

![](img/da170456a3c63ef7fe9369037e261c69_20.png)

![](img/da170456a3c63ef7fe9369037e261c69_22.png)

---

![](img/da170456a3c63ef7fe9369037e261c69_24.png)

## 创建并运行你的第一个Hugo站点
接下来，我们按照Hugo官方快速入门指南创建一个新站点。

![](img/da170456a3c63ef7fe9369037e261c69_26.png)

1.  使用 `hugo new site` 命令创建新站点。
    ```bash
    hugo new site quickstart
    ```
2.  进入站点目录并初始化Git仓库。
    ```bash
    cd quickstart
    git init
    ```
3.  添加一个主题（以Ananke主题为例）。
    ```bash
    git submodule add https://github.com/theNewDynamic/gohugo-theme-ananke.git themes/ananke
    ```
4.  将主题配置写入站点配置文件。
    ```bash
    echo "theme = 'ananke'" >> config.toml
    ```
5.  创建第一篇博客文章。
    ```bash
    hugo new posts/my-first-post.md
    ```
6.  **关键一步**：编辑刚创建的文章文件（`content/posts/my-first-post.md`），将文件头中的 `draft: true` 改为 `draft: false`，这样文章才会发布。然后在正文添加内容，例如“Hello World”。

![](img/da170456a3c63ef7fe9369037e261c69_15.png)
![](img/da170456a3c63ef7fe9369037e261c69_16.png)
![](img/da170456a3c63ef7fe9369037e261c69_18.png)
![](img/da170456a3c63ef7fe9369037e261c69_19.png)
![](img/da170456a3c63ef7fe9369037e261c69_20.png)
![](img/da170456a3c63ef7fe9369037e261c69_22.png)

---

![](img/da170456a3c63ef7fe9369037e261c69_28.png)

## 本地测试与远程访问配置
现在，我们可以在本地运行服务器进行测试。

1.  启动Hugo开发服务器。
    ```bash
    hugo server -D
    ```
    `-D` 参数表示包含草稿文章，但我们已将其设为非草稿，所以此参数可选。
2.  Hugo会输出一个本地地址（通常是 `http://localhost:1313`）。为了在Cloud9环境中测试，我们可以打开一个新的终端标签页，使用 `curl` 命令访问。
    ```bash
    curl http://localhost:1313
    ```
    如果看到HTML输出，说明运行正常。

![](img/da170456a3c63ef7fe9369037e261c69_24.png)

为了能从外部浏览器访问这个运行在Cloud9（本质是EC2实例）上的Hugo站点，我们需要配置安全组。

![](img/da170456a3c63ef7fe9369037e261c69_30.png)

1.  进入AWS EC2控制台，找到你的Cloud9实例所属的安全组。
2.  编辑入站规则，添加一条规则：
    *   类型：自定义TCP
    *   端口范围：1313
    *   来源：0.0.0.0/0（允许任何IP访问，仅用于测试）
3.  保存规则。

![](img/da170456a3c63ef7fe9369037e261c69_28.png)
![](img/da170456a3c63ef7fe9369037e261c69_30.png)

![](img/da170456a3c63ef7fe9369037e261c69_32.png)

![](img/da170456a3c63ef7fe9369037e261c69_33.png)

![](img/da170456a3c63ef7fe9369037e261c69_34.png)

然后，你需要让Hugo服务器绑定到所有网络接口，而不仅仅是本地回环。停止当前服务器，使用以下命令重新启动：

![](img/da170456a3c63ef7fe9369037e261c69_35.png)

```bash
hugo server -D --bind=0.0.0.0 --baseURL=http://[你的EC2实例公有IP]:1313
```

现在，你就可以通过浏览器访问 `http://[你的EC2实例公有IP]:1313` 来查看网站了。在Cloud9中修改文章内容并保存，刷新浏览器页面，可以看到网站内容实时更新。

![](img/da170456a3c63ef7fe9369037e261c69_32.png)
![](img/da170456a3c63ef7fe9369037e261c69_33.png)
![](img/da170456a3c63ef7fe9369037e261c69_34.png)
![](img/da170456a3c63ef7fe9369037e261c69_35.png)

这是一个非常高效的本地开发工作流。

---

## 实现持续部署：CodeBuild 与 Buildspec.yml
当你完成本地开发后，下一步就是将其自动化。就像我做的那样，你需要将代码推送到Github仓库，并配置AWS CodeBuild。

实现自动化的“秘诀”在于一个名为 `buildspec.yml` 的配置文件。它完成了大部分工作。

以下是 `buildspec.yml` 文件的核心步骤：

```yaml
version: 0.2
phases:
  install:
    commands:
      # 1. 下载并安装指定版本的Hugo
      - wget https://github.com/gohugoio/hugo/releases/download/v0.XX.X/hugo_0.XX.X_Linux-64bit.tar.gz
      - tar -xzf hugo_0.XX.X_Linux-64bit.tar.gz
      - sudo cp hugo /usr/local/bin/
  build:
    commands:
      # 2. 使用Hugo构建静态网站（生成public/目录）
      - hugo
  post_build:
    commands:
      # 3. 将构建好的文件同步到S3存储桶
      - aws s3 sync public/ s3://你的存储桶名称 --delete
      # 4. (可选) 设置缓存控制头，优化CDN缓存
      - aws s3 cp s3://你的存储桶名称 s3://你的存储桶名称 --recursive --metadata-directive REPLACE --cache-control max-age=31536000
      # 5. 使CloudFront CDN缓存失效，确保用户立即看到新内容
      - aws cloudfront create-invalidation --distribution-id 你的CloudFront分配ID --paths "/*"
```

这个文件定义了三个阶段：
1.  **安装**：在构建环境中安装Hugo。
2.  **构建**：运行 `hugo` 命令生成网站静态文件。
3.  **构建后**：将文件同步到S3，并触发CloudFront缓存刷新。

---

## 配置AWS服务：S3、Route 53 与 IAM
要使整个流程运转起来，还需要正确配置几项AWS服务。

**1. Amazon S3 存储桶**
*   创建一个S3存储桶（例如以你的网站命名）。
*   在存储桶属性中**启用“静态网站托管”**。
*   在存储桶权限中，添加一个**存储桶策略**，允许公开读取访问（只读）。这是让外界能访问你网站的关键。

![](img/da170456a3c63ef7fe9369037e261c69_37.png)

![](img/da170456a3c63ef7fe9369037e261c69_37.png)

![](img/da170456a3c63ef7fe9369037e261c69_39.png)

**2. AWS CodeBuild 项目**
*   在CodeBuild中创建新的构建项目。
*   将源代码源设置为你的Github仓库。
*   选择环境镜像：托管镜像 -> Amazon Linux 2 -> 标准运行时。
*   **重要**：创建一个新的服务角色，或使用现有角色。这个角色必须拥有向S3写入数据以及使CloudFront缓存失效的权限（`s3:PutObject`, `s3:ListBucket`, `cloudfront:CreateInvalidation` 等）。
*   在“构建规范”部分，选择“使用 buildspec.yml 文件”。

**3. AWS IAM (身份和访问管理)**
你需要为CodeBuild创建一个具有足够权限的角色。
1.  进入IAM控制台。
2.  创建新角色，受信任实体类型选择“AWS服务”，用例选择“CodeBuild”。
3.  附加策略：至少需要包含AmazonS3FullAccess（或更细粒度的策略）和CloudFrontFullAccess（或自定义策略）的策略。
4.  创建角色，并在创建CodeBuild项目时选择此角色。

![](img/da170456a3c63ef7fe9369037e261c69_39.png)

**4. Amazon Route 53 (DNS)**
*   在Route 53中，将你的域名（或子域名）的A记录或别名记录指向S3静态网站托管端点。

**5. Amazon CloudFront (CDN)**
*   创建一个CloudFront分发，源站选择你刚配置的S3静态网站托管端点。
*   这将为你的网站提供全球加速和缓存。`buildspec.yml` 中的最后一条命令就是用来刷新这个CDN缓存的。

![](img/da170456a3c63ef7fe9369037e261c69_41.png)

---

## 完整步骤总结
本节课中我们一起学习了在AWS上为Hugo网站搭建持续部署管道的完整过程。让我们回顾一下所有步骤：

1.  **准备AWS账户与开发环境**：确保你有一个AWS账户，并启动一个Cloud9环境。
2.  **配置Git**：在Cloud9中设置Git用户信息，并配置SSH密钥以便与Github通信。
3.  **安装Hugo**：在Cloud9环境中下载、解压并安装最新版Hugo到 `/usr/local/bin/`。
4.  **创建Hugo站点**：使用快速入门指南创建新站点，添加主题（作为Git子模块），创建内容并运行本地服务器测试。
5.  **配置安全组**：为Cloud9实例的安全组开放1313端口，以便临时远程访问测试。
6.  **手动部署测试**：
    *   在AWS S3上创建一个存储桶，并启用静态网站托管功能。
    *   按照AWS官方文档正确配置存储桶策略（公开只读）。
    *   你可以手动从Cloud9使用 `aws s3 sync` 命令将 `public/` 目录同步到S3，验证网站是否能正常访问。
7.  **配置自动化构建**：
    *   在IAM中创建CodeBuild服务角色，赋予其访问S3和CloudFront的权限。
    *   在CodeBuild中创建构建项目，连接到你的Github仓库，使用Amazon Linux 2环境，并指定正确的服务角色。
    *   在项目设置中，确保选中“报告Git子模块”选项。
    *   在代码库根目录创建并提交 `buildspec.yml` 文件。
8.  **配置DNS与CDN**：
    *   在Route 53中将域名指向S3端点。
    *   创建CloudFront分发以加速网站，并在 `buildspec.yml` 中配置缓存失效步骤。
9.  **触发自动化**：现在，每次你向Github仓库推送代码，CodeBuild都会自动执行构建、部署和缓存刷新流程。

通过以上步骤，你就建立了一个非常直接、高效的流程，可以搭建一个全球规模的网站，其架构能力可与大型新闻网站媲美。

祝你成功！😊