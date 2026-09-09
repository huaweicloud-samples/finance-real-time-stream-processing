# 服务映射 - lambda-refarch-streamprocessing

## AWS → 华为云 服务映射

| AWS 服务 | 华为云服务 | 对齐度 | 迁移说明 |
|----------|-----------|--------|----------|
| Kinesis Stream | DIS (数据接入服务) | 🟢 完全对齐 | 1:1 映射，流概念一致 |
| Lambda | FunctionGraph | 🟢 完全对齐 | 事件触发机制相同 |
| DynamoDB | GeminiDB (DynamoDB 兼容) | 🟢 完全对齐 | 使用 DynamoDB 兼容模式 |
| IAM Role | IAM 委托 | 🟢 完全对齐 | 委托机制等价 |
| IAM User + AccessKey | IAM 委托 + AK/SK | 🟢 完全对齐 | 凭据管理方式相同 |
| S3 (Lambda 代码) | OBS | 🟢 完全对齐 | 对象存储兼容 |

## 对齐度汇总

- 🟢 完全对齐: 6/6 (100%)
- 🟡 部分对齐: 0
- 🔴 无对标: 0

## 风险评估

**无红色风险项** - 所有服务均有直接对标，可正常迁移。
