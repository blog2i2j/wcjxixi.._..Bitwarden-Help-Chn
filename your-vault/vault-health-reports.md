# 密码库健康报告

{% hint style="success" %}
对应的[官方文档地址](https://bitwarden.com/help/article/reports/)
{% endhint %}

密码库健康报告可用于评估 Bitwarden 个人或组织密码库的安全性。

{% hint style="info" %}
密码库健康报告功能适用于高级用户，包括付费组织（家庭、团队或企业）的成员。
{% endhint %}

## 查看报告 <a href="#view-a-report" id="view-a-report"></a>

完成以下步骤以查看您的**个人密码库**的任何密码库健康报告：

1、登录到[网页密码库](../getting-started/getting-started-webvault.md) 。

2、从顶部导航栏选择**报告**。

{% embed url="https://images.ctfassets.net/7rncvj1f8mw7/JcoKvP7eLrZHUEKmjTqgc/ac824e27d1c6d09866d1a3abdcecf277/Screen_Shot_2022-04-06_at_9.08.04_AM.png?fm=webp&h=593&q=50&w=800" %}
报告页面
{% endembed %}

3、选择要运行的报告。

完成以下步骤以查看您的**组织密码库**的任何密码库健康报告：

1、登录到[网页密码库](../getting-started/getting-started-webvault.md)并打开您的组织 。

2、在您的组织中，打开**工具**标签页。

{% embed url="https://images.ctfassets.net/7rncvj1f8mw7/5POQmt3TrEgfFzRNwHancg/17f24424c574f0b4f845fb348771ce5a/tools-section.png?fm=webp&h=421&q=50&w=707" %}
组织报告
{% endembed %}

3、从左侧菜单的**报告**部分选择一个报告。

## 可用的报告 <a href="#available-reports" id="available-reports"></a>

### 公开密码报告 <a href="#exposed-passwords-report" id="exposed-passwords-report"></a>

**公开密码报告**可以识别被黑客公开发布或在暗网上出售的已知数据泄露事件中发现的密码。

该报告使用受信任的网络服务在已知泄露密码的数据库中检索您所有密码哈希值的前 5 位，然后，将返回的匹配的散列列表与你的密码的完整散列列表进行本地比较。这种比较只在本地进行，以保护你的 [k-匿名性](https://en.wikipedia.org/wiki/K-anonymity)。

确定后，你应该为违规账户或服务创建一个新的密码。

{% hint style="success" %}
**为什么使用密码哈希值的前 5 位？**

如果此报告使用你的实际密码来执行，那这些密码是否暴露并不重要了，因为你主动将其泄露给此服务了。并且这个报告的结果并不意味着你的个人账户已被泄露，只是你使用的密码已经在这些暴露的密码数据库中被发现，你应该避免使用泄露的密码和非唯一的密码。
{% endhint %}

### 重复使用的密码报告 <a href="#reused-passwords-report" id="reused-passwords-report"></a>

**重复使用的密码报告**可以识别密码库中的非唯一密码。如果在多个服务中重复使用相同的密码，当一个服务被攻破时，会让黑客轻松获取您的更多在线账户的访问权限。

确定后，您应该为违规账户或服务创建一个唯一的密码。

### 弱密码报告 <a href="#weak-passwords-report" id="weak-passwords-report"></a>

**弱密码报告**可以识别出容易被黑客和用于破解密码的自动化工具猜中的弱密码，并按弱点的严重性进行排序。Bitwarden 密码生成器可以帮助您创建更强大的密码。

确定后，您应该使用 Bitwarden 密码生成器为违规账户或服务创建一个强密码。

### 不安全网站报告 <a href="#unsecured-websites-report" id="unsecured-websites-report"></a>

**不安全网站报告**可以识别在 URI 中使用不安全(`http://`)方案的登录项目。使用 `https://` 的 TLS/SSL 加密通信要安全得多。要了解更多信息，请参阅 [URI 的使用](../auto-fill/using-uris.md)。

确定后，您应该将违规的 URI 由 `http://` 更改为 `https://`。

### 未激活 2FA 报告 <a href="#inactive-2-fa-report" id="inactive-2-fa-report"></a>

**未激活 2FA 报告**可以识别如下的登录项目：

* 该服务提供了通过 TOTP 的双重验证（2FA）
* 您尚未存储 TOTP 验证证器密钥

双重验证（2FA）是保护您帐户安全的一个重要安全设置。如果网站提供，您应该始终启用双重验证。通过将 URI 数据与来自 [https://2fa.directory/](https://2fa.directory/) 的数据进行交叉引用，可以识别出违规项目。

确定后，使用`说明（Instructions）`超链接来为每个违规项目设置 2FA。

### 数据泄露报告（仅个人密码库） <a href="#data-breach-report-individual-vaults-only" id="data-breach-report-individual-vaults-only"></a>

**数据泄露报告**使用一种叫做 Have I Been Pwned (HIBP) 的服务来识别已知事件中的泄露数据（电子邮件地址、密码、信用卡、DoB 等）。

> \[**译者注**]：DoB - Date of Birth，出生日期

HIBP 将「泄漏」定义为「通常是由于访问控制不足或软件的安全弱点造成数据在脆弱的系统中无意中暴露的事件」。更多信息，请参阅 [HIBP 常见问题文档](https://haveibeenpwned.com/FAQs)。

{% hint style="info" %}
如果您是自托管 Bitwarden，想要在您的实例中运行**数据泄露报告**，您需要购买 HIBP 订阅密钥，该密钥将授权您对 API 进行调用。可以[在此处](https://haveibeenpwned.com/API/Key)购买此密钥。

拥有此密钥后，打开 `./bwdata/env/global.override.env` 并将 `globalSetting__hibpApiKey=` 的占位符值替换为你购买的 API 密钥：

```
globalSettings__hibpApiKey=REPLACE
```

更多信息，请参阅[配置环境变量](../on-premises-hosting/configure-environment-variables.md)。
{% endhint %}
