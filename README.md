# long-sentence-parser-skill

面向专四备考、外刊精读的英文长难句解析 Skill。用户粘贴英文长难句，自动划分主句主干与修饰成分，给出通顺中文翻译，标注关键语法考点，梳理句子逻辑。

## 项目解决什么问题

专四备考学习者在刷英语阅读真题、进行外刊精读时，经常遇到多层从句嵌套的英文长难句。句子中大部分单词都认识，但难以快速识别主句主干，区分定语、状语、宾语从句、定语从句等各类修饰成分，容易出现理解偏差；手动拆解句子耗时较长，降低精读刷题效率。本 Skill 将"拆句—翻译—标语法—理逻辑"固化为固定流程，一次粘贴即可完成结构化解析。

## 主要功能

接收用户粘贴的英文长难句（适配专四阅读真题、外刊精读场景），固定按四个模块输出，顺序不调换：

- **🔍 句子成分拆分**：优先提取主句主干；从句、非谓语、定语、状语等修饰成分单独标出，并写明各自修饰的对象；
- **📖 中文翻译**：贴合原文逻辑，通顺自然，避免机器直译腔；
- **📌 关键语法标注**：选取本句核心语法考点，简要说明用法；
- **💡 逻辑梳理**：讲清分句之间的信息关系（让步、因果、补充说明等），帮助读懂作者表达思路。

**限制说明**：暂不支持网页抓取、PDF 解析、图形界面；只处理用户直接粘贴的英文长难句文本。

## 安装方法

本项目为本地 Skill，无需安装额外依赖。将本目录（含 `SKILL.md`）作为一个 Skill 文件夹，放入当前环境的 Skill 根目录（如 `workspace/.user_skills` 下）即可被加载使用。部署后如需校验 `SKILL.md` 配置是否合规，可使用 skill-creator-for-work 自带的 `quick_validate.py` 脚本对技能目录进行校验。

## 使用方法

1. 将需要分析的英文长难句直接粘贴发送；
2. 工具依次输出：句子成分拆分 → 中文翻译 → 关键语法标注 → 逻辑梳理；
3. 可继续粘贴新的长难句，逐句独立解析，持续开展精读练习。

## 输入输出示例

**用户输入**

While many people believe that online learning is convenient, others argue that it lacks face-to-face communication which is vital for deep understanding.

**AI 输出**

- 🔍 句子成分拆分
  - 主干：others argue that ...
  - 让步状语从句：While many people believe that online learning is convenient
  - 宾语从句 1：that online learning is convenient（作 believe 的宾语）
  - 宾语从句 2：that it lacks face-to-face communication（作 argue 的宾语）
  - 定语从句：which is vital for deep understanding（修饰 face-to-face communication）

- 📖 中文翻译：尽管很多人认为线上学习十分便捷，但另一些人认为线上学习缺少面对面交流，而这种交流对于深度理解至关重要。

- 📌 关键语法标注
  - while 此处引导让步状语从句，含义为"尽管"；
  - that 引导宾语从句；
  - which 引导限制性定语从句，修饰前面的 communication。

- 💡 逻辑梳理：先用让步从句引出正方观点，再抛出反方论点，最后用定语从句补充理由。
