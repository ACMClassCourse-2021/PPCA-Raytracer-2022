![banner](https://user-images.githubusercontent.com/4198311/89027545-461dd180-d35d-11ea-9972-7bf1b07f942d.png)

# PPCA Raytracer 2022

![GitHub top language](https://img.shields.io/github/languages/top/ACMClassCourse-2021/PPCA-Raytracer-2022)
![License](https://img.shields.io/github/license/ACMClassCourse-2021/PPCA-Raytracer-2022)
![GitHub repo size](https://img.shields.io/github/repo-size/ACMClassCourse-2021/PPCA-Raytracer-2022)
![GitHub Workflow Status](https://img.shields.io/github/workflow/status/ACMClassCourse-2021/PPCA-Raytracer-2022/CI)

## 课程介绍

- 本项目为 2021-2022 学年暑期小学期课程
- ACM 班时间为学期第 3 - 6 周（7.4 - 7.29），工科为第 3 - 4 周
- 项目助教：[PaperL](https://github.com/PaperL/)、[yichuan](https://github.com/yichuan520030910320)、[Alr_ksim](https://github.com/Alr-ksim)

具体安排暂定如下（Day 1 = July 4th, 2022）：

### 工科

- **日程**

  - **Day 1**：介绍项目与前期准备（Task 0）
  - **Day 2 - 3**：熟悉 Rust 语法（Task 1）
  - **Day 4 - 7**：学习完成教程 book 1 & 2（Task 2）
  - **Day 8 - 9**：自行设计创作结课作品
  - **Day 10**：结课分享 & code review

- **分数**

  - | 任务                       | 分数占比（总计 100%）                 |
    | -------------------------- | ------------------------------------- |
    | **Task 0**                 | 10%                                   |
    | **Task 1**                 | 30%                                   |
    | **Task 2**                 | 40%                                   |
    | **结课作品 & code review** | 20%                                   |
    | 结课分享                   | 10% *（作为 Bonus，总分不溢出 100%）* |

### ACM 班

- **日程**

  - **Day 1**：介绍项目与前期准备（Task 0）
  - **Day 2**：熟悉 Rust 语法（Task 1）
  - **Day 3 - 5**：学习完成教程 book 1 & 2（Task 2）
  - **Day 6 - 7**：完成 book 3 优化内容（Task 3）
  - **Day 8**：进阶内容介绍
  - **Day 9 - 18**：完成自主学习（Task 4）
  - **Day 19 - 20**：结课展示 & code review

- **分数**

  - | 任务       | 分数占比（总计 100%）                 |
    | ---------- | ------------------------------------- |
    | **Task 0** | 5%                                    |
    | **Task 1** | 15%                                   |
    | **Task 2** | 20%                                   |
    | **Task 3** | 10%                                   |
    | **Task 4** | 50%                                   |
    | 结课展示   | 10% *（作为 Bonus，总分不溢出 100%）* |

---

## 导言

> Powered by Pseudo Photograph Company of ACM
>
> ACM 伪摄影公司，简称 PPCA，于 2021 年成立😉

　　本项目主要内容为学习 Rust 语言并实现一个光线追踪渲染器（基于路径追踪算法）。以这个形式，你能通过学习一门新的（而且漂亮的）语言—— Rust 来加深对编程语言设计、编译原理的理解，同时又能趣味性地了解 Computer Graphics 的基础工作。项目设有作品互评环节。使用自己手写的渲染器，发挥艺术才能，创造出惊艳全场的超现实大作吧！

　　下文中 `something` 表示命令行指令或文件，💠 标记表示该条目为进阶内容。

　　你可以直接点击网页右上角的 “Use this template” 绿色按钮将这个项目复制到自己的 GitHub Profile 中。接下来，你需要做一些准备工作。

---

## Task 0: Preparation

- [ ] 在 `raytracer/Cargo.toml` 中，修改作者信息
- [ ] 在 `LICENSE` 中，将作者修改为自己。你也可以换成其他许可证
- [ ] 配置 Rust 环境
  - 使用 [rustup](https://doc.rust-lang.org/book/ch01-01-installation.html) 安装 Rust。如果下载速度很慢，可以考虑使用 [SJTUG Mirror](https://mirrors.sjtug.sjtu.edu.cn) 的 rust-static 和 crates.io 镜像
  - 之后，你需要安装一些工具。首先，你需要定位到项目目录。而后，运行 `rustup component add clippy rustfmt`
  - 接着，运行 `make ci`。如果程序可以正常运行，那么环境就已经配置成功了
- [ ] 配置 GitHub Action
  - 如果你的 Repo 直接使用题面模板
    - 那么在上述操作完成后，将库 push 到 GitHub 上。在 GitHub Action 中，“Lint and Test” 和 “Build and Upload” 都应当通过（该功能位于 Github Repo 网页上方项目名称旁的 Actions 选项卡）
    - 程序生成的结果会出现在 GitHub Action 的 Artifacts 中。`output` 文件夹下的内容应当是程序运行时生成的。对 output 文件夹的修改不应该被同步到 GitHub 上（参考 `.gitignore`）
  - 💠你也可以自己学习设计工作流程（可以参考题面 Repo `.github/workflows/cargo.yml`）
- [ ] 最后，你可以把 `README.md` 中的教程部分删除，换成自己项目的描述、运行方法等信息
- [ ] code review
  - 运行题面 Demo 代码或 Hello World
  - GitHub Action 成功完成工作流程
  - 每位学生提交 GitHub Repo 链接

## Task 1: Learn about Rust

我们希望用几天的时间让大家熟悉 Rust 的语法。请阅读 [***The Rust Programming Language***](https://doc.rust-lang.org/book/title-page.html)（或者你认为合适的教程）学习，以下为 Tips：

- 通常来说，你只需要用到前 6 章和第 10.2 节的内容
- 如果碰到了 lifetime 相关的问题，请仔细阅读第 4 章，特别是 4.2 的例子。当然，你也可以通过第 15 章中的智能指针解决一部分 lifetime 导致的问题
- Rust 的面向对象特性（trait，对应 C++ 的类）可以在 10.2 中找到
- 💠涉及到多线程渲染时，你可以阅读第 15、16 章的内容

为了快速上手语法，请使用 Rust 语言完成以下[力扣（LeetCode）网站](https://leetcode.cn/)练习：

- [ ] [88. 合并两个有序数组](https://leetcode.cn/problems/merge-sorted-array/)
- [ ] [2181. 合并零之间的节点](https://leetcode.cn/problems/merge-nodes-in-between-zeros/)
- [ ] [94. 二叉树的中序遍历](https://leetcode.cn/problems/binary-tree-inorder-traversal/)
- [ ] code review
  - Rust 基础语法特性掌握（范围不超出前 6 章与第 10.2 节）

## Task 2: Shoot the Light

了解完 Rust 语法，就可以开始学习和动手实现 ray tracer 了！[***Ray Tracing in One Weekend - The Book Series***](https://raytracing.github.io) 是一套十分经典的教程，从原理和实践角度详细地阐释了 ray tracing 的基础知识，本项目便是基于该教程展开：

- [ ] 学习 Ray Tracing book 1，使用 Rust 语言实现该部分程序，并渲染成果图
- [ ] 完成 Ray Tracing book 2，要求同上
- [ ] 💠实现多线程渲染
- [ ] code review
  - book 1 & 2 最终成果图
  - book 1 & 2 相关实现细节

## Task 3: Faster than Light

通过 book 1 & 2 的学习，你已经实现了一个基于路径追踪算法的光线追踪渲染器，这个渲染器的逻辑十分简单而显然。接下来，你将接触到真正的光线追踪知识，学习一个十分基础而重要的算法——蒙特卡洛算法。在 book 3 中详细阐述了蒙特卡洛算法以及它在我们的渲染器中的应用。

- [ ] 完成 Ray Tracing book 3
- [ ] code review
  - book 3 最终成果图
  - 理解蒙特卡洛算法及相关概念
  - 💠尝试找出教程中的问题（错误），并在自己代码中加以解决或改进

## 💠Task 4: Out of Light

通过 *Ray Tracing in One Weekend* 教程的学习，你已经基本掌握了路径追踪算法。正如 book 3 书名 *The Rest of Your Life*，光线追踪和 CG 是一片无垠的知识领域，投入一生的时间或许也无法学尽。本项目剩余的时间便交由你来自由探索，有几个大致方向可供参考：

- [ ] 更抽象的程序特性（部分补充说明详见 [Releases](https://github.com/ACMClassCourse-2021/PPCA-Raytracer-2022/releases)）

  - 多线程
  - 静态 BVHNode
- [ ] 更炫酷的视觉效果
  - 镜头光晕
  - 镜头景深、移轴
- [ ] 更高效的渲染算法
  - 光子贴图
  - Unity / Blender Shader
- [ ] 更真实的 CG 模型

  - 物理光谱
  - 光的波动性
- [ ] 其他更 exciting 的 idea！

最终成果形式不限，可以是一张图、一份实验报告或一场展示。请与助教交流你想学习的知识，我们会尽可能地给予支持。

---

## More Information

### Makefile

[`Makefile`](https://github.com/ACMClassCourse-2021/PPCA-Raytracer-2022/blob/main/Makefile) 中包含了运行 raytracer 的常用指令。如果没有安装 `make`，你也可以直接运行 `cargo balahbalah`。

* `make fmt` 会自动格式化所有的 Rust 代码
* `make clippy` 会对代码风格做进一步约束
* `make test` 会运行程序中的单元测试。你编写的 `Vec3` 需要通过所有测试
* `make run_release` 会运行优化后的程序。通常来说，你需要用这个选项运行 raytracer。否则，渲染会非常慢
* `make run` 以 debug 模式运行程序
* `make ci` = `fmt + clippy + test + run_release`。建议在把代码 push 到远程仓库之前运行一下 `make ci`

### GitHub Action

这个仓库已经配置好了 GitHub Action。只要把代码 push 到远程仓库，GitHub 就会进行下面两个检查。

* **Lint and Test** 会运行所有单元测试，并检查代码风格
* **Build and Upload** 会运行优化后的程序，并将 output 目录下生成的文件传到 build artifacts 中

## Advanced Program Features

请参考 [Alex Chi 学长设计的内容](https://github.com/aik2mlj/raytracer-tutorial#advanced-features)

---

## Reference

* [The Rust Programming Language](https://doc.rust-lang.org/book/title-page.html)
* [rustlings](https://github.com/rust-lang/rustlings) 包含许多 Rust 小练习。如果你希望通过练习来学习 Rust 语言，可以尝试一下这个参考资料。
* [Ray Tracing in One Weekend — The Book Series](https://raytracing.github.io)
* （Advanced）过程宏相关
  * [Procedural Macros](https://doc.rust-lang.org/reference/procedural-macros.html) (关注 Function-like procedural macros 即可)
  * [quote crate](https://crates.io/crates/quote)
* （Advanced）JSON / yaml 读取
  * [serde-json](https://docs.serde.rs/serde_json/)，只需要关注其中的 untyped 部分。
  * [yaml-rust](https://docs.rs/yaml-rust/0.4.4/yaml_rust/)
  * 通常来说，你并不需要使用到下面这个序列化/反序列化的包。
  * [serde](https://serde.rs)

