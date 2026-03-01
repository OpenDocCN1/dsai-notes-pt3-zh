#  070：使用 Google Cloud Run 运行 Rust Actix 微服务 🚀

![](img/8822931ca1ee39dbd086b1e8b217bcd7_0.png)

## 概述
在本节课中，我们将学习如何在 Google Cloud Shell 环境中安装 Rust，并创建一个简单的 Actix-web 微服务。随后，我们将把这个微服务容器化，并最终部署到 Google Cloud Run 平台，使其成为一个公开可访问的 Web 服务。

---

## 在 Cloud Shell 中安装 Rust 🛠️

首先，我们需要在 Google Cloud Shell 环境中安装 Rust 编译器。Cloud Shell 是一个临时的在线环境，非常适合快速测试和开发。

![](img/8822931ca1ee39dbd086b1e8b217bcd7_2.png)

以下是安装 Rust 的步骤：

![](img/8822931ca1ee39dbd086b1e8b217bcd7_4.png)

![](img/8822931ca1ee39dbd086b1e8b217bcd7_6.png)

1.  打开 Cloud Shell 终端。
2.  运行以下命令来安装 Rust：
    ```bash
    curl --proto ‘=https’ --tlsv1.2 -sSf https://sh.rustup.rs | sh
    ```
3.  安装完成后，需要加载 Cargo（Rust 的包管理器）的环境变量：
    ```bash
    source $HOME/.cargo/env
    ```

![](img/8822931ca1ee39dbd086b1e8b217bcd7_8.png)

现在，我们可以验证 Rust 是否安装成功。让我们创建一个新的 Rust 项目并运行它。

```bash
cargo new hello
cd hello
cargo run
```

![](img/8822931ca1ee39dbd086b1e8b217bcd7_10.png)

如果一切顺利，终端将输出 `Hello, world!`，这表明 Rust 环境已准备就绪。

![](img/8822931ca1ee39dbd086b1e8b217bcd7_12.png)

---

## 使用 Cloud Shell 编辑器进行开发 ✍️

![](img/8822931ca1ee39dbd086b1e8b217bcd7_14.png)

上一节我们介绍了如何在终端中安装 Rust，本节中我们来看看如何使用 Cloud Shell 内置的编辑器来编写和修改代码。

![](img/8822931ca1ee39dbd086b1e8b217bcd7_16.png)

Cloud Shell 提供了一个基于 Web 的代码编辑器，功能比纯终端更强大。我们可以在这里编辑源代码文件。

![](img/8822931ca1ee39dbd086b1e8b217bcd7_18.png)

1.  在 Cloud Shell 界面中，点击“打开编辑器”按钮。
2.  在左侧的文件浏览器中，导航到我们刚才创建的 `hello` 项目。
3.  打开 `src/main.rs` 文件，将 `println!` 的内容修改为：
    ```rust
    println!(“Hello GCP from Rust!”);
    ```
4.  保存文件，然后回到终端，在项目目录下再次运行 `cargo run`。

![](img/8822931ca1ee39dbd086b1e8b217bcd7_20.png)

现在，程序将输出我们自定义的问候语。为了更方便地管理项目，我们还可以创建一个 `Makefile` 来定义常用的命令，如格式化代码、代码检查和运行。

![](img/8822931ca1ee39dbd086b1e8b217bcd7_22.png)

![](img/8822931ca1ee39dbd086b1e8b217bcd7_24.png)

![](img/8822931ca1ee39dbd086b1e8b217bcd7_26.png)

---

![](img/8822931ca1ee39dbd086b1e8b217bcd7_28.png)

## 为 Cloud Run 准备 Rust 微服务 🌐

![](img/8822931ca1ee39dbd086b1e8b217bcd7_30.png)

我们已经有了一个可以运行的 Rust 程序，但 Cloud Run 需要的是能够处理 HTTP 请求的 Web 服务。因此，我们需要将程序改造成一个 Web 微服务。

![](img/8822931ca1ee39dbd086b1e8b217bcd7_32.png)

![](img/8822931ca1ee39dbd086b1e8b217bcd7_34.png)

我们将使用 **Actix-web** 框架，它是 Rust 生态中最流行的 Web 框架之一。以下是改造步骤：

![](img/8822931ca1ee39dbd086b1e8b217bcd7_36.png)

![](img/8822931ca1ee39dbd086b1e8b217bcd7_37.png)

1.  首先，我们需要修改 `Cargo.toml` 文件来添加依赖项。
2.  然后，编写一个简单的 HTTP 服务器代码。

![](img/8822931ca1ee39dbd086b1e8b217bcd7_39.png)

![](img/8822931ca1ee39dbd086b1e8b217bcd7_41.png)

![](img/8822931ca1ee39dbd086b1e8b217bcd7_43.png)

以下是 `Cargo.toml` 文件中需要添加的依赖项：

![](img/8822931ca1ee39dbd086b1e8b217bcd7_45.png)

![](img/8822931ca1ee39dbd086b1e8b217bcd7_47.png)

```toml
[dependencies]
actix-web = “4”
actix-rt = “2”
serde = { version = “1”, features = [“derive”] }
rand = “0.8”
```

接下来，我们替换 `src/main.rs` 文件的内容。以下是一个返回随机水果名称的简单 API 示例：

```rust
use actix_web::{get, App, HttpResponse, HttpServer, Responder};
use rand::seq::SliceRandom;
use serde::Serialize;

#[derive(Serialize)]
struct Fruit {
    name: String,
}

#[get(“/”)]
async fn hello() -> impl Responder {
    HttpResponse::Ok().body(“Hello world! Random Fruit API”)
}

#[get(“/fruit”)]
async fn get_random_fruit() -> impl Responder {
    let fruits = vec![“Apple”, “Banana”, “Cherry”, “Date”, “Elderberry”];
    let fruit = fruits.choose(&mut rand::thread_rng()).unwrap();
    let response = Fruit {
        name: fruit.to_string(),
    };
    HttpResponse::Ok().json(response)
}

#[actix_web::main]
async fn main() -> std::io::Result<()> {
    HttpServer::new(|| {
        App::new()
            .service(hello)
            .service(get_random_fruit)
    })
    .bind((“0.0.0.0”, 8080))?
    .run()
    .await
}
```

编写完成后，使用 `cargo run` 命令在本地运行服务。然后，打开另一个终端标签页，使用 `curl` 命令测试 API：

```bash
curl http://localhost:8080/
curl http://localhost:8080/fruit
```

如果服务返回了问候语和随机的水果 JSON 数据，说明我们的微服务已经成功运行。

---

## 创建 Dockerfile 并本地构建镜像 🐳

上一节我们创建了一个可运行的 Web 微服务，本节中我们来看看如何将其容器化，这是部署到 Cloud Run 的关键一步。

Cloud Run 运行的是容器化应用。我们需要创建一个 `Dockerfile` 来定义如何构建我们的 Rust 应用镜像。

以下是一个高效的两阶段构建 `Dockerfile` 示例。它首先在一个完整的 Rust 镜像中编译应用，然后将编译好的二进制文件复制到一个更精简的最终镜像中，以减小镜像体积。

```dockerfile
# 第一阶段：使用 Rust 官方镜像进行构建
FROM rust:latest as builder
WORKDIR /usr/src/app
COPY . .
RUN cargo build --release

# 第二阶段：使用轻量级 Debian 镜像运行应用
FROM debian:buster-slim
RUN apt-get update && apt-get install -y extra-runtime-dependencies && rm -rf /var/lib/apt/lists/*
COPY --from=builder /usr/src/app/target/release/web-docker /usr/local/bin/web-docker
CMD [“web-docker”]
```

在项目根目录下创建这个 `Dockerfile` 后，我们可以使用 Cloud Shell 编辑器中的 Cloud Code 扩展来模拟本地构建和运行。

1.  在编辑器中，找到 Cloud Code 面板。
2.  选择“在本地运行 Cloud Run 应用”。
3.  扩展会自动检测 `Dockerfile` 并启动一个本地 Minikube 集群来模拟 Cloud Run 环境，进行构建和部署测试。

这个过程会验证我们的容器配置是否正确，为真正的云端部署做好准备。

---

## 部署到 Google Cloud Run ☁️

经过本地测试，我们的容器镜像已经准备就绪。现在，我们可以将其部署到 Google Cloud Run，使其成为一个全球可访问的服务。

使用 Cloud Shell 编辑器中的 Cloud Code 扩展，部署过程非常简单直观：

1.  在 Cloud Code 面板中，找到我们正在运行的服务。
2.  点击“部署到 Cloud Run”按钮。
3.  在弹出的配置窗口中，保持默认设置（如服务名称、区域选择“完全托管”）。
4.  点击“部署”。

系统将开始执行以下步骤：
*   将我们的源代码和 `Dockerfile` 打包。
*   在 Google Cloud Build 服务中根据 `Dockerfile` 构建容器镜像。
*   将构建好的镜像推送到 Google Container Registry。
*   在 Cloud Run 上创建并启动一个新的服务实例，并分配一个公开的 HTTPS 网址。

部署过程可能需要几分钟，具体时间取决于代码编译和镜像上传的速度。我们可以在日志窗口中查看实时进度。

部署成功后，Cloud Code 会提供一个可点击的 URL。点击它，或在浏览器中访问该 URL，我们应该能看到 `Hello world! Random Fruit API` 的响应。访问 `/fruit` 路径则会返回随机的 JSON 格式水果数据。

## 总结 🎉

![](img/8822931ca1ee39dbd086b1e8b217bcd7_49.png)

本节课中我们一起学习了在 Google Cloud 平台上运行 Rust 微服务的完整流程。

![](img/8822931ca1ee39dbd086b1e8b217bcd7_51.png)

我们首先在 Cloud Shell 中配置了 Rust 开发环境，然后使用 Actix-web 框架创建了一个简单的 Web API。接着，我们通过编写 `Dockerfile` 将应用容器化，并利用 Cloud Shell 的 Cloud Code 扩展完成了本地模拟测试。最后，我们成功地将容器化应用一键部署到了 Google Cloud Run，使其成为了一个可弹性伸缩、免运维的云服务。

![](img/8822931ca1ee39dbd086b1e8b217bcd7_53.png)

整个过程表明，尽管 Cloud Run 的控制台向导没有直接提供 Rust 模板，但通过标准的容器化流程，我们可以轻松地将任何语言（包括 Rust）编写的应用部署上去，享受 Serverless 带来的便利。