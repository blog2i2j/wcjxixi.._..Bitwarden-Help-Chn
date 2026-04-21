# 清除同步缓存

{% hint style="success" %}
对应的[官方文档地址](https://bitwarden.com/help/article/clear-sync-cache/)
{% endhint %}

当同步更改到您的 Bitwarden 组织时，Directory Connector 将会保留本地缓存。此缓存允许 Directory Connector **仅在两个目录之间发送增量**（之前/之后）。

如果特定目录更改未按预期同步，或者您遇到同步错误（例如「An unhandled server error has occurred」（发生未处理的服务器错误）），请尝试清除此缓存。清除缓存将在下一次同步操作时触发完全同步。

要清除本地缓存：

{% tabs %}
{% tab title="桌面版" %}
打开 [Directory Connector 桌面 App](directory-connector-desktop-app.md)：

1. 选择 **More** 选项卡。
2. 在 **Other** 部分，选择 **Clear Sync Cache** 按钮。
{% endtab %}

{% tab title="CLI" %}
使用如下命令：

```shell
bwdc clear-cache
```
{% endtab %}
{% endtabs %}
