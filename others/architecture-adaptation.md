# 架构适配 - lambda-refarch-streamprocessing

## 架构模式

**事件驱动流处理** - Kinesis Stream → Lambda → DynamoDB

## 适配方案

### 1. Kinesis Stream → DIS
- 华为云 DIS (数据接入服务) 提供与 AWS Kinesis 等效的流数据接入能力
- 映射: `AWS::Kinesis::Stream` → `huaweicloud_dis_stream`
- 参数基本一致：分片数 (shard_count)

### 2. Lambda → FunctionGraph
- 函数计算 (FunctionGraph) 提供与 AWS Lambda 等效的无服务器计算能力
- 映射: `AWS::Serverless::Function` → `huaweicloud_fgs_function`
- 需适配：
  - Runtime: Node.js 6.10 → Node.js 18.15
  - Handler 签名兼容
  - 事件结构 (Kinesis 事件格式相同)

### 3. DynamoDB → GeminiDB
- GeminiDB 提供 DynamoDB 兼容模式
- 映射: `AWS::DynamoDB::Table` → `huaweicloud_geminidb_instance` (dynamodb 存储引擎)
- 使用 DynamoDB 兼容 API 访问

### 4. IAM → IAM 委托
- IAM 委托机制与 AWS IAM Role 等效
- 映射: `AWS::IAM::Role` → `huaweicloud_iam_agency`

### 5. S3 → OBS
- OBS (对象存储服务) 提供与 S3 等效的对象存储能力
- Lambda 代码可上传到 OBS 或直接 inline

## 降级决策

无需降级 - 所有服务均有直接对标。
