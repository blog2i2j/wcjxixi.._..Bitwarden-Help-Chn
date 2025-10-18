# 导入到组织密码库

{% hint style="success" %}
对应的[官方文档地址](https://bitwarden.com/help/article/import-to-org/)
{% endhint %}

直接将数据导入您的组织，以便轻松地从任何密码管理解决方案迁移到 Bitwarden。有关支持的导入格式的完整列表，请参阅 [Bitwarden 支持导入哪些文件格式？](../../../import-export/import-and-export-faqs.md#q-what-file-formats-does-bitwarden-support-for-import)。直接导入数据到您的组织有两种方式：

* 组织[所有者、管理员和具有合适权限的自定义角色用户](../../manage-members/member-roles.md)可以通过本文中的说明使用组织的管理控制台导入项目。
* 具有[管理集合权限](../collections/collection-permissions.md)的组织成员可以通过[此流程](../../../password-manager/import-and-export/import-data.md)直接将数据导入他们具有权限的任何集合。

## 导入到组织密码库 <a href="#import-to-an-organization-vault" id="import-to-an-organization-vault"></a>

数据只能从网页 App 导入到组织。数据在发送到服务器存储之前会在本地本地[加密](../../../security/encryption/encryption-protocols.md)。

{% hint style="info" %}
虽然某些项目类型无法导入，但您仍可将其添加到密码库：

* 将[文件附件](../../../your-vault/file-attachments.md)单独上传到新的密码库。
* 在新的密码库中重新创建 [Send](../../../bitwarden-send/about-send.md)。
{% endhint %}

1、登录 Bitwarden 网页 App 然后打开管理控制台：

{% embed url="https://res.cloudinary.com/bw-com/image/upload/f_auto/v1/ctf/7rncvj1f8mw7/2uxBDdQa6lu0IgIEfcwMPP/e3de3361749b6496155e25edcfdcf08b/2024-12-02_11-19-56.png?_a=DAJCwlWIZAAB" %}
产品切换器
{% endembed %}

2、转到**设置** → **导入数据**：

{% embed url="https://res.cloudinary.com/bw-com/image/upload/f_auto/v1/ctf/7rncvj1f8mw7/12fA17Iq9LdCXdhPsPYQyq/6fb380ff6165058fefe6fd311e038364/2024-12-03_15-42-21.png?_a=DAJCwlWIZAAB" %}
管理控制台导入
{% endembed %}

3、在**数据**中，选择您要导入的[文件格式](../../../import-export/import-and-export-faqs.md#q-what-file-formats-does-bitwarden-support-for-import)。如果您正在导入一个[加密导出](../../../import-export/encrypted-exports.md)，请注意这没有单独的选项。选择 **.json** 然后处理程序将确定文件是加密的，并尝试使用您的[账户加密密钥](../../../security/encryption/encryption-key-rotation.md)或加密导出的密码来解密文件。

{% hint style="success" %}
如果您希望将导入文件的内容直接放入指定集合中，请使用**目的地**部分中的**集合**下拉列表来选择一个集合。当导入供特定用户群体使用的数据块而不是导入组织的所有数据时，这通常最有用。
{% endhint %}

4、选择**选择文件**并添加要导入的文件，或将文件内容复制/粘贴到输入框中。

{% hint style="danger" %}
导入过程不会检查重复。如果您多次导入同一文件或导入的项目已经存在于密码库中，则会创建重复的项目。
{% endhint %}

5、选择**导入数据**以触发导入。如果要导入受密码保护的 `.json` 文件，请在出现的**确认密码库导入**窗口中输入密码。

## 导入错误故障排除 <a href="#troubleshoot-import-errors" id="troubleshoot-import-errors"></a>

如果出现「导入错误」消息，则表明没有数据添加到您的密码库中。[修复导入文件问题](../../../password-manager/import-and-export/import-data.md#troubleshoot-import-errors)然后重试。

某些导入错误是针对组织的：

* **文件包含未分配的项目**：确保所有[项目至少分配给一个集合](../../../password-manager/import-and-export/import-data.md#https-bitwarden.com-help-import-data-file-contains-unassigned-items)，然后再尝试重新上传文件。
* **组织最多只能有两个集合**：免费组织支持最多两个集合。如果您的导入文件超过此限制，[减少文件中的集合数量](../../../password-manager/import-and-export/import-data.md#organization-can-only-have-a-maximum-of-two-collections)或升级以导入更多。

{% hint style="info" %}
为减少此错误，请开启[限制为仅所有者和管理员可以创建集合设置](../collections/collection-settings.md#restrict-collection-creation-to-owners-and-admins)，以防止用户创建集合。
{% endhint %}
