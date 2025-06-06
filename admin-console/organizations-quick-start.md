# 组织快速入门

{% hint style="success" %}
对应的[官方文档地址](https://bitwarden.com/help/article/getting-started-organizations/)
{% endhint %}

像 Bitwarden 这样的密码管理器使您可以轻松地在您的所有设备上存储和访问唯一且安全的密码，从而使您的在线账户比以往任何时候都更加安全！使用 Bitwarden，你将不需要危险地重复使用简单的密码，也不必以电子表格、文档或便笺等未加密的格式暴露密码。

**Bitwarden 组织**为您的家庭、团队或企业的密码管理增加了一层协作和共享，使您可以安全地共享常见信息，例如办公室 wifi 密码、在线凭据或共享的公司信用卡。组织拥有的凭据的安全共享既**安全**又**简单**。

本文将帮助您开始使用**免费的 2 人组织**，这样您就可以立即体验安全的共享。

## 什么是组织？ <a href="#what-are-organizations" id="what-are-organizations"></a>

Bitwarden 组织将用户和密码库项目关联在一起，以[安全地共享](../organizations/sharing.md)组织拥有的登录、笔记、支付卡和身份。组织可以是一个家庭、团队、公司或需要安全共享数据的任何一群人。组织具有独立的密码库，[管理员](user-management/member-roles-and-permissions.md)可以在其中管理组织的项目、用户和设置：

{% embed url="https://images.ctfassets.net/7rncvj1f8mw7/1pgKWi4j94eDV9ehpEeUvw/b8658ed64c38494c4ce5643a38614d98/org-vault-admin.png?fm=webp&h=264&q=50&w=766" %}
组织密码库
{% endembed %}

### 组织与高级会员比较 <a href="#comparing-organizations-with-premium" id="comparing-organizations-with-premium"></a>

关键的是要知道，**组织可以启用组织到用户之间的安全共享**。[高级个人计划](../plans-and-pricing/password-manager/about-bitwarden-plans.md#premium-individual)可解锁高级密码安全和管理功能，包括高级 2FA 选项、Bitwarden 验证器 (TOTP)、加密的文件附件等，但高级个人**不包含安全数据共享功能**。

付费组织（家庭、团队或企业）自动为组织中已注册的**每一个**用户提供这些高级功能（高级 2FA 选项、Bitwarden 验证器 (TOTP) 等）。

## 设置 Bitwarden 账户 <a href="#setup-bitwarden-accounts" id="setup-bitwarden-accounts"></a>

免费的 Bitwarden 组织允许 2 位用户安全地共享组织拥有的凭证。您可以使用免费的组织与朋友或伙伴共享，或者在[升级到不同的计划](../plans-and-pricing/password-manager/about-bitwarden-plans.md)之前测试组织。

Bitwarden 在许多设备上提供了应用程序，包括浏览器扩展、移动应用程序、桌面应用程序和 CLI，但在本指南中，我们将重点介绍[网页密码库](../getting-started/getting-started-webvault.md)。对于管理你的组织，**网页密码库提供了最丰富的 Bitwarden 体验**。

### 注册 Bitwarden <a href="#sign-up-for-bitwarden" id="sign-up-for-bitwarden"></a>

[创建一个 Bitwarden 帐户](https://vault.bitwarden.com/#/register)，并确保您挑选了一个强大而难忘的[主密码](../account/log-in-and-unlock/your-master-password.md)。我们甚至建议您写下您的主密码，并将其存储在安全的地方。

{% hint style="success" %}
**不要忘记您的主密码！**&#x42;itwarden 是一种零知识的解决方案，这意味着 Bitwarden 团队以及 Bitwarden 系统本身对你的主密码一无所知，也没有办法找回或重置你的主密码。
{% endhint %}

创建帐户后，登录到[网页密码库](../getting-started/getting-started-webvault.md)并验证帐户的电子邮件地址以解锁对所有功能的访问权限：

![发送验证电子邮件](../.gitbook/assets/2-verify-email.png)

### 再次注册 Bitwarden <a href="#sign-up-for-bitwarden-again" id="sign-up-for-bitwarden-again"></a>

为了使用免费的 2 人组织进行安全共享，您需要拥有 2 个 Bitwarden 帐户。设置了第一个 Bitwarden 帐户后，请按照相同的步骤（或帮助您的朋友或伴侣操作）来设置另一个帐户。

{% hint style="success" %}
Bitwarden 组织具有深层次的[用户级别访问控制](user-management/member-roles-and-permissions.md)。无论你用哪个用户来[设置你的组织](organizations-quick-start.md#setup-your-organization)，其都将成为**所有者**。
{% endhint %}

## 设置您的组织 <a href="#setup-your-organization" id="setup-your-organization"></a>

要设置您的组织：

1. 在您的网页密码库中，选择 ✚**新建组织**按钮。
2. 输入**组织名称**和**帐单电子邮件**，我们可以通过此地址与您联系。在本指南中，我们将设置一个免费的组织，所以你将不会被收取任何费用。
3. **选择您的计划**。Bitwarden 提供适合任何需求的组织，但在这种情况下，请选择**免费**。
4. 向下滚动并选择**提交**以完成组织的创建。

### 了解您的组织 <a href="#get-to-know-your-organization" id="get-to-know-your-organization"></a>

创建完成后，您将进入组织密码库，这是所有内容共享和组织管理的中心。作为[组织所有者](user-management/member-roles-and-permissions.md)，您将能够查看您的**密码库**，管理用户和[集合](organizations-quick-start.md#get-to-know-collections)，使用一些 Bitwarden **工具**以及配置组织的**设置**：

{% embed url="https://bitwarden.com/_gatsby/image/bade21306371e375ec1a70ceda727886/72add32be5d81e5c969864e380e0e5b8/Screen%20Shot%202023-02-07%20at%2010.25.46%20AM.webp?eu=dadf59e4e79ca88f096ea18b6a24653fe96a5faaff5763826862b7af4bf99c8577a21b0724947fe279385dd881e717ee35c27d614fec86d2c2b81ef6bf63a30d058b59e731e526520529cea6f4b1460662d90501fcd29f5de0732190b3e2f4334c145f35f62ffc9eebeb6b37f6d92e64e2ebe1297a9ae10aa55b1e07ce6112b625c893845643879ce54ef0b4bda1589bc8e0280548dda03676221a4e50bc2feff7e301783928450f369fa847a432d4e369420e4006004798653ad256e66c33dee4fcce0c9d157ae1b6cb346e82c5c1f19004ec7421&a=w%3D850%26h%3D484%26fm%3Dwebp%26q%3D75&cd=2023-02-15T12%3A50%3A04.101Z" %}
免费组织密码库
{% endembed %}

### 了解集合 <a href="#get-to-know-collections" id="get-to-know-collections"></a>

集合是 Bitwarden 组织的重要组成部分；它们代表[属于您的组织](organizations-quick-start.md#shared-items)拥有的密码库项目的逻辑分组。您的组织预设了一个**默认集合**和一个**未分配**标签。对于免费组织，您可以使用**密码库**选项卡创建最多 2 个集合：

{% embed url="https://bitwarden.com/_gatsby/image/91aa7173066e5818c070ace7f7a43668/6041fa748404af9b01abc08f40f7c8bb/Screen%20Shot%202023-02-07%20at%2010.27.56%20AM.webp?eu=dc8b02b7e09cadd25d69f48b6c75683be63e56fdfc5365d83f60e7fc19af9e8477f01b0176c079b57e3d5bded5e017eb36c02d601eecd3d396e84afdbf3dab0c57875bee6fb770535b7380baf0b60c5a779f4709f6d68b16f0292485a6f0e2345a4e427eec65bfc3b2fa733eb1d5276fadb1b92961a1ed1b864d5723816433bb62dceeba687ab695ea00e9e1bffc5ccac8b22f5542d2a06322764b1950e879bba7b60c736a2d470861cdb03b9423c3e36273027b011b6cf56738d348fb6e2cc3e394f019b67b7bffaace2f7580acdffdf35af27d&a=w%3D850%26h%3D452%26fm%3Dwebp%26q%3D75&cd=2023-02-15T12%3A50%3A04.056Z" %}
免费组织 - 创建新的集合
{% endembed %}

{% hint style="success" %}
在很多方面，集合类似于用来组织个人密码库的[文件夹](../your-vault/folders.md)。一个关键的区别是，[属于您的组织](organizations-quick-start.md#shared-items)的项目**必须包括在至少一个集合中**。
{% endhint %}

## 将用户添加到您的组织 <a href="#add-a-user-to-your-organization" id="add-a-user-to-your-organization"></a>

现在您已经熟悉了您的组织，现在是添加您将与之共享的其他组织成员的好时机。为了确保您组织的安全，Bitwarden 应用了一个 3 步流程来加入新成员，[邀请 ](organizations-quick-start.md#invite)→ [接受](organizations-quick-start.md#accept) → [确认](organizations-quick-start.md#confirm)。

### 邀请 <a href="#invite" id="invite"></a>

作为组织所有者，邀请新成员的步骤如下：

1、在您的组织密码库中，打开**成员**选项卡然后选择 ✚**邀请用户**按钮：

{% embed url="https://bitwarden.com/_gatsby/image/7be2d0c299383eb7c658b0f6eeaf785e/b8257e323ee5953820291453e1197a99/Screen%20Shot%202023-02-07%20at%2010.29.20%20AM.webp?eu=d98d55efe2c8f88e0f6fa1d06821663ae03d52fefe5737d13537e3fb1cfb998772a11804769d2be32f6c0fd7d7e516b836c22d3419ea86ddc0e81bf0be31af5e55800ebc32e67400047ac0aae1a053163ec21e0bf7d7cf5aa53974d3b0e0e2741b051823a978e983e5fa6735b3812834ecb2a0266ccbab2ab4170b54cc1a7ba420ffd09d3901f197ed4eb8b3adb75a89cab66e44159fb02b7c2208005faf73e8e3e805273174075c2ac9de229d0392e97d693f50265c72ff6e53b90a9c2c49dcedfaa75cda7f72e0ac98677580cbffd4be1aad2e74e5ce22aed36f290958ae13b2df28b587315861e272a5d123b00307365d821e942427b6691be30684ff459a36fe6e49474cdebc4406&a=w%3D850%26h%3D325%26fm%3Dwebp%26q%3D75&cd=2023-02-15T12%3A50%3A04.064Z" %}
免费组织 - 邀请成员
{% endembed %}

2、在**角色**选项卡中，输入第二个成员的**电子邮件**，该电子邮件应与他们[注册 Bitwarden](organizations-quick-start.md#sign-up-for-bitwarden-again) 的电子邮件相匹配。然后，选择一个[成员角色](user-management/member-roles-and-permissions.md#member-roles)。

3、在**集合**选项卡中，选择允许该用户可以访问的集合，以及授予对每个集合的[权限](user-management/member-roles-and-permissions.md#permissions)级别。

4、选择**保存**将邀请发送到指定的电子邮件地址。

发送邀请后，通知您的新成员并帮助他们[接受邀请](organizations-quick-start.md#accept)。

### 接受 <a href="#accept" id="accept"></a>

作为新的被邀请的成员，打开您的电子邮件收件箱并查找来自 Bitwarden 的邀请您加入组织的电子邮件。单击电子邮件中的链接将打开 Bitwarden 网页客户端邀请窗口：

{% embed url="https://bitwarden.com/_gatsby/image/958ce51e71025d451256ade85e478bd5/106d26c390438e4a0c9b999390e67465/Screen%20Shot%202023-04-28%20at%2010.40.35%20AM.webp?eu=8dd856e2e49af48f5e3da0816923316db66950f8f85437d93b67b2f91caa9b8120a14a5d21962bb22a6e0fddd5e416b23392716411ebd1dfc4ed1af4b93dad095bd75cb866e5710e592cc4fee2fd0e443d944b0ca9829a01f66b72d4e6b6bf774b01152ba92bbad7bfa83767b1d52e61e8e4f32f3794a120a4561e17c1076ea539eac78b7000bd8ae64eaca5bbed4ad3c2b269184799ad66642d4d4950b06abcbab46e3b4149031c7daff019a333cced5f7b3e77191744e86e39d854ae6e3695b0aef458d92e7eb2fe9c317684c7a983eb19af7f20e09a73b6e168385b58f27ccee424b3bd66060c8237fa9151b00b6a6404ed1d893a24d9265c8968f59c59d376ab&a=w%3D601%26h%3D594%26fm%3Dwebp%26q%3D75&cd=2023-04-28T14%3A41%3A41.708Z" %}
Bitwarden 邀请
{% endembed %}

由于您已经[注册了 Bitwarden](organizations-quick-start.md#sign-up-for-bitwarden-again)，请选择**登录**。完全登录到您的密码库将接受邀请。

{% hint style="info" %}
邀请将在 5 天后到期。确保您在该窗口内接受邀请，否则组织所有者将不得不[重新邀请您](organizations-quick-start.md#invite)。
{% endhint %}

### 确认 <a href="#confirm" id="confirm"></a>

确认已接受的组织以完成这个循环：

1、登录到您的网页密码库并打开您的组织。

2、打开**成员**选项卡。

3、选中任何`已接受`的用户并使用 **≡选项**菜单 **✔︎确认所选**：

{% embed url="https://bitwarden.com/_gatsby/image/65a755f8719ee31b279e75ab83d281c2/e3c97f431c846f897b92cb064dca9c1e/Screen%20Shot%202023-02-07%20at%2010.31.31%20AM.webp?eu=8adf52efe5ccfa810b3ea1833a21313be33e04adf80035d76865e2a648a196d226f24f0429902fb1243d0fdd86b342ec66c229374fbad28e92bc1ff6e266ac0d538550b623f730445b34dba7eda451102bd8491cf7d28b4bf62931cabbe6f36f1e124278ee20b9d7e4f47263af867a509ed4d7713aa0c80fa170392ea27203f932ecdac1604dbccdb31feee5effa0ac9cfb12453148da23026741a1d5be429bbf4b55675264a1319609bf137a439c9f2531e61215d4203f57a3ad73aaa285ec2e4e5a25cc7797a8ed9b42f30d894&a=w%3D850%26h%3D446%26fm%3Dwebp%26q%3D75&cd=2023-02-15T12%3A50%3A03.982Z" %}
免费组织 - 确认成员
{% endembed %}

4、验证您屏幕上显示的[指纹短语](../security/account-fingerprint-phrase.md)是否与您的新成员的匹配，指纹短语可以在**设置** → **我的帐户**中找到。

每一个指纹短语对于其帐户都是唯一的，它是确保安全添加用户的最后一层监督。如果它们匹配，请选择**提交**。

## 了解您的密码库 <a href="#get-to-know-your-vault" id="get-to-know-your-vault"></a>

Bitwarden组织的神奇之处在于，属于你的项目和[属于组织](organizations-quick-start.md#shared-items)的项目可以在**密码库**视图中并排访问。您可以在个人项目（**我的密码库**）和组织项目（**我的组织**）之间进行筛选：

{% embed url="https://bitwarden.com/_gatsby/image/c456aacff85947688caa11633e92c7ed/1f661096264ec90b0631567c79d0f67d/Screen%20Shot%202022-05-16%20at%209.46.24%20AM.webp?eu=8b8f59e6b7c0a98f5a69a0d568703668b26e55a9aa043fd36932b5a849aacfd271f0100075c07eb77e6c098cdbe94bbf31c47a671eef838bc5be19fdb932aa09518453e832e62202567990f7e4f55541629e5e1ce1c0c217bc342f85b2e6f46e4a144a7aeb39edc5afb76b31f49c2870b4e5e0746494a325a7154150bf1a35a03cb2f9a553549aa7b21f8c8f99cf729eebf82c5145dffa3570754a4b5fe42dbdadbb05223c2e155f339bad5fc734c3e4341c7e400d1d56a23955b30da4285ec1e4f9a340d97f66e0aea66034e9cab084eb04ae2e1996b239e9dc6c&a=w%3D784%26h%3D500%26fm%3Dwebp%26q%3D75&cd=2022-12-09T17%3A24%3A47.936Z" %}
已启用的组织的密码库
{% endembed %}

### 从组织共享的项目 <a href="#items-shared-from-an-organization" id="items-shared-from-an-organization"></a>

您可能还没有[从组织共享的项目](organizations-quick-start.md#items-shared-from-an-organization)，但是当您共享项目时，它会显示在您的密码库中，并带有一个**已共享**图标：

已共享的项目归组织**所有**。这意味着任何有权限的人都可以更改或删除该项目，删除该项目也会将其从您的密码库中移除。

## 移动项目到组织 <a href="#move-an-item-to-the-organization" id="move-an-item-to-the-organization"></a>

安全共享之路的最后一步是创建一个项目并将其移动到组织以便共享。现有的[密码库项目](../your-vault/vault-items.md)可以在创建后被移动到组织，但在本指南中，我们将重点放在如何从您的个人密码库创建一个**新的**登录：

1. 在 **🔒我的密码库**页面上，选择 ✚**添加项目**按钮。
2. 为您的新登录项填写所有相关信息（例如用户名和密码）。该项目可以是您希望自己和其他组织用户都可以访问的任何内容，例如家庭流媒体帐户。
3. 在添加项目面板底部的**所有权**部分，勾选您的组织以指定用于共享的项目。
4. 选择一个或多个用于存放此项目的**集合**。两人组织的用户通常设置为两人对所有集合的访问权限。在更大或更复杂的组织中，您将项目存放到哪个集合将决定谁可以访问它。
5. 选择**保存**按钮完成组织所有的项目的创建。

您和组织的其他用户都可以访问这个新的项目！只要两个用户都可以访问它所在的集合，它就会与其他个人密码库项目一起出现在组织密码库以及**我的密码库**视图中。

## 恭喜！ <a href="#congratulations" id="congratulations"></a>

您已经设置了新的 Bitwarden 帐户、创建了一个组织、了解了一些有关您的密码库的知识、并共享了一个项目！干得好！如果您想升级到付费组织以解锁[许多附加功能](../plans-and-pricing/password-manager/about-bitwarden-plans.md)，请导航到您的组织**设置** → **订阅**视图，然后选择**升级计划**按钮：

{% embed url="https://bitwarden.com/help/images/plans-and-pricing/upgrade-org.png" %}
升级您的组织
{% endembed %}
