# 安全说明

## 报告安全问题

如果你发现安全漏洞，请通过 GitHub 的 **私有漏洞报告** 功能（仓库 Security → Private vulnerability reporting）私下提交，**不要**公开创建 Issue。

## 安全设计

- 运行时数据（角色卡 / 日记 / 会话）保存在用户自己的设备上，不向外部服务发送（存储位置与数据处理详见 README 常见问答「数据会不会上传？」）
- 仅有的联网例外都由用户主动发起：蒸馏时用户自己提供链接，或用户明确确认联网检索后才发生

## 修复周期

安全问题会在下一个版本中优先修复，请关注 [Releases](https://github.com/Treasure-hub-agent/ai-with-u/releases)。
