# 与 Bitwarden 支持一起排除移动端故障

{% hint style="success" %}
对应的[官方文档地址](https://bitwarden.com/help/flight-recorder/)
{% endhint %}

在 Bitwarden 移动 App 上（包括 Password Manager 和 Authenticator），您可以激活 **Flight Recorder** 来捕获额外的日志活动，以便对意外行为进行故障排除。这在您与 Bitwarden 支持合作时尤其有用。

Flight Recorder 是一个轻量级的临时事件记录器，它捕获最近的 App 活动，例如用户交互和关键系统事件等。这些信息由您控制，它仅存储在您的设备上，如果您愿意，可以将其导出以与 Bitwarden 支持团队分享。Flight Recorder **不会**记录敏感信息，例如您的主密码或密码库数据等。

## 使用 Flight Recorder <a href="#using-flight-recorder" id="using-flight-recorder"></a>

{% hint style="success" %}
在与 Bitwarden 支持合作时，如果您遇到难以复现的问题，或者遇到了崩溃或意外行为，可能会要求您激活 Flight Recorder。
{% endhint %}

Flight Recorder 默认未激活。要激活 Flight Recorder：

1. 在 Bitwarden 移动 App 中，点击**设置** → **关于**。
2. 向下滚动然后点击 **Flight Recorder**。
3. 检查您要报告给 Bitwarden 支持的问题所涉及的任务或工作流程。

{% hint style="info" %}
Flight Recorder 仅存储一段最近的活动窗口，因此 Bitwarden 建议在激活 Flight Recorder 后立即尝试重现您遇到的问题。
{% endhint %}

Flight Recorder 捕获到您遇到的问题后：

1. 通过从同一菜单将 **Flight Recorder** 切换为关闭以停止记录。
2. 点击**设置** → **关于** → **查看已记录的日志**以下载您的日志文件。每个日志文件都将将一直保留到您将其删除或自创建之日起 30 天后过期为止。
3. 在以后与 Bitwarden 支持沟通时，请将日志文件包含在您关于意外 App 行为、问题或潜在错误的讨论主题中。

## Flight Recorder 捕获的数据 <a href="#data-captured-by-flight-recorder" id="data-captured-by-flight-recorder"></a>

Bitwarden 优先考虑您的安全。Flight Recorder 被设计为：

* 日志仅存储在您的设备上，绝不会自动传输。
* 日志只能由您启动、停止或共享。
* 日志不包含敏感的用户数据，如主密码或密码库数据。

Flight Recorder 被激活期间，可能会捕获以下数据：

| 类别                  | 数据                                    |
| ------------------- | ------------------------------------- |
| 用户事件                | 屏幕导航和导航时间戳，按键点击和用户交互，进入和退出模态、表单或重叠。   |
| App & 构建信息          | Bitwarden App 版本、构建类型、设备平台、设备型号、OS 版本 |
| 崩溃 & 异常报告           | 异常信息、异常类型、异常特定元数据、堆栈跟踪                |
| Flight Recorder 元数据 | 日志记录会话开始时间、日志记录会话持续时间、日志文件大小          |
