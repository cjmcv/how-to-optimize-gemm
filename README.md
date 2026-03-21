# Reading notes on open source code of AI infrastructure (LLM, Inference, HPC)

AI Infra 相关开源代码的阅读笔记，笔记主要以代码注释的方式呈现 (用 `<NT>` 标记)，极个别内容会添加文档笔记以辅助源码阅读。

## 笔记列表-源码注解

| 项目名 | 笔记范围 | 笔记量 | 重要系数 | 最后更新日期 |
| :---: | :--- | :--- | :---: | :---: |
| cutlass | 整体精读 | 171 | :star::star::star: | 20251102 |
| tilelang | 整体精读 | 30 | :star::star::star: | 20260321 |
| sglang | 整体精读 | 285 | :star::star: | 20251020 | 
| flash-attention | /hopper/ | 96 | :star: | 20250620 |
| SageAttention | 部分阅读 | 43 | :star: | 20250627 |
| marlin | 整体阅读 | 89 | :star: | 20241010 |
| lighteval | metrics评价指标部分 | 4 |:star: | 20250210 |

## 文档/图片笔记-docs

| 项目名 | 主题 | 最后更新日期 |
| :---: | :--- | :---: | 
| sglang | [kvcache代码梳理](https://github.com/cjmcv/ai-infra-notes/tree/master/docs/sglang/kvcache) | 20250326 |
| sglang | [基本结构](https://github.com/cjmcv/ai-infra-notes/tree/master/docs/sglang/sglang-architecture-20250117.jpg) | 20250117 |
| flash-attention | [基本代码结构](https://github.com/cjmcv/ai-infra-notes/tree/master/docs/flash-attention/flash-attention-code-structure-20250620.png) | 20250620 |
| flash-attention | [基础模块关系](https://github.com/cjmcv/ai-infra-notes/tree/master/docs/flash-attention/flash-attention-module-relationship-20250620.png) | 20250620 |
| lighteval | [评价指标梳理](https://github.com/cjmcv/ai-infra-notes/tree/master/docs/lighteval/lighteval-metrics-20250218.jpg) | 20250218 |

## 浏览笔记方式

```bash
git clone https://github.com/cjmcv/ai-infra-notes.git
cd ai-infra-notes
# 拉取你感兴趣的模块阅读，以sglang为例
git submodule init sglang
git submodule update sglang
```

笔记部分会用 `<NT>` 标记，可以搜索查看

* 注意：如发现中文显示乱码，可尝试按GB2312或UTF8格式查看。以vscode为例，点击右下角的编码格式，选Reopen with Encoding，切换到GB2312或UTF8查看。

## 仓库管理方式

1. 将想深入阅读代码的仓库fork下来，保留主分支用于同步代码.

2. 基于当前主分支最新代码，新增note-date1分支, date1对应开分支前的最后一次提交日期。

3. 网页端在settings中，将note-date1分支设为Default branch。

4. 开始阅读note-date1分支代码，在代码阅读过程中将自己的理解以注释方式添加到代码里。

5. 经一段时间阅读后，主分支已落后于原仓库，则通过网页端Sync fork直接将主分支更新到最新，基于更新后的主分支再新增一个note-date2。

6. 因note-date2是基于主分支从原仓库上同步过来的，上一阶段的阅读笔记还留在note-date1中，则需要使用对比软件，手动将note-date1中的中文注解挪到note-date2中，同时将新的阅读分支设为Default branch，进行下一阶段的阅读，以5和6步反复推进。

7. 将代码阅读的fork仓库以submodule的方式接入到本仓库中统一管理。

```bash
git submodule add https://github.com/cjmcv/sglang.git sglang
```