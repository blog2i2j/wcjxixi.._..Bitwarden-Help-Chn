# 恢复成员账户

{% hint style="success" %}
对应的[官方文档地址](https://bitwarden.com/help/recover-a-member-account/)
{% endhint %}

恢复忘记主密码或丢失可信设备的成员的账户：

* 您必须是[所有者、管理员或允许的自定义角色成员](../member-roles.md)。
* 您的组织必须已开启[账户恢复管理策略](../../oversight-visibility/enterprise-policies.md#setting-enterprise-policies)。
* 要恢复账户的成员必须[已注册](account-recovery-enrollment.md)。

{% hint style="success" %}
已注册账户恢复的成员将在**策略**栏中显示一个钥匙图标 (**🔑**)。
{% endhint %}

完成以下步骤已恢复组织成员的账户：

1、在管理控制台中，导航至**成员**视图。

2、对于要恢复其账户的成员，请使用 **≡**&#x9009;项菜单选择 **🔑恢复账户**：

{% embed url="https://res.cloudinary.com/bw-com/image/upload/f_auto/v1/ctf/7rncvj1f8mw7/26oD8iqDY15SNJXCJlQE71/22e66b7e11a56d99c13ac41a1236c4e7/2024-12-03_15-35-51.png?_a=DAJCwlWIZAAB" %}
恢复账户
{% endembed %}

3、在恢复账户窗口中，为用户创建一个**新密码**。如果您的组织启用了[主密码策略](../../oversight-visibility/enterprise-policies.md#master-password)，您将需要创建一个满足实施要求的密码（例如，最少 8 个字符，包含数字）：

{% embed url="https://res.cloudinary.com/bw-com/image/upload/f_auto/v1/ctf/7rncvj1f8mw7/28qKke9XJLj6nTZJjg4mK4/7b1c2c5cb2c139bf08ea4c5f65c9a02a/2024-12-03_15-38-52.png?_a=DAJCwlWIZAAB" %}
创建一个新的密码
{% endembed %}

4、复制新的主密码然后使用安全的通讯方式联系用户，例如使用 [Bitwarden Send](../../../bitwarden-send/create-a-send.md)。

5、选择**保存**以执行账户恢复。这样做会将用户从当前会话中注销。某些客户端应用程序（比如移动 App）上的活动会话可能会保持活动长达一小时。
