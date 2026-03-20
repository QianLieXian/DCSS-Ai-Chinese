# DCSS 0.34.1 汉化说明

本仓库用于 **Dungeon Crawl Stone Soup 0.34.1** 的中文文本覆盖。

## 使用方法

将以下目录中的全部文件复制到游戏对应目录（覆盖原文件）：

- `Real New Chinese descript` → `dat/descript/zh`
- `Real New Chinese database` → `dat/database/zh`

> 本仓库已移除旧的 `New Chinese *` 目录，请使用 `Real New Chinese *` 目录中的最新文本。
> 建议先备份原始 `zh` 目录，便于回滚。

## 你截图里那几类英文文本在哪里？

你发的三张图里，出现英文的内容主要分两类：

1. **角色回归提示、未知命令、帮助主菜单标题**
   - 例如：`Welcome back, ...`、`Press ? for a list of commands...`、`Unknown command.`、`Dungeon Crawl Help`、`Manual Contents`
   - 这类文本大多是 **游戏源码中的界面字符串**（C++ / Lua UI 逻辑），不在 `dat/descript/zh` 或 `dat/database/zh` 的文本库里。

2. **武器数值面板里的说明句**
   - 例如：`Base accuracy`、`Base attack delay`、`Damage rating`、`This weapon falls into ...`
   - 这些通常也是 **源码拼接出来的动态文本**（根据武器类型、技能、延迟实时计算），不属于纯文本词条覆盖范围。

## 为什么会出现“还有英文没汉化”？

本仓库当前是 **文本数据库覆盖方案**，只替换 `dat/descript/zh` 和 `dat/database/zh` 中可覆盖的词条。  
因此：

- 词条库里的描述、帮助条目、怪物/道具说明可以汉化；
- 但源码里硬编码或动态生成的 UI 文本，单靠本仓库无法完全覆盖。

## 如果要把这部分也汉化，需要做什么？

需要在 DCSS 源码层处理（通常是官方源码树中的 `crawl-ref/source/`）：

- 找到对应 UI/描述生成代码；
- 增加/接入可本地化字符串；
- 重新编译游戏。

换句话说，本仓库不是“全量源码汉化补丁”，而是“可覆盖文本库汉化包”。

## 兼容性说明

- 本仓库只修改文本与说明，不涉及游戏逻辑代码。
- 为避免兼容问题，请确保游戏版本为 **0.34.1**。
- 若使用其他版本，部分词条可能缺失或显示异常。

## 致谢

感谢蜥蜴大佬与 Zijingng 大佬提供的前期模板与工作基础。
