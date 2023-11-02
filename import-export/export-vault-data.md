# 导出密码库数据

{% hint style="success" %}
对应的[官方文档地址](https://bitwarden.com/help/article/export-your-data/)
{% endhint %}

您通过任一个客户端应用程序导出你的个人密码库数据，或通过网页密码库或 CLI 导出组织密码库。导出的数据可以下载为纯文本的 `.json` 或 `.csv` 文件，或 `.json` [加密导出](encrypted-exports.md)。

我们建议使用 `.json` 作为更完整的导出，而 `.csv` 目前不能导出支付卡和身份。有关 Bitwarden `.csv` 和 `.json` 文件格式的完整信息，请参阅[使用 Bitwarden .csv 或 .json](condition-a-bitwarden-.csv-or-.json.md)。

密码库导出**将不会包含**[文件附件](../your-vault/file-attachments.md)、回收站中的项目、~~密码历史记录~~以及 Send。

{% hint style="warning" %}
除非您使用[加密导出](encrypted-exports.md)，否则不要通过不安全的渠道（例如电子邮件）来存储或发送导出的文件，用完后请立即将其删除。
{% endhint %}

## 导出个人密码库 <a href="#export-a-personal-vault" id="export-a-personal-vault"></a>

{% hint style="warning" %}
从个人密码库导出数据**不会**导出您所属组织的任何数据。要导出组织数据，请遵循[此说明](export-vault-data.md#export-an-organization-vault)。
{% endhint %}

{% tabs %}
{% tab title="网页密码库" %}
要通过网页密码库导出您的个人密码库数据：

1、从顶部导航栏中选择**工具**。

2、从左侧工具菜单中选择**导出密码库**。

3、在导出密码库页面中，选择一个**文件格式**（`.json`、`.csv` 或 `.json (Encrypted)`）。

4、如果选择 `.json (Encrypted)`，请选择您希望用于加密导出的**文件类型**：

* **账户备份**：该文件只能导入到当前生成加密导出文件的 Bitwarden 账户。
* **密码保护**：可以使用加密导出过程中设置的密码将此文件导入任何 Bitwarden 账户。

5、选择**确认格式**，输入您的主密码，然后选择**导出密码库**按钮以完成。
{% endtab %}

{% tab title="浏览器扩展" %}
要通过浏览器扩展导出您的个人密码库数据：

1、打开 **⚙️设置**标签。

2、向下滚动到**工具**部分并选择**导出密码库**选项。

3、在导出密码库视图中，选择一个**文件格式**（`.json`、`.csv`，或 `.json (Encrypted)`）。

{% hint style="success" %}
如果您需要将此数据导入新的 Bitwarden 帐户，我们建议使用网络密码库创建**密码保护**的导出。
{% endhint %}

4、输入您的**主密码**然后选择**提交**。

{% hint style="info" %}
如果您是从 Vivaldi 浏览器扩展导出，您可能需要弹出浏览器扩展以便导出能正常工作。
{% endhint %}
{% endtab %}

{% tab title="桌面端" %}
要通过桌面应用程序导出您的个人密码库数据：

1、从菜单栏中，导航到**文件** → **导出密码库**。

2、在导出密码库窗口中，选择一个**文件格式**（`.json`、`.csv`，或 `.json (Encrypted)`）。

{% hint style="success" %}
如果您需要将此数据导入新的 Bitwarden 帐户，我们建议使用网络密码库创建**密码保护**的导出。
{% endhint %}

3、输入您的**主密码**然后选择 **📥下载**按钮。
{% endtab %}

{% tab title="移动端" %}
要通过移动应用程序导出您的个人密码库数据：

1、点击 ⚙️**设置**标签。

2、向下滚动到**工具**部分并点击**导出密码库**选项。

3、在导出密码库视图中，选择一个**文件格式**（`.json`、`.csv`，或 `.json (Encrypted)`）。

{% hint style="success" %}
如果您需要将此数据导入新的 Bitwarden 帐户，我们建议使用网络密码库创建**密码保护**的导出。
{% endhint %}

4、输入您的**主密码**然后点击**导出密码库**按钮。
{% endtab %}

{% tab title="CLI" %}
要通过 CLI 导出您的个人密码库数据，需使用 `export` 命令。默认情况下，`export` 导出密码库为 `.csv` 文件并保存在工作目录下，然而，这种行为可以通过使用选项来更改：

```batch
bw export --output /users/me/documents/ --format json --password mYP@ssw0rd
```

`--password` 选项可用于指定一个加密 `encrypted_json` 导出的密码，而不是您的[帐户加密密钥](../security/account-encryption-key.md)。

更多详情，请参阅 Bitwarden [CLI 文档](../password-manager/developer-tools/password-manager-cli.md)。
{% endtab %}
{% endtabs %}

有关个人密码库导出中包含的所有项目和字段的完整列表，请参阅此 **⬇️**[JSON 示例](https://assets.ctfassets.net/7rncvj1f8mw7/3klSoZBBd57skEvwFkcMJc/9dfe5d696c102cd32da88dc325706738/Individual\_vault\_export.json)。

## 导出组织密码库 <a href="#export-an-organization-vault" id="export-an-organization-vault"></a>

组织的[管理员和所有者](../admin-console/user-management/member-roles-and-permissions.md)可以通过网页密码库或 CLI 导出他们的组织密码库（即组织拥有的所有项目）：

{% tabs %}
{% tab title="网页密码库" %}
要通过网页密码库导出您的组织密码库：

1、打开您的组织然后选择**设置**标签页。

2、在**设置**菜单中选择**导出密码库**：

{% embed url="https://bitwarden.com/_gatsby/image/1b51ec6faaad683faf85662a97be2ee7/9491affef7bef9021a7c1e0b8604530a/Screen%20Shot%202022-12-27%20at%204.10.38%20PM.webp?eu=dc8852e2e69aad850861a1d13b7a693ab53f03a8f65133d03d64ecaf1bfa98d522f54d56259d2fb62d615288d4e414ba63c12e371eedd5da92b44cf1e267a30e06865be86ee624545523c3abe2fc04163bce490ef3d6cd0fa3682387e0b2b7251a564e7efe28b884e8fc3764b4862d33e9e2a2286091fd7de2115c019d1b7ba420ffd09d3901f197ed4eb8b3adb75a89cab66e44159fb02b7c2208005faf73e8e3e805273174075c2accca398e34f0f17f6132705f0904b13440af0ba5094edcecfca50c8b7d73e4fdcf3275d0c2fbd2e819fa2c75b4c927fc843f28080cac15b2df28b587315861e272a5d123b00307375d831e942627b6691be3039ae0478d2bf401464b2f80a24d&a=w%3D850%26h%3D440%26fm%3Dwebp%26q%3D75&cd=2023-02-15T12%3A50%3A03.846Z" %}
导出组织密码库
{% endembed %}

3、在导出密码库页面，选择一个**文件格式**（`.json`、`.csv` 或 `.json (Encrypted)`），然后选择**确认格式**按钮。

4、输入您的主密码然后选择**导出密码库**按钮。

{% hint style="info" %}
导出组织密码库数据将被事件日志捕获。[了解更多](../admin-console/reporting/event-logs.md)。
{% endhint %}
{% endtab %}

{% tab title="CLI" %}
要通过 CLI 导出您的组织密码库，需使用带 `--organizationid <orgId>` 选项的 `export` 命令。

默认情况下，`export` 导出密码库为 `.csv` 文件并保存在工作目录下，然而，这种行为可以通过使用选项来更改：

```batch
bw export my-master-password --organizationid 7063feab-4b10-472e-b64c-785e2b870b92 --output /users/me/documents/ --format json
```

{% hint style="success" %}
如果您一时不知道您的 `organizationid` 值，可以在命令行使用 `bw list organizations` 来获取它。
{% endhint %}

更多详情，请参阅 Bitwarden [CLI 文档](../password-manager/developer-tools/password-manager-cli.md)。

{% hint style="info" %}
导出组织密码库数据将被事件日志捕获。[了解更多](../admin-console/reporting/event-logs.md)。
{% endhint %}


{% endtab %}
{% endtabs %}

有关组织密码库导出中包含的所有项目和字段的完整列表，请参阅此 **⬇️**[JSON 示例](https://assets.ctfassets.net/7rncvj1f8mw7/2oQPd5ZsY1N0hph4N6pBrY/b5fc7c05ac238d71d9a1902a58559cc6/Organization\_vault\_export.json)。
