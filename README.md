# mihomo-rules

3X-UI 用的 Mihomo 分流规则。

## 使用

1. 打开面板设置中的 **Clash / Mihomo**，开启“启用路由”，在“全局路由规则”中填入：

   ```text
   https://raw.githubusercontent.com/VfanLee/mihomo-rules/main/routing.yaml
   ```

2. 保存并按提示重启面板。
3. 在 Clash Verge Rev 中更新面板的 Mihomo 订阅，使用规则模式。

也可以复制 [routing.yaml](./routing.yaml) 的内容，直接粘贴到输入框。

国内和私有网络默认直连，广告默认拦截，其他流量通过“节点选择”。已有客户端可能保留之前的选择，可手动切换广告组到 `REJECT`。

所有分组自动包含当前面板订阅的节点。节点有变化时，更新订阅即可；其他订阅的节点需要先加入面板。

文件只包含分流设置，DNS 和端口在客户端配置。修改仓库规则后，也需要刷新面板来源并更新客户端订阅。

规则来自 [MetaCubeX/meta-rules-dat](https://github.com/MetaCubeX/meta-rules-dat)，通过 `gh-proxy.com` 下载，每天更新。
