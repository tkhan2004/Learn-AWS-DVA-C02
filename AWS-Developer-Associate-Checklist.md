# 🎯 AWS Certified Developer Associate (DVA-C02) — Lộ trình học

> Exam code: DVA-C02 | Thời gian: 130 phút | 65 câu | Điểm đạt: 720/1000
> Domain weight: Development (32%) · Security (26%) · Deployment (24%) · Troubleshooting (18%)

---

## 📌 Giai đoạn 0 — Chuẩn bị nền tảng (trước khi vào khóa học)

- [ ] Tạo AWS Free Tier account
- [ ] Cài & config AWS CLI v2
- [ ] Cài AWS SDK cho ngôn ngữ quen dùng (Node.js/Python/Java)
- [ ] Hiểu tổng quan AWS Global Infrastructure: Region, Availability Zone, Edge Location
- [ ] Nắm khái niệm Shared Responsibility Model
- [ ] Ôn lại kiến thức nền: REST API, HTTP methods/status code, JSON, IAM cơ bản
- [ ] Cài AWS Toolkit / Console Mobile App (optional, để theo dõi nhanh)

---

## 🧩 Domain 1 — Development with AWS Services (32%)

### AWS Lambda
- [ ] Execution model: cold start vs warm start
- [ ] Execution role (permissions Lambda cần để gọi service khác)
- [ ] Resource-based policy (ai được gọi Lambda)
- [ ] Environment variables & encryption
- [ ] Lambda Layers (chia sẻ code/dependency)
- [ ] Concurrency: reserved concurrency vs provisioned concurrency
- [ ] Timeout, memory allocation, và tradeoff CPU/cost
- [ ] Event source mapping (SQS, DynamoDB Streams, Kinesis)
- [ ] Synchronous vs Asynchronous invocation
- [ ] Lambda versioning & aliases
- [ ] Dead-letter queue cho Lambda async
- [ ] Lambda@Edge (biết sơ lược)
- [ ] Container image support cho Lambda

### API Gateway
- [ ] REST API vs HTTP API vs WebSocket API — khi nào dùng loại nào
- [ ] Resource, Method, Integration request/response
- [ ] Authorizers: IAM, Lambda authorizer, Cognito authorizer
- [ ] Usage plans & API keys
- [ ] Throttling (account level vs stage level)
- [ ] Caching ở API Gateway
- [ ] CORS configuration
- [ ] Stage & deployment (dev/prod stage)
- [ ] Request validation & mapping templates

### DynamoDB
- [ ] Partition key vs Sort key (composite key)
- [ ] Primary key design & access pattern
- [ ] Global Secondary Index (GSI) vs Local Secondary Index (LSI)
- [ ] Read/Write Capacity Mode: On-Demand vs Provisioned
- [ ] Consistent read vs Eventually consistent read
- [ ] DynamoDB Streams (kết hợp với Lambda)
- [ ] DAX (DynamoDB Accelerator) — caching layer
- [ ] Conditional writes & optimistic locking
- [ ] Batch operations: BatchGetItem, BatchWriteItem
- [ ] TTL (Time To Live) cho item
- [ ] Transactions (TransactWriteItems/TransactGetItems)
- [ ] Query vs Scan (hiệu năng & cost)

### S3
- [x] Storage classes: Standard, IA, One Zone-IA, Glacier, Glacier Deep Archive, Intelligent-Tiering
- [x] Versioning
- [x] Lifecycle policy (transition & expiration rules)
- [x] Presigned URL (upload/download tạm thời)
- [x] Multipart upload (file lớn)
- [x] Event notifications (S3 → Lambda/SQS/SNS)
- [x] S3 Transfer Acceleration
- [x] Static website hosting
- [x] Cross-region replication (CRR)

### Messaging & Integration
- [ ] SQS: Standard queue vs FIFO queue
- [ ] Visibility timeout & long polling
- [ ] Dead-letter queue (DLQ) & redrive policy
- [ ] SNS: topic, subscription, fan-out pattern
- [ ] SNS vs SQS vs EventBridge — phân biệt use case
- [ ] EventBridge: event bus, rule, pattern matching, scheduled events
- [ ] Step Functions: state machine, Standard vs Express workflow
- [ ] Step Functions error handling (Retry/Catch)

### Caching & khác
- [ ] ElastiCache: Redis vs Memcached
- [ ] Caching strategies: lazy loading, write-through, TTL
- [ ] Kinesis Data Streams cơ bản (nếu có thời gian)

---

## 🔐 Domain 2 — Security (26%)

### IAM
- [x] IAM User, Group, Role — khi nào dùng cái nào
- [x] Identity-based policy vs Resource-based policy
- [x] Trust policy (ai được assume role)
- [x] Permission boundary
- [x] STS: AssumeRole, temporary credentials
- [x] Policy evaluation logic (explicit deny > allow)
- [x] Inline policy vs Managed policy

### Cognito
- [ ] User Pool (authentication) vs Identity Pool (authorization/federated access) — **rất dễ nhầm, học kỹ**
- [ ] Federated identity (Google, Facebook, SAML)
- [ ] Cognito với API Gateway authorizer
- [ ] JWT token flow (ID token, access token, refresh token)

### Encryption & Secrets
- [ ] KMS: Customer Master Key (CMK) vs Data key
- [ ] Envelope encryption
- [ ] Encryption context
- [ ] KMS key policy
- [ ] Secrets Manager vs Systems Manager Parameter Store — so sánh chi phí, rotation, use case
- [ ] Secret rotation tự động
- [ ] Encryption at rest vs in transit cho từng service (S3, DynamoDB, RDS)

### Khác
- [ ] Resource policies cho S3, Lambda, SQS
- [ ] VPC endpoint (Gateway vs Interface) liên quan security
- [ ] CloudHSM (biết sơ lược, ít câu hỏi)

---

## 🚀 Domain 3 — Deployment (24%)

### CI/CD Pipeline
- [ ] CodeCommit — Git repo trên AWS
- [ ] CodeBuild: buildspec.yml, build environment
- [ ] CodePipeline: stage, action, artifact
- [ ] CodeDeploy: deployment group, application revision

### Deployment Strategies
- [ ] In-place deployment
- [ ] Rolling deployment
- [ ] Blue/Green deployment
- [ ] Canary deployment
- [ ] Lambda traffic shifting: Linear, Canary, All-at-once (weighted alias)
- [ ] CodeDeploy AppSpec file (appspec.yml)
- [ ] Rollback strategy khi deployment fail

### Elastic Beanstalk
- [ ] Application vs Environment
- [ ] .ebextensions config files
- [ ] Deployment policy: All at once, Rolling, Rolling with additional batch, Immutable, Blue/Green
- [ ] Environment tier: Web server vs Worker

### Infrastructure as Code
- [ ] CloudFormation: template structure (Resources, Parameters, Outputs, Mappings)
- [ ] Intrinsic functions (Ref, GetAtt, Sub, Join)
- [ ] Stack update behavior: No interruption / With interruption / Replacement
- [ ] Change sets (preview thay đổi trước khi apply)
- [ ] Nested stacks
- [ ] Stack policies & Deletion policy
- [ ] SAM (Serverless Application Model): template, `sam build`, `sam deploy`, `sam local` để test local
- [ ] CDK — biết khái niệm cơ bản (constructs, stack)

---

## 🔍 Domain 4 — Troubleshooting & Optimization (18%)

### Monitoring
- [ ] CloudWatch Metrics: namespace, dimension, custom metrics
- [ ] CloudWatch Alarms
- [ ] CloudWatch Logs & Logs Insights (query syntax)
- [ ] CloudWatch Embedded Metric Format (EMF)
- [ ] CloudWatch Events (nay là 1 phần của EventBridge)

### Tracing & Debugging
- [ ] X-Ray: segment vs subsegment
- [ ] X-Ray service map
- [ ] Sampling rule
- [ ] X-Ray SDK integration với Lambda/API Gateway

### Logging & Audit
- [ ] CloudTrail vs CloudWatch — phân biệt rõ (audit API calls vs monitoring metrics/logs)
- [ ] CloudTrail event history & trail

### Performance Optimization
- [ ] Lambda cold start optimization (provisioned concurrency, package size)
- [ ] DynamoDB throttling — nguyên nhân & cách fix (hot partition)
- [ ] API Gateway timeout troubleshooting

---

## ⚠️ Các cặp dễ nhầm — học kỹ trước

- [ ] SQS vs SNS vs EventBridge
- [ ] Cognito User Pool vs Identity Pool
- [ ] Secrets Manager vs Parameter Store
- [ ] CloudTrail vs CloudWatch
- [ ] GSI vs LSI (DynamoDB)
- [ ] In-place vs Blue/Green vs Canary deployment
- [ ] Standard vs Express Step Functions
- [ ] REST API vs HTTP API (API Gateway)

---

## 🛠️ Hands-on Lab đề xuất (thực hành trước khi thi)

> ✅ 10 lab dưới đây đã được gộp thành 1 project xuyên suốt: [99-LAB-SnapVault](99-LAB-SnapVault/README.md) — theo dõi tiến độ ở đó.

- [ ] Lab 1: Deploy Lambda function + API Gateway trigger (Hello World API)
- [ ] Lab 2: Kết nối Lambda + DynamoDB (CRUD API đơn giản)
- [ ] Lab 3: Thêm Cognito authentication vào API Gateway
- [ ] Lab 4: Setup S3 event → Lambda (resize ảnh khi upload)
- [ ] Lab 5: SQS + Lambda (xử lý message với DLQ)
- [ ] Lab 6: Viết CloudFormation/SAM template deploy toàn bộ stack trên
- [ ] Lab 7: Setup CI/CD pipeline với CodePipeline + CodeBuild + CodeDeploy
- [ ] Lab 8: Thêm X-Ray tracing vào Lambda + API Gateway
- [ ] Lab 9: Test Lambda alias traffic shifting (canary deployment)
- [ ] Lab 10: Dùng KMS encrypt data trước khi lưu vào S3/DynamoDB

---

## 📚 Tài nguyên ôn luyện

- [ ] AWS Skill Builder — official free courses
- [ ] AWS Whitepapers: Well-Architected Framework (Security & Cost pillar liên quan nhiều)
- [ ] AWS FAQ pages cho Lambda, DynamoDB, S3, API Gateway (đọc kỹ phần FAQ, exam hay hỏi chi tiết)
- [ ] Practice exam (Tutorials Dojo / AWS official practice questions)
- [ ] AWS Docs: Developer Guide cho từng service ở trên

---

## 🗓️ Gợi ý lịch học (8 tuần)

- [ ] **Tuần 1-2:** Domain 1 — Lambda, API Gateway, DynamoDB (core serverless stack)
- [ ] **Tuần 3:** Domain 1 — S3, SQS/SNS/EventBridge, Step Functions
- [ ] **Tuần 4:** Domain 2 — IAM, Cognito, KMS, Secrets Manager
- [ ] **Tuần 5:** Domain 3 — CI/CD (CodePipeline/CodeBuild/CodeDeploy), Deployment strategies
- [ ] **Tuần 6:** Domain 3 — CloudFormation, SAM, Elastic Beanstalk
- [ ] **Tuần 7:** Domain 4 — CloudWatch, X-Ray, CloudTrail + làm hết 10 labs
- [ ] **Tuần 8:** Practice exam full + ôn lại các cặp dễ nhầm + review sai

---

## ✅ Checklist sẵn sàng thi

- [ ] Làm ít nhất 2-3 bộ practice exam đạt >80%
- [ ] Tự giải thích được sự khác biệt tất cả cặp "dễ nhầm" ở trên mà không cần tra
- [ ] Đã tự tay làm xong 10 labs
- [ ] Review lại toàn bộ FAQ của Lambda, DynamoDB, API Gateway
- [ ] Đặt lịch thi (Pearson VUE / PSI)
