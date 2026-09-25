# 多核调度：第一版问题一、二、三

第一版三问的求解程序、实验脚本与图表归档。

**[下载压缩包及校验文件（Release v1.0.0）](https://github.com/BGMYE/multicore-scheduling-v1-experiments-20260926/releases/tag/v1.0.0)**

## 交付内容

- 117 个 Python 源文件：三问求解器、批处理、消融、敏感性分析、审计及绘图脚本。
- 15 个图表文件，包含 PNG、PDF 和 SVG。
- 官方输入数据与配置、问题二/三单核基准、问题三固定种子。
- 实验汇总、完成报告，以及 57 个更优候选方案及其官方结果。
- 包内 README_使用说明.md、图片索引.md 与逐文件 SHA-256 清单 MANIFEST.json。

## 实验范围与验证

| 问题 | 补充配置 | 发现耗时更低方案的图×核数组 |
|---|---:|---:|
| 问题一 | 452 | 19 |
| 问题二 | 344 | 29 |
| 问题三 | 156 | 9 |

共952组配置、10,338条候选记录审计无错误；86次绕缓存官方复评一致；19项行为测试通过。80份原求解及官方源文件保持原样。

问题一消融采用独立核数核心求解器对照：28组直接匹配原主结果，4组通过低核保留证据衔接。57个更优候选是本次实验中的探索结果，不构成全局最优保证。

## 文件与使用

压缩包：multicore-scheduling-v1-experiments-20260926.zip（215.97 MiB，226,459,844 bytes）。

解压后先阅读根目录 README_使用说明.md，保持 output 下四个目录的相对位置。原环境为 Python 3.12.3；求解仅依赖标准库，绘图另需 Matplotlib，测试另需 pytest/pytest-cov。

本包包含程序、脚本、图表和支持数据；未收入大体积评价缓存、完整逐候选轨迹及全部原始运行目录。历史报告和元数据保留原工作区路径与执行哈希，具体复算条件见包内说明。

GitHub下载附件使用英文文件名，ZIP内容和原中文文件完全一致。

## 完整性校验

归档SHA-256：

    f85e120d9769ed713a750f62fc52efa4f8f5abcb3e6761653682301edb942acf

Windows PowerShell：

    Get-FileHash -Algorithm SHA256 -LiteralPath 'multicore-scheduling-v1-experiments-20260926.zip'

Release同时提供.sha256及.verification.json文件。打包后已逐文件校验解压读取的CRC、字节数、SHA-256，并通过全部归档Python文件的语法检查。
