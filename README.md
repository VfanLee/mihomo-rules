# Mihomo 分流规则

供 3X-UI 的 Clash / Mihomo 全局路由功能使用，适用于 Clash Verge Rev 等使用 Mihomo 内核的客户端

## 固定规则地址

```text
https://raw.githubusercontent.com/VfanLee/mihomo-rules/main/routing.yaml
```

## 使用方法

1. 在 3X-UI 中打开“面板设置 → Clash / Mihomo”
2. 开启“启用路由”，将上方固定地址填入“全局路由规则”
3. 保存设置，并按面板提示重启面板
4. 在 Clash Verge Rev 中导入或更新面板生成的 Clash / Mihomo 订阅，使用规则模式
5. 检查“🚀 节点选择”和“⚡ 自动选择”是否包含当前订阅节点；“🛑 广告拦截”首次使用默认选择 REJECT，已有客户端可手动确认选择

也可以打开 [routing.yaml](./routing.yaml)，复制全部内容粘贴到同一输入框

## 分流与节点

- 包含 21 个策略组、47 个规则提供者、48 条规则
- 按广告、AI、视频、社交媒体、游戏、教育、金融、云服务等分类分流
- 国内服务及私有网络默认直连，其他分类默认通过“🚀 节点选择”
- 所有策略组使用 `include-all-proxies: true`，自动包含面板为当前订阅生成的出站节点；“⚡ 自动选择”每 300 秒测速
- 节点新增、删除、改名或 Reality 参数调整后，更新客户端订阅即可，无需修改本文件中的节点引用
- 其他面板或其他订阅中的节点需要先纳入当前面板订阅，才会出现在策略组中

## 配置边界

本文件仅包含 `proxy-groups`、`rule-providers` 和 `rules`，节点连接参数由面板生成，DNS、监听端口等由客户端现有配置负责

远程规则更新需要面板刷新远程来源并由客户端更新订阅后生效，不保证立即推送到客户端；规则提供者由客户端按 86400 秒间隔更新

规则来源为 [MetaCubeX/meta-rules-dat](https://github.com/MetaCubeX/meta-rules-dat)，下载地址保留原配置使用的 `gh-proxy.com`，实际可用性取决于客户端网络

## 验证范围

发布前检查 YAML 格式、策略组和规则引用、循环引用及广告默认选项，并检查公开文件不包含节点凭据

3X-UI 订阅生成、规则下载和实际分流效果需在使用环境中验收
