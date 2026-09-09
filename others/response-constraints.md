# 响应约束和检查 - lambda-refarch-streamprocessing

## 约束清单

| # | 约束 | 状态 |
|---|------|------|
| C1 | 全程使用华为云原生产品 | ✅ |
| C2 | IaC 统一为 Terraform | ⏳ 待执行 |
| C3 | 无对标服务处理 | ✅ 无需处理 |
| C4 | 函数代码不直连原云端点 | ⏳ 待执行 |
| C5 | 无迁移措辞 | ⏳ 待执行 |
| C6 | terraform validate 通过 | ⏳ 待执行 |
| C7 | 产物结构符合约定 | ⏳ 待执行 |
| C8 | 报告无真实 AK/SK | ✅ |
| C9 | apply 前确认费用 | ⏳ 待执行 |
| C10 | ignore_changes 配置 | ⏳ 待执行 |
| C11 | 公网入口告知 | N/A |
| C12 | 许可证统一 | ✅ |
| C13 | 费用信息仅存 others/ | ⏳ 待执行 |
| C14 | 人工降级记录 | N/A |
| C15 | README 实测 | ⏳ 待执行 |

## 自检进度

- [ ] terraform validate 通过
- [ ] src/、infra/ 无残留 AWS 直接依赖
- [ ] docs/、infra/、src/、README.md 无迁移措辞
- [ ] 部署费用信息仅存 others/
- [ ] README 使用方法章节已实测
