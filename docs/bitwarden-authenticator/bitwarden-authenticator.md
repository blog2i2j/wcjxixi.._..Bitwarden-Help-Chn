# =Bitwarden Authenticator

{% hint style="success" %}
对应的[官方文档地址](https://bitwarden.com/help/bitwarden-authenticator/)
{% endhint %}

Bitwarden Authenticator 是一款独立的 App，可为支持身份验证 App 双重身份验证 (2FA) 的登录生成基于时间的一次性密码 (TOTP)。Bitwarden Authenticator 生成 5-10 位的代码，默认使用 SHA-1 并每 30 秒轮换一次。

Bitwarden 提供两种身份验证器：Bitwarden Authenticator App 和 Password Manager 集成身份验证器。 Bitwarden Authenticator 可供所有人使用，无论是否拥有 Bitwarden Password Manager 账户。如果您使用这两个 App，则可以在 Authenticator 和 Bitwarden 密码库之间同步代码。同步后，您的代码将标注为**本地代码**或由您的账户电子邮件地址标注：

{% embed url="https://bitwarden.com/assets/4fMWMI0YBJQybhhyOlV0Zb/2bb912b6e9a6f38818cc37d8a0f982b4/2025-05-21_10-13-39.png?w=780&fm=avif&q=80" %}
Bitwarden iOS Authenticator App
{% endembed %}

## 安装 Bitwarden Authenticator <a href="#install-bitwarden-authenticator" id="install-bitwarden-authenticator"></a>

Bitwarden Authenticator 可在 iOS 和 Android 设备上使用。首先，从设备的 App 商店下载该 App：

* iOS：[App Store](https://apps.apple.com/us/app/bitwarden-authenticator/id6497335175) (iOS 15+)
* Android：[Google Play](https://play.google.com/store/apps/details?id=com.bitwarden.authenticator\&pli=1) (Android 9+)

{% hint style="info" %}
在 iOS 16+ 上，当直接从相机 App 扫描代码时，您可以将 Bitwarden Authenticator 或 Password Manager 集成身份验证设置为默认的验证码 App。要进行此设置：

1. 打开设备上的 iOS **设置** App。
2. 点击**通用**。
3. 点击**自动填充与密码**。
4. 点击**密码选项**。
5. 在**验证码**部分中，从**设置验证码**下拉菜单中选择一个 App。
{% endhint %}

## 添加代码 <a href="#add-codes" id="add-codes"></a>

如果设置为与 Password Manager 同步，Authenticator 将自动添加并更新存储在 Password Manager 中的验证码。使用 Authenticator App，您还可以**扫描二维码**或**手动添加代码**，并选择是将其保存在本地还是保存在 Password Manager 中：

{% tabs %}
{% tab title="扫描二维码" %}
&#x20;在 Bitwarden Authenticator 中：

1. 点击 ✚图标。
2. 将相机对准二维码。扫描将自动进行。
3. 选择**保存在这里**（表示仅保存在 Authenticator 中）或是**保存到 Bitwarden**（表示保存为 Password Manager 中的登录项目）。
{% endtab %}

{% tab title="手动添加代码" %}
在 Bitwarden Authenticator 中：

1. 点击 ✚图标。
2. 点击屏幕底部的**手动输入密钥**。
3. 在**名称**字段中输入网站或 App 的名称。
4. 输入网站或 App 提供的**验证器密钥**。某些服务将此称为「机密密钥」或「TOTP 种子」。
5. 选择**保存在这里**（表示仅保存在 Authenticator 中）或是**保存到 Bitwarden**（表示保存为 Password Manager 中的登录项目）。
{% endtab %}

{% tab title="从 Password Manager 同步" %}
要从 Bitwarden Password Manager 同步 TOTP：

1. 确保您的设备上已同时安装了 Bitwarden Authenticator 和 Bitwarden Password Manager，并在 Password Manager 中登录了您要同步的账户。
2. 在 Password Manager 中，导航到**设置** → **账户安全**，然后打开**允许验证器同步**选项。
3. 在 Bitwarden Authenticator 中，确认 Password Manager 中存储的任何 TOTP 都列在您的 Bitwarden 账户标题下，而不是在**本地代码**下。

{% hint style="info" %}
身份验证器同步功能适用于 Android 版本 12 或更高版本。
{% endhint %}

{% hint style="info" %}
您可以与任意多个 Bitwarden Password Manager 账户同步，但需要为每个账户分别切换**允许验证器同步**选项。
{% endhint %}
{% endtab %}
{% endtabs %}

{% hint style="success" %}
如果您在 Authenticator 中创建本地代码，稍后想要将其添加到您的密码库，请将该代码复制到 Password Manager。
{% endhint %}

## 编辑代码 <a href="#edit-codes" id="edit-codes"></a>

要编辑从密码库同步的代码，请[更新 Password Manager 中的登录项目](../password-manager/your-vault/vault-items/vault-items.md#manage-items)。对于仅存储在 Authenticator 中的本地代码，长按该代码然后选择**编辑**以访问以下选项：

* 编辑**名称**或**密钥**。
* 添加**用户名**。当您在同一网站拥有多个账户并且每个账户需要单独的验证码时，请使用此字段。
* 打开**收藏**，可将该代码移动到 App 主界面的顶部，以便于访问。
* 更改用于生成代码的**算法**。Bitwarden Authenticator 默认使用 SHA-1。
* 更改代码的**刷新周期**。Bitwarden Authenticator 默认使用 30 秒。
* 更改代码的**位数**。Bitwarden Authenticator 默认使用 6 位数字。

{% hint style="success" %}
**算法**、**刷新周期**和**位数**由您使用验证码的网站决定。除非该网站要求或允许您自定义验证码行为，否则请勿更改这些设置项目。
{% endhint %}

## 使用代码 <a href="#use-codes" id="use-codes"></a>

要使用验证码，请打开 Bitwarden Authenticator 然后点击某条目以复制验证码。然后，将代码粘贴到您登录时的验证提示中。

## 将代码传输到新的移动设备 <a href="#transfer-codes-to-a-new-mobile-device" id="transfer-codes-to-a-new-mobile-device"></a>

## FAQ <a href="#frequently-asked-questions" id="frequently-asked-questions"></a>

<details>

<summary>Bitwarden Authenticator 和 Password Manager 集成身份验证器有什么区别？</summary>

独立的 Bitwarden Authenticator App 和密码管理器集成身份验证器存储并生成 TOTP。根据您的安全偏好，您可以一起、独立、或在它们之间切换使用这些 App。同时使用时，请决定是保持代码连接还是单独管理。主要区别包括：

| 特性       | Authenticator                                                                                               | 密码管理器集成身份验证器                                                   |
| -------- | ----------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------- |
| 谁可以使用它   | 所有人。不要求 Bitwarden 账户                                                                                        | <p>免费账户可以存储密钥。</p><p></p><p>高级用户和付费组织的成员可以存储密钥并生成 TOTP 代码。</p> |
| 主要用途     | 任何喜欢将 2FA 代码与密码管理器和想要生成 TOTP 代码的免费 Bitwarden 账户分开存储的人                                                       | 便捷的一体化密码和 2FA 管理                                               |
| 平台       | 仅限移动设备，iOS 和 Android                                                                                        | 所有 Bitwarden 客户端，包括移动 App、浏览器扩展、桌面 App 和网页 App                 |
| 默认存储     | <p>您的本地设备</p><p></p><p>*如果您的 Password Manager 允许身份验证器同步和/或您主动将本地代码复制到您的密码库，则这些代码也会存储在您的 Bitwarden 密码库中。</p> | 您的 Bitwarden 密码库                                               |
| App 之间同步 | 可以手动将本地代码复制到 Password Manager 以允许同步，并且可以自动与 Password Manager 中的代码同步                                         | 可以自动与 Authenticator 中的代码同步                                     |

</details>

<details>

<summary>我可以使用 Bitwarden Authenticator 将 2FA 添加到我的 Bitwarden 账户吗？</summary>

可以！因为 Bitwarden Authenticator 允许您在 Bitwarden 账户外存储代码，所以这个 App 可以用来为您的 Bitwarden 账户添加 2FA。

如果执行此操作，请将代码保存为身份验证器中的本地代码，以防止其同步到您的密码库。将代码同步到其要保护的同一个密码库可能会将您锁定。

</details>

<details>

<summary>如何更改 Authenticator App 的外观？</summary>



</details>

<details>

<summary>我的数据如何存储和保护？</summary>

您的验证密钥（有时称为「安全秘钥」或「TOTP 种子」）和所有相关元数据都存储在您设备上的本地未加密数据库中。这些数据不会同步到 Bitwarden 服务器。您的数据将由您设备的云备份系统（如 iCloud 或 Google One）进行备份。要保护您的 App 中的数据，您还可以设置生物识别登录。

</details>

<details>

<summary>如何备份和恢复我的 TOTP 数据？</summary>

您设备的云备份系统（如 iCloud 或 Google One）会对您的数据进行加密备份。要恢复数据，请恢复您设备的云备份。

您还可以导出身份验证器数据并将其安全地存储为备份。

</details>

<details>

<summary>我使用的是哪个版本的 Bitwarden Authenticator？</summary>

要了解您正在使用的 Bitwarden Authenticator 版本，请转到**设置**然后向下滚动到**关于**部分。

</details>
