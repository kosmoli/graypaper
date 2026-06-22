# JAM 灰皮书中文翻译

本目录包含 Gavin Wood 所著 JAM 规范（Graypaper）的中文翻译。

## 翻译约定

- **技术术语保留英文**：JAM、Polkadot、Ethereum、PVM、Safrole、GRANDPA、BEEFY、CoreJam、gas、blob、opcode 等
- **章节标题**：中文翻译后附英文原文，如 `\section{引言 (Introduction)}`
- **数学公式**：完整保留，不做任何修改
- **LaTeX 命令/宏/标签/引用**：完整保留
- **编译环境**：需要 XeLaTeX + xeCJK（原版使用 pdfLaTeX）

## 文件结构

与上游 `gavofyork/graypaper` 完全对应：

```
ChineseTranslate/
├── graypaper.tex          # 主文件（与上游相同）
├── preamble.tex           # 前言（增加了 xeCJK 中文支持）
├── context.tex            # 上下文定义
├── biblio.bib             # 参考文献
├── assets/                # 图片资源
├── text/                  # 章节翻译
│   ├── abstract.tex       # 摘要
│   ├── intro.tex          # 引言
│   ├── previous_work.tex  # 先前工作
│   ├── notation.tex       # 符号约定
│   ├── overview.tex       # 概述
│   ├── header.tex         # 区块头
│   ├── safrole.tex        # Safrole 共识
│   ├── recent_history.tex # 近期历史
│   ├── authorization.tex  # 授权
│   ├── accounts.tex       # 服务账户
│   ├── judgments.tex      # 争议与判决
│   ├── reporting_assurance.tex # 报告与保证
│   ├── accumulation.tex   # 累积
│   ├── statistics.tex     # 统计
│   ├── work_packages_and_reports.tex # 工作包与报告
│   ├── guaranteeing.tex   # 担保
│   ├── assurance.tex      # 可用性保证
│   ├── auditing.tex       # 审计
│   ├── beefy.tex          # BEEFY 分发
│   ├── best_chain.tex     # 最优链选择
│   ├── discussion.tex     # 讨论
│   ├── conclusion.tex     # 结论
│   ├── ack.tex            # 致谢
│   ├── pvm.tex            # PVM 虚拟机（附录）
│   ├── pvm_invocations.tex # PVM 调用（附录）
│   ├── serialization.tex  # 序列化（附录）
│   ├── merklization.tex   # Merklization（附录）
│   ├── utilities.tex      # 工具函数（附录）
│   ├── bandersnatch.tex   # Bandersnatch VRF（附录）
│   ├── erasure_coding.tex # 纠删码（附录）
│   └── definitions.tex    # 定义索引
└── README.md              # 本文件
```

## 同步上游更新

```bash
# 在 graypaper 根目录
git remote -v  # 确认 upstream 指向 gavofyork/graypaper
git fetch upstream
git merge upstream/main
# 然后检查 text/ 中哪些文件有变更，更新 ChineseTranslate/text/ 中的对应翻译
```

## 编译

```bash
# 需要安装 XeLaTeX 和 CJK 字体
# Ubuntu/Debian:
#   apt install texlive-xetex texlive-lang-chinese fonts-noto-cjk
# 然后：
cd ChineseTranslate
xelatex graypaper.tex
biber graypaper
xelatex graypaper.tex
xelatex graypaper.tex
```

---
*翻译于 2026-06-22，Kleo & Kosmo*
