# Rust开发笔记

Rust安全、性能高、无所畏惧的并行开发


## 1. Rust在ubuntu下的安装
如果使用rustup安装rust，在终端输入以下命令
```bash
curl https://sh.rustup.rs -sSf | sh
```
之后在一个脚本页面中选择安装类型1，如果对于rustup程序熟悉的同学可以安装2，并回车。

> 这个地方安装会比较慢一些，如果等不及可以换一个镜像源。（以下操作可选）

首先先修改一下上边的命令，将安装脚本导出：
```bash
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs > rust.sh
```
之后打开rust.sh脚本，找到root
```bash
  8 
  9 # If RUSTUP_UPDATE_ROOT is unset or empty, default it.
 10 RUSTUP_UPDATE_ROOT="${RUSTUP_UPDATE_ROOT:-https://static.rust-lang.org/rustup}"
```

将其修改为
```bash
RUSTUP_UPDATE_ROOT="https://mirrors.ustc.edu.cn/rust-static/rustup"
```
这样就能加快下载速度。再修改一下环境变量
```bash
export RUSTUP_DIST_SERVER=https://mirrors.tuna.tsinghua.edu.cn/rustup
```
让rustup-init从国内进行下载rust组件，提高速度。

最后执行bash.sh
```bash
bash rust.sh
```

## 2. 管理Rust
那在安装完rust之后该如何管理rust呢？

可以使用`rustup update`来进行管理，自动更新到最新版本。

如果不再使用的话，可以使用`rustup self unistall`。自动删除rust语言机器所有相关的数据和工具链。


## 3. 查看是否安装成功
使用`rust -V` 或者是`rust --version`来进行对应版本的查看。


## 4. 敏捷学习rust
首先是用最基本的代码，查看一下rust环境是否编译成功。

定义一个以`rs`结尾的文件，文件名的命名方式为小写字母与下划线结合
```rust
fn main() {
  println!("Hello World!");
}
```

这是一个最简单的`main`函数，通过`rustc`来进行编译，最终使用`./hello_world.rs`来运行代码即可看到输出结果。

但是rustc只适合一些小型程序，cargo是针对rust的一个包管理工具，比较成熟

可以通过`cargo new hello_cargo`来创建一个hello_cargo的项目



cargo build

cargo run

cargo check

cargo build --release

尽量来使用cargo开发

## 5. rust的变量
