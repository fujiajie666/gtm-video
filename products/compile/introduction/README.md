# OpenViking Compile 产品介绍

[观看介绍视频（MP4，55 秒）](./video.mp4)

Compile 可以把分散的项目资料整理成 Wiki、知识图谱或报告。以 Wiki 为例，它按 Skill 定义的规则读取文档、会议记录和反馈，把同一主题的信息汇集到一页，并保留来源引用，方便读者核对原文。[Compile 介绍文档](https://docs.openviking.ai/zh/context-compilation/01-overview)

## 基本用法

下面以灯塔项目为例。先启用 Compile Runtime，导入示例资料并安装 LLM Wiki Skill。准备步骤见[上下文编译入门](https://docs.openviking.ai/zh/getting-started/13-compile)。

指定来源目录、用于存放 Wiki 的新目录和整理资料的 Skill，然后提交任务。

```bash
ov compile --from viking://resources/onboarding-zh-v1 \
  --to viking://resources/onboarding-wiki-v1 \
  --skill viking://agent/skills/llm-wiki \
  --instruction "请用中文生成 index.md 和灯塔项目页面，并在正文中引用原始资料的 viking:// URI。"
```

用返回的任务 ID 查询进度，例如 `ov task status cmp_...`。状态变为 `completed` 后，打开 Wiki 首页即可按主题浏览。

```bash
ov read viking://resources/onboarding-wiki-v1/index.md
```
