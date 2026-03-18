# AGENTS.md

## 作用范围

本文件适用于仓库根目录及其全部子目录。

## 仓库目标

本仓库用于维护 Clash 分流规则与配置文件，不包含可执行代码。

## 关键目录

- `Clash/`: 主配置与规则文件
- `Clash/Ruleset/`: 各服务独立规则集（`.list`）
- `Clash/kclash.ini`: 规则与策略组映射主入口
- `Clash/pref.ini`: 生成参数配置

## 编辑约定

- 仅在必要范围内修改，避免无关文件改动。
- `.list` 文件保持纯文本，一行一条规则，不在逗号后加空格。
- 规则类型使用 Clash 常见格式：`DOMAIN-SUFFIX`、`DOMAIN-KEYWORD`、`DOMAIN`、`IP-CIDR`、`IP-CIDR6`、`GEOIP`。
- 新增规则优先放到对应服务文件；不要把无关服务混入同一规则集。
- 若新增服务规则文件，需同步更新 `Clash/kclash.ini` 中对应 `ruleset` 与策略组映射。
- `kclash.ini` 中规则顺序有优先级：更具体的规则放前面，更通用的规则放后面。

## 提交前检查

- 确认无重复规则、无明显冲突规则。
- 确认新增文件命名与现有风格一致（通常为 `ServiceName.list`）。
- 确认 `kclash.ini` 中新增的规则集链接和策略组名称一致。
- 保持 `README.md` 的使用说明与新增能力一致（如有行为变化）。

