# 账户切换

{% hint style="success" %}
对应的[官方文档地址](https://bitwarden.com/help/account-switching/)
{% endhint %}

您知道吗？您可以在 Bitwarden 桌面和移动应用程序中同时登录**多达 5 个** Bitwarden 帐户。使用帐户切换功能，在个人帐户和工作帐户等 Bitwarden 帐户之间无缝切换。

## 登录第二个账户 <a href="#login-to-a-second-account" id="login-to-a-second-account"></a>

{% tabs %}
{% tab title="移动端" %}
要登录第二个（或第三个、第四个或第五个）帐户，请从顶部菜单栏中选择当前已登录的帐户，然后选择 **🞤添加帐户**。

{% embed url="https://bitwarden.com/_gatsby/image/24972ae798dd78136d3862197dc1eb0f/f733d76482dc17b25769efd395e73745/mobile%20account%20switching.webp?u=https%3A%2F%2Fimages.ctfassets.net%2F7rncvj1f8mw7%2F56xAZhiS6wZqKktMlFwbVn%2F163fe1ed9686da777b621eb7c37d5128%2Fmobile_account_switching.png&a=w%3D850%26h%3D654%26fm%3Dwebp%26q%3D75&cd=2022-06-01T12%3A31%3A35.154Z" %}
移动端账户切换
{% endembed %}

选择 **🞤添加帐户**将带您进入登录界面：

{% embed url="https://bitwarden.com/_gatsby/image/adb3a869b1f73d7d81030856e1273f4c/f733d76482dc17b25769efd395e73745/mobile%20account%20switching%202.webp?u=https%3A%2F%2Fimages.ctfassets.net%2F7rncvj1f8mw7%2F112EwzW6sPKPGu65R8rKHc%2Facb93d1607ea1b8cf0018e99272f79fc%2Fmobile_account_switching_2.png&a=w%3D850%26h%3D654%26fm%3Dwebp%26q%3D75&cd=2022-06-01T12%3A31%3A35.159Z" %}
移动端账户切换
{% endembed %}

{% hint style="success" %}
如果您在多台服务器上拥有帐户，例如，如果自托管 Bitwarden 的雇主向您发放了家庭组织赞助，请使用 **⚙️设置**菜单将**服务器 URL** 更改为帐户的 URL。

在此示例中，您的工作帐户可能使用诸如 `https://your.company.bitwarden.com`，而您的家庭组织帐户将使用 `https://vault.bitwarden.com`。
{% endhint %}

登录第二个帐户后，您可以从同一菜单中快速切换它们，该菜单还将显示每个帐户的密码库的当前状态（已锁定或已解锁）。如果您注销其中一个帐户，它将从列表中移除，除非[密码库超时](vault-timeout-options.md)设置为注销。

{% hint style="info" %}
大多数密码库操作，包括添加新项目或文件夹、同步、自动填充以及[密码库超时](vault-timeout-options.md)和解锁（[PIN](unlock-with-pin.md) 或[生物识别](unlocking-with-biometrics.md)）等设置仅适用于_活动_帐户，您可以通过应用程序顶部菜单栏中显示的图标来确定活动账户。

但某些**选项**，例如[主题](../miscellaneous/change-app-theme.md)，则适用于**所有账户**。
{% endhint %}

### 自动填充 <a href="#auto-fill" id="auto-fill"></a>

如果您正使用帐户切换，您的移动应用程序将默认自动填充当前活动帐户的凭据，但是，您可以在自动填充期间从一个帐户切换到另一个帐户：

{% embed url="https://bitwarden.com/_gatsby/image/e6f1ac306e89db673337892c9c2903f4/8be7ce6e6da40a01ff27e11ec51903d7/attempt5.webp?u=https%3A%2F%2Fimages.ctfassets.net%2F7rncvj1f8mw7%2F3bN7xwY4iOL4UoywSAi8Vq%2F58c5529af388736a1f5ace002bfba542%2Fattempt5.gif&a=w%3D652%26h%3D324%26fm%3Dwebp%26q%3D75&cd=2022-06-01T12%3A31%3A35.171Z" %}
Android 账户切换
{% endembed %}
{% endtab %}

{% tab title="桌面端" %}
要登录第二个（或第三个、第四个或第五个）帐户，请从桌面应用程序顶部右上角选择当前已登录的帐户，然后选择 **🞤添加帐户**。

{% embed url="https://bitwarden.com/_gatsby/image/0cdc034d62123377eacdff5652ebbf70/b4b305513c1909542532d5c62739b41f/Screen%20Shot%202022-05-18%20at%203.33.08%20PM.webp?u=https%3A%2F%2Fimages.ctfassets.net%2F7rncvj1f8mw7%2F7fpUmakpNIByzoWQa1cU8L%2F3673552e2fcc77ea3c0a8cae7fbd2b83%2FScreen_Shot_2022-05-18_at_3.33.08_PM.png&a=w%3D850%26h%3D616%26fm%3Dwebp%26q%3D75&cd=2022-06-01T12%3A31%3A35.650Z" %}
桌面端账户切换
{% endembed %}

选择 **🞤添加帐户**将带您进入登录界面：

{% embed url="https://bitwarden.com/_gatsby/image/a5638680a365b752e29e02e23a8a0120/067393f8d5348109439cff77586cfa4a/Screen%20Shot%202022-05-12%20at%2010.58.33%20AM.webp?u=https%3A%2F%2Fimages.ctfassets.net%2F7rncvj1f8mw7%2F3gAo9PEjSXwgf4VY0Ew3TZ%2F11e2e56da3fa052e41f7606a029a004b%2FScreen_Shot_2022-05-12_at_10.58.33_AM.png&a=w%3D850%26h%3D550%26fm%3Dwebp%26q%3D75&cd=2022-06-01T12%3A31%3A35.164Z" %}
桌面端账户切换
{% endembed %}

{% hint style="success" %}
如果您在多台服务器上拥有帐户，例如，如果自托管 Bitwarden 的雇主向您发放了家庭组织赞助，请使用 **⚙️设置**菜单将**服务器 URL** 更改为帐户的 URL。

在此示例中，您的工作帐户可能使用诸如 `https://your.company.bitwarden.com`，而您的家庭组织帐户将使用 `https://vault.bitwarden.com`。
{% endhint %}

登录第二个帐户后，您可以从同一菜单中快速切换它们，该菜单还将显示每个帐户的密码库的当前状态（已锁定或已解锁）。如果您注销其中一个帐户，它将从列表中移除。

{% hint style="info" %}
大多数密码库操作，包括添加新项目或文件夹、同步、搜索以及[密码库超时](vault-timeout-options.md)和解锁（[PIN](unlock-with-pin.md) 或[生物识别](unlocking-with-biometrics.md)）等设置仅适用于_活动_帐户，您可以通过显示在应用程序右上角中的电子邮件来确定活动账户。

但某些**偏好设置**，则适用于**所有账户**。
{% endhint %}
{% endtab %}
{% endtabs %}
