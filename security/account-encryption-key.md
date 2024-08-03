# 账户加密密钥

{% hint style="success" %}
对应的[官方文档地址](https://bitwarden.com/help/article/account-encryption-key/)
{% endhint %}

每个 Bitwarden 账户都有一个根据[加密](encryption.md)中定义的方法，从您的主密码派生出来的加密密钥。该加密密钥用于加密所有密码库数据。

## 轮换您的加密密钥 <a href="#rotate-your-encryption-key" id="rotate-your-encryption-key"></a>

{% hint style="warning" %}
**轮换加密密钥是潜在的危险操作。**请通读本章节，以了解这样做的全部后果。
{% endhint %}

轮换账户的加密密钥会生成一个新的加密密钥，用于重新加密所有密码库数据。如果您的账户已被盗用，并且有人获得了您的加密密钥，则您应该考虑轮换您的加密密钥。

### 轮换之前 <a href="#before-rotating" id="before-rotating"></a>

在轮换之前，您应该采取以下措施以防止数据丢失或损坏：

#### 重新创建账户的加密导出 <a href="#re-create-any-account-backup-exports" id="re-create-any-account-backup-exports"></a>

如果您使用[加密导出](../import-export/encrypted-exports.md)来存储长期的安全备份，您应该立即使用新的加密密钥重新创建密码库数据的加密导出。

加密导出使用您的加密密钥来加密**以及解密**您的密码库数据，这意味着，经过轮换的加密密钥将无法解密使用「陈旧」（轮换前）的密钥创建的导出。

#### 注销客户端应用程序 <a href="#log-out-of-client-applications" id="log-out-of-client-applications"></a>

轮换加密密钥后，您**必须立即**注销 Bitwarden 客户端应用程序（桌面应用程序、浏览器扩展、移动应用程序等）上的任何已登录会话。以这种方式注销客户端应用程序将关闭使用「陈旧」（轮换前）加密密钥的会话。然后，像往常一样重新登录将使用新的加密密钥。

**在使用「陈旧」加密密钥的会话中进行更改将导致数据损坏，使您的数据无法恢复。**

{% hint style="danger" %}
我们建议在轮换您的账户加密密钥之前创建密码库备份。要了解有关密码库导出以及包含哪些项目的更多信息，请参阅导[出密码库数据](../import-export/export-vault-data.md)。
{% endhint %}

### 如何轮换您的加密密钥 <a href="#how-to-rotate-your-encryption-key" id="how-to-rotate-your-encryption-key"></a>

要轮换您账户的加密密钥：

1、在网页 App 中，导航到**设置** → **安全** → **主密码**：

{% embed url="https://res.cloudinary.com/bw-com/image/upload/f_auto/v1/ctf/7rncvj1f8mw7/2Svv0PwlH9i7SSK73dlv9A/a5dbbf97d447c3fff64074fabeec2ac0/Screenshot_2024-02-26_at_4.13.59_PM.png?_a=DAJAUVWIZAAB" %}
主密码设置
{% endembed %}

2、输入您的**当前主密码**并输入/确认**新主密码**。

{% hint style="success" %}
如果您不想更改您的主密码而只想轮换您的账户加密密钥，您可以在**新的**字段中输入您当前的主密码以防止其更改。
{% endhint %}

3、勾选**同时轮换我的账户的加密密钥**复选框并接受弹出的对话框。

4、选择**更改主密码**按钮。

> **\[译者注]**：更改您的主密码或更改加密密钥设置（KDF）时，均不会主动轮换账户的加密密钥。仅在更改您的主密码时勾选**同时轮换账户的加密密钥**才会更改您账户的加密密钥。
