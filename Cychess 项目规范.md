Version: 0.0
Date: 2026-1-20
## 目录规范

Cychess 中文件夹如下：

```txt
Assets       
|------ Scripts 脚本文件夹
		|------ Utils   所有的工具类和工具方法
		|------ Logic   游戏逻辑
		        |------ GameManager.cs  整个游戏的流程管理
		        |------ SceneStart      开始场景逻辑
		        |------ ...             其他场景逻辑
		|------ Component   一般性的部件脚本
		|------ Chess       Chess逻辑与AI适配
|------ Shaders 着色器文件夹
|------ ArtAssets   美术资源文件夹
		|------ Common  公用资源
		|------ SceneStart  开始场景资源
		|------ ...         其他场景资源
```

## 代码规范

### 提交规范

禁止直接投 main 分支。禁止强制推送。所有撤回一律发 revert 提交。

Revert 和 Merge 提交尽量使用系统自动生成的 commit 内容。

每个 commit 尽可能小，单个 commit 不能引入已知 bug.

commit 格式：

```txt
feat: 添加功能
refactor: 重构
doc: 添加文档/注释
fix: 修bug
art: 添加美术资源
asset: 其他资源
scene: 所有场景内部的更改

例：
feat: 添加了王车易位
fix: 修复了游戏将军判断导致stack overflow的问题
scene: 在开始游戏场景中配置了UI
```

### 分支规范

每一个独立的功能拉一个独立的分支，比如 v0.0 的开发分支如下：

```txt
main 主分支
chess 下棋功能
chess/art 巫师棋建模
chess/feat Chess 组件开发
chess/feat/logic Chess 逻辑
chess/feat/ai    Chess AI适配
chess/scene 巫师棋场景
```

合并的时候遵循逐级合并的规则，即：

```txt
merge chess/feat/logic to chess/feat
merge chess/feat/ai    to chess/feat
merge chess/feat       to chess
merge chess/art        to chess
merge chess/scene      to chess
merge chess            to main
```
### 命名规范

一律遵照 C# 语言建议进行。

典型的规则有：

1. 所有命名均采用驼峰命名法
2. 类名，方法名，类的公有成员均用首字母大写的驼峰命名法
3. 局部变量，函数参数均用首字母小写的驼峰命名法
4. 私有成员均用一个下划线开头，首字母小写的驼峰命名法

额外的规则：

1. 游戏对象命名也一律使用驼峰命名法
2. GameObject 可以当文件夹用，总之不能把大量的 GameObject 直接全塞到场景下面。
3. 脚本属性必须有 Header
4. 禁止滥用 Tag

### 语言规范

## 资源规范

### 目录规范

所有同类资源放在一个文件夹下。特别地，同一资源的不同变体需要放在同一文件夹下。
### 命名规范

全部使用驼峰命名法，但数字和字母之间用下划线隔开。所有目录和所有资源大项首字母大写，同一资源的变体首字母小写。

例如：

```txt
SceneStart.unity
Scene_1.unity
Knight
|------ Black
|------ White
```