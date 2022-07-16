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

- **工科小朋友的作品已经新鲜出炉啦 ~~~**
![work1](/sences/work1.jpg)
![work2](/sences/work2.jpg)
![work3](/sences/work3.jpg)
![work4](/sences/work4.jpg)
![work5](/sences/work5.png)

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

下面会是几个具体的track

### Advanced features

* **Track 1: Reduce Contention** 此项工作的前提条件是完成多线程渲染。在多线程环境中，clone / drop Arc 可能会导致性能下降。因此，我们要尽量减少 Arc 的使用。这项任务的目标是，仅在线程创建的时候 clone Arc；其他地方不出现 Arc，将 Arc 改为引用。

* **Track 2: Static Dispatch** 调用 `Box<dyn trait>` / `Arc<dyn trait>` / `&dyn trait` 中的函数时会产生额外的开销。我们可以通过泛型来解决这个问题。

  * 这个任务的目标是，通过定义新的泛型材质、变换和物体，比如 `LambertianStatic<T>`，并在场景中使用他们，从而减少动态调用的开销。你也可以另开一个模块定义和之前的材质同名的 struct。
  * 你可以在 `material.rs` 里找到泛型的相关用法。
  * 仅在 `HitRecord`, `ScatterRecord` (这个在 Rest of Your Life 的剩余部分中出现), `HittableList` 和 `BVHNode` 中使用 `dyn`。
  * 如果感兴趣，可以探索如何使用 `macro_rules` 来减少几乎相同的代码写两遍的冗余。

* **Track 3: Code Generation** 此项工作的前提条件是完成 BVH。

  * 目前，`BVHNode` 是在运行时构造的。这个过程其实可以在编译期完成。我们可以通过过程宏生成所有的物体，并构造静态的 `BVHNode`，从而提升渲染效率。
  * `raytracer_codegen`和`raytracer`大概是不能共用module的，你可能需要把一些实现（如`Vec3`）简单地copy到`raytracer_codegen`下。
  * 你可以使用 `cargo expand` 来查看过程宏处理过后的代码。你也可以在编译过程中直接输出过程宏生成的代码。
  * `codegen` 部分不需要通过 clippy。
  * 如果感兴趣，你也可以探索给过程宏传参的方法。e.g. 通过 `make_spheres_impl! { 100 }` 生成可以产生 100 个球的函数。

* **Track 4: PDF Static Dispatch** 此项工作的前提条件是完成 Rest of your Life 的剩余部分。PDF 中需要处理的物体使用泛型完成，去除代码路径中的 `&dyn`。

* **Track 5: More Code Generation** 在过程宏中，读取文件，直接从 yaml 或 JSON 文件（选择一种即可）生成场景对应的程序。

  * 在 `data` 文件夹中给出了一些例子。
  * 例子中 `BVHNode` 里的 `bounding_box` 是冗余数据。你可以不使用这个数据。
  * 读 JSON / yaml 可以调包。

* **Track 6: Advanced Features** 增加对 Transform 的 PDF 支持。

* **Track 7: Benchmark to test the efficiency of the code** 你可以通过 benchmark 来测试实现功能前后的区别。 

  * 完成 Track 3 前请备份代码 (比如记录 git 的 commit id)。完成 Track 4, 5, 6 时请保留原先的场景和程序，在此基础上添加新的内容。
  * 你可以使用 `criterion` crate 做 benchmark。benchmark 的内容可以是往构造好的场景中随机打光线，记录打一条光线所需的时间。或者可以设计你自己的实验，来说明你做的部分代码上的优化能提升光线追踪的性能.
  * 最后的展现形式可以是多样的：比如criterion集成好的html展示,或者是额外的一些图形包 比如:gnuplot。当然你还可以去尝试火焰图（之后可能在你们的操作系统课上会遇到）等工具来看具体调用函数的情况来更深入的了解性能提升的原因。
  * [参考资料1](https://bheisler.github.io/criterion.rs/book/ ) [参考资料2](https://bheisler.github.io/criterion.rs/book/getting_started.html)

* **Track 8: Support for obj** 支持载入obj文件并渲染。完成这一部分你可能需要：

  * 了解obj文件格式
  * 实现一个obj_loader
    * 可调包，如tobj
    * OBJ文件格式和tobj可参考[参考资料](https://docs.rs/tobj/3.0.1/tobj/)或自行搜索
  * 实现对简单多边形的渲染
  * 支持obj可以让你最后的大作更精彩哦 :)                 图源参考资料↓

  ![Rust logo with friends](http://i.imgur.com/E1ylrZW.png)

* 另外如果你在查找3D模型的时候发现有些让你心仪的模型是.stl格式的，你也可以尝试着让你的光线追踪模型去支持.stl文件来让你场景更加丰富，你可以手动实现.stl的导入（或许并不复杂，只要一个parser即可），也可以调用现有的库，如果你实现了obj和stl都能够支持的光追模型，我们当然会根据你的工作量给你更多的分数！
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

