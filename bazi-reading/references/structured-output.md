# 结构化输出

当需要让模型为网页或 API 返回内容时，要求只输出 JSON 对象，不输出 Markdown 或前言。

```json
{
  "overview": "不超过 3 句的总览",
  "sections": [
    {
      "type": "prose | features | timeline | cards | milestones | quote",
      "title": "主标题",
      "kicker": "可选副标题",
      "intro": "可选导语",
      "body": "可选正文",
      "items": [
        {
          "label": "可选标签",
          "title": "小标题",
          "body": "2-4 句，含判断、风险与建议",
          "meta": "仅时间线或年份使用",
          "bullets": ["可选要点"]
        }
      ]
    }
  ]
}
```

推荐类型：

- `features`：命局特征、十神白话、五行补偏。
- `timeline`：大运阶段；`meta` 写年龄或年份。
- `cards`：一生运势、流年分项。
- `milestones`：关键年份；`meta` 写年份。
- `quote`：最后简短总结，不要宿命化诗句。

限制每个模块 2-5 项、每项 2-4 句。展示端应验证 JSON、删去未知字段、截断超长文本；如果模型输出被截断或 JSON 格式不完整，要求它用更短内容重试一次。

