# 账户恢复

{% hint style="success" %}
对应的[官方文档地址](https://bitwarden.com/help/account-recovery/)
{% endhint %}

{% hint style="info" %}
账户恢复适用于当前计划的**企业组织**。与 SSO 登录一样，账户恢复不适用于[经典 2019 企业组织](../plans-and-pricing/updates-to-bitwarden-plans-2019-2020.md)计划。
{% endhint %}

## 什么是账户恢复？ <a href="#what-is-account-recovery" id="what-is-account-recovery"></a>

账户恢复（以前叫「管理员密码重置」）允许[指定的管理员](admin-password-reset.md#permissions)恢复企业组织用户账户以及在员工忘记[主密码](../your-vault/your-master-password.md)时恢复访问权限。通过[启用账户恢复策略](admin-password-reset.md#activate-account-recovery)为组织激活账户恢复。

个人用户必须被注册（通过[自行注册](admin-password-reset.md#self-enroll-in-password-reset)或使用[自动注册策略选项](admin-password-reset.md#automatic-enrollment)）才有资格进行账户恢复，因为注册会触发密钥交换，以确保恢复的安全。

**账户恢复不会绕过两步登录或 SSO 登录。**如果为账户启用了[两步登录方式](../two-step-login/two-step-login-methods.md)，或者如果您的组织[要求 SSO 身份验证](enterprise-policies.md#single-sign-on-authentication)，您在密码重置后仍将需要使用该方式访问您的密码库。

### 加密 <a href="#encryption" id="encryption"></a>

当组织的成员[注册](admin-password-reset.md#automatic-enrollment)账户恢复时，该用户的[加密密钥](../security/account-encryption-key.md)将使用组织的公钥进行加密。其结果将作为**账户恢复密钥**存储。

当执行恢复操作时：

1. 使用组织对称密钥解密组织私钥。
2. 使用已解密的组织私钥解密用户的**账户恢复密钥**，从而得到用户的[加密密钥](../security/account-encryption-key.md)。
3. 用户的加密密钥和主密码散列被替换为新的加密密钥和新的主密码散列，这些散列源自新的主密码。
4. 使用组织的公钥加密用户新的加密密钥，使用新的密钥替换之前的**账户恢复密钥**。

任何人，包括执行重置的管理员，都**无法**看到旧的主密码。

### 权限 <a href="#permissions" id="permissions"></a>

管理员密码重置可由[所有者、管理员和允许的自定义用户](../admin-console/user-management/member-roles-and-permissions.md)执行。管理员密码重置使用分级权限结构来确定谁可以重置谁的主密码：

* 任何所有者、管理员或允许的自定义用户都可以重置用户、经理或自定义用户的主密码。
* 只有管​​理员或所有者可以重置管理员的主密码。
* 只有所有者可以重置其他所有者的主密码。

### 事件日志 <a href="#event-logging" id="event-logging"></a>

以下情况会记录[事件](../admin-console/reporting/event-logs.md)：

* 使用账户恢复重置了主密码。
* 用户更新了通过账户恢复颁发的密码。
* 用户注册了账户恢复。
* 用户撤销了账户恢复。

## 激活账户恢复 <a href="#activate-account-recovery" id="activate-account-recovery"></a>

要为您的企业组织激活账户恢复，请导航到组织的**管理**选项卡，从左侧菜单选择**策略**，然后启用**账户恢复管理**策略：

{% embed url="https://bitwarden.com/_gatsby/image/3ed737ae33882d52451effd692957b53/c108ed4ae804218975cdc02452f19206/Screen%20Shot%202023-07-17%20at%202.53.44%20PM.webp?eu=8ddc58e3eacaaa84093ef2d13e71343db26d56acf85035816867edfe4ea1cb8f71f51b5673c42ee42c3a5a8cd7e840ec36907e304cead88ec9ef18f1e936fc5c51d252bb61bb7600552bc0ffb6f4524169cf195ea0879e0ca26e72d4e1b0bf701d58182ca222fcc5acea3f7bafda7263bde3e5303686fd29a3510b1088062fa920a4979c6d4da894b149e7bba9ae16cfcabb725f1bdd8176400c0a4e12b767ffe2f44e3243364653679cac0d9160c5be391533260c5a55f5363c8152fe6a33c4b2f3f45b887f6482fb8b6425d8accdd8b25ec32876e5cc3aa985267b0962fd57c2be65f2d17a020aee4a878b0cec54&a=w%3D850%26h%3D406%26fm%3Dwebp%26q%3D75&cd=2023-07-17T18%3A54%3A02.234Z" %}
设置策略
{% endembed %}

用户需要[自行注册](admin-password-reset.md#self-enroll-in-password-reset)或[自动注册](admin-password-reset.md#automatic-enrollment)账户恢复，然后才能重置其主密码。

### 自动注册 <a href="#automatic-enrollment" id="automatic-enrollment"></a>

启用自动注册策略选项将在新用户[加入组织的邀请被接受后](user-management.md#accept)自动注册新用户的账户恢复功能。并且会阻止他们[撤销](admin-password-reset.md#withdraw-enrollment)账户恢复。

已经在组织中的用户不会被注册账户恢复，需要他们[自行注册](admin-password-reset.md#self-enroll-in-password-reset)。

{% hint style="success" %}
如果您为组织成员使用自动注册账户恢复，我们**强烈建议您通知他们这一功能**。很多 Bitwarden 组织用户在他们的个人密码库中存储私人凭据，应该让他们知道账户恢复将允许管理员访问他们的个人密码库。
{% endhint %}

### 自行注册 <a href="#self-enroll-in-password-reset" id="self-enroll-in-password-reset"></a>

要注册账户恢复，选择您的组织旁边的 **≡选项**菜单，然后选择**注册账户恢复**：

{% embed url="https://bitwarden.com/_gatsby/image/c207d1dabebb7fc1a7e094f2701270dd/3d0b477d31b2a297e2f1e557755b34d0/Screen%20Shot%202023-07-17%20at%203.10.02%20PM.webp?eu=8e8f56e7e7c1ff865c69f58a6872343bb4395ef8fe0233816c31e4fc4eaf99802df64c0421977bb32d3c58d982e246b232c178681aed82dbc0bc4df1e267ac59558b5abf35b02102582892f9e4a750406fce195aa887990af6692682ecbbb3754a531979fb7cbc81eaaa3d37b4d52660b8b4ac762186eb3bea0d410d964926a927a5c39a654fad8de55bacf8b0fc4dd29ba573540681f2632a2a0b1847e97cfbf0b30d123c55470763ceeb29b614dfcf626b033c580b02f46e3fd65cfd3832c3e4f2a70e8f722ee8fecd37248f91ab85ee1bfd2c69849c65fcd765156d55f357c2be7bf5d17906099c2bfdfa1df66c062b41820289264fb94541cc59d3&a=w%3D850%26h%3D385%26fm%3Dwebp%26q%3D75&cd=2023-07-17T19%3A10%3A40.283Z" %}
注册账户恢复
{% endembed %}

如果您愿意，您可以在多个组织中注册账户恢复。

### 撤销注册 <a href="#withdraw-enrollment" id="withdraw-enrollment"></a>

注册后，您可以从用于注册的同一下拉菜单中**撤销**账户恢复：

{% embed url="https://bitwarden.com/_gatsby/image/3b093aec539fbba6ae8a8233a28dae9d/3d0b477d31b2a297e2f1e557755b34d0/Screen%20Shot%202023-07-17%20at%203.08.16%20PM.webp?eu=dfdd05b3e1cef5820739a0d73926326de73c51a9f9053fd66b32e3fc1daacf8270a74d50269d7bb57e6c0f8881e641bf32c771654bec818fc1bb1efce235a30157850fea31bb72515b7380baf0b60c5a779f4709f6d68b16f0292485a6f0e2345a4e427eec65bfc3b2fa733eb1d5276fadb1b92a12a0aa7fe64e0f00c25833a960f8faa0305c9fcdb500bde7edaf0e9b9eb27f0f118ffa667724454c59b87befa2e30376312f405a6798b03b9423c3e36273027b011b6cf56738d348fb6b2cc2e394f019b67965e1a0d73076e9a3d39ead44fb&a=w%3D850%26h%3D385%26fm%3Dwebp%26q%3D75&cd=2023-07-17T19%3A09%3A44.252Z" %}
撤销账户恢复
{% endembed %}

已启用[自动注册](admin-password-reset.md#automatic-enrollment)策略选项的组织中的用户将**不允许撤销**账户恢复。此外，手动更改您的主密码或[轮换您的加密密钥](../security/account-encryption-key.md)**不会**使您撤销账户恢复。

## 恢复账户 <a href="#recover-an-account" id="recover-an-account"></a>

{% hint style="info" %}
您必须是[所有者、管理员或允许的自定义用户](admin-password-reset.md#permissions)才能重置主密码。检查本文的[权限](admin-password-reset.md#permissions)章节以了解您可以重置谁的主密码。
{% endhint %}

要重置企业组织成员的主密码：

1、在[网页密码库](https://vault.bitwarden.com/)中，打开您的组织。

2、打开**人员**选项卡。

3、对于要重置其主密码的成员，请使用**选项**菜单选择 **🔑恢复账户**：

{% embed url="https://bitwarden.com/_gatsby/image/4a09d118a856674343d68b6f4dc01cc8/4321a705eb4bf9935031580d12f9d1da/Screen%20Shot%202023-07-17%20at%203.04.26%20PM.webp?eu=8edf51e1e4cfaad65b61f6d23b7a646fb66b5fabfe5830816861e4ad4cfec88424f64b0722932cb47d6f5888d6b246bb32c12d371ae7828cc7ea1ba6e23ca20c50d15cba35e17603022dc0afb8a300406f93480cf2879900a73821d5e5b5be251c021c7ef92bba85e6f17120f0c0252df5effb7f3297e866b3560805885b24b827a5ce8b7701e98cee4ca9bcefff0190dbe032054684873d7b36387659e84ec5dfda770b6548355c34d1fd5dc46392b36a493325565c03f7603c8650ff3d3796e5f8a2098c7a2eb5ae9c2e13d581fbd5b375cf7229a3a025a98038670e0ab112aad32ab3bd67180e8534f89323d27e1b751ed5&a=w%3D850%26h%3D482%26fm%3Dwebp%26q%3D75&cd=2023-07-17T19%3A13%3A08.179Z" %}
恢复账户
{% endembed %}

4、在恢复账户窗口中，为用户创建一个**新密码**。如果您的组织启用了[主密码策略](enterprise-policies.md#master-password)，您将需要创建一个满足实施要求的密码（例如，最少 8 个字符，包含数字）：

{% embed url="https://bitwarden.com/_gatsby/image/a071f5a2a1b65a3bcdc378590f53bb9e/d1f837187dc06b8064eefc030e215457/pwreset-newpw.webp?eu=d68e04e1e5cef5835c3da9d23e213668e26a02adf90063d56c32e1a946aacf8324a7195d719c7bb47f3d52dad5e945ba3297716048bb83de95b411a7b866ae5b56d60cbb6deb34431168cee1afac5b143f935946f2c79e59e02e2790a6ade9255d4f1b69f629fedbedff3d39f7843030e2f7dd7530cbc3029c48580aaf720ba633bfcda53701eb9fb11eeceee6ae0d9e95b67c0345daf03470711f1e58ef2fb8a5b65123387c5f1b728cfa1b92258be8695b2164401f5da0&a=w%3D510%26h%3D502%26fm%3Dwebp%26q%3D75&cd=2022-01-19T18%3A15%3A25.579Z" %}
创建一个新的密码
{% endembed %}

复制新的主密码并使用安全的通讯方式联系用户，例如使用 [Bitwarden Send](../bitwarden-send/create-a-send.md)。

5、选择**保存**以执行账户恢复。这样做会将用户从当前会话中注销。某些客户端应用程序（比如移动应用程序）上的活动会话可能会保持活动长达一小时。

### 恢复后 <a href="#after-a-recovery" id="after-a-recovery"></a>

当您的主密码被重置时，您将收到一封来自 Bitwarden 的电子邮件，通知您这一点。收到此电子邮件后，请联系您的组织管理员，通过诸如 [Bitwarden Send](../bitwarden-send/create-a-send.md) 等安全渠道获取您的新主密码。

当您使用新的主密码重新获得对密码库的访问权限后，系统将提示您再次更新主密码：

{% embed url="https://bitwarden.com/help/images/organizations/pwreset-temporary.png" %}
更新您的主密码
{% endembed %}

因为主密码应该是**强大**且**易记**的，并且**只有您自己**知道，所以重置后您会被要求更新您的主密码。
