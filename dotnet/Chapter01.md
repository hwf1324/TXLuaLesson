# 命令行工具

必要前驱：

- [引言](Chapter00.md)

## 统一的工具链

对于一些比较传统的语言，例如C语言。学习它的工具链有时候甚至比学习这门语言本身更复杂。每一个C程序，从源码到可执行文件，需要经过预处理，编译（从C语言到汇编语言），汇编（从汇编语言到），链接四个阶段。每一个阶段都有至少一个专门工具与之对应。而当项目涉及多个源码文件的时候，事情就更加复杂。需要专门的构建工具来描述构建过程中各个源码文件的关系。而随着软件规模的进一步扩张，写构建工具所需读取的脚本也成了一个很复杂的事情。所以就又出现了生成构建脚本的工具。这还不算调试所需的调试工具，测试阶段需要的单元测试工具，管理依赖库的包管理工具等。

而dotnet的工具非常简单易用。安装dotnet sdk之后，就会有一个`dotnet`命令行命令。基本上开发中所涉及的所有工具都能通过这个命令调用。

> dotnet所提供的是编译工具链，调试工具，测试工具，包管理工具等后台工具。并不涉及源码编辑工具。推荐使用同样微软推出的Visual Studio Code。通过一些插件和配置，你甚至能在Visual Studio Code中通过调用dotnet完成构建运行和调试。

## 相关资源

如果你对于使用这个命令行工具有任何疑问，可以去查查dotnet command的官方手册。手册地址是<https://docs.microsoft.com/en-us/dotnet/core/tools>。

## 基本操作

要开始一个项目，第一步当然是创建项目。项目并不等价于几个源码文件，一般来说一个项目中除了项目源码，还包括对项目的说明。这些说明中包括项目中源码文件之间的关系，以及项目对非标准库包的依赖等。

一个项目被保存在一个文件夹中。所以创建一个项目分为两步——第一，创建一个空文件夹；第二，进入这个文件夹通过dotnet进行项目初始化。例如：

```shell
mkdir TXProject
cd TXProject
dotnet new console -lang C#
```

其中`dotnet new`用于进行项目初始化。`console`是控制台项目模板的意思。常用的通用项目模板除了`console`还有`classlib`，表示类库。不过接下来很长一段时间我们都用控制台来演示。`-lang C#`是用于指定语言的选项，如果需要F#项目，就使用`-lang F#`。当没有`-lang`选项的时候，默认语言为C#。

> 如果你要删除一个项目，只需要把这个项目的文件夹删除。如果你需要备份项目，最简单的办法就是压缩复制这个文件夹。

> dotnet仅仅初始化了与dotnet相关的文件。如果你使用VS Code编辑源码，那么在项目文件夹内启动VS Code时会提示你生成VS Code相关的配置（保存在项目文件夹下的`.vscode`文件夹中）。为了进行代码版本管理，你还可以再在这个文件夹中初始化git。

如果要构建项目，使用`dotnet build`命令。当然也可以使用`dotnet run`编译并运行。编译的目标文件存在于项目文件夹中的`bin`文件夹下。这两个命令都有一些参数，用于控制编译版本（Debug或Release），编译基于的框架版本等。详见dotnet命令行工具的文档。

在上传源码时，编译测试之后的可执行文件以及中间文件是没有必要上传的。此时可以使用`dotnet clean`清除项目构建的结果和中间文件。

当开发工作告一段落，需要发布软件的时候，使用`dotnet publish`命令生成发布文件。生成的发布文件在项目文件夹下的`bin/Debug/publish`或`bin/Release/publish`文件夹中（没错发布版也分Debug和Release）。

dotnet生成的发布文件的入口是一个后缀为`dll`的文件。这种文件不能直接在操作系统中执行，而需要在dotnet运行环境中执行。例如要执行一个`TXProject.dll`文件，使用命令：

```shell
dotnet TXProject.dll
```
