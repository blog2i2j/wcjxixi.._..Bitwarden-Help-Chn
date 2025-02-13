# 文件夹

{% hint style="success" %}
对应的[官方文档地址](https://bitwarden.com/help/article/folders/)
{% endhint %}

文件夹是用于通过收集登录、支付卡、身份和安全笔记来组织您的个人密码库的结构。使用文件夹是使所有密码库项目易于查找的比较好的方法。可以将任何密码库项目（包括[组织已与您共享的项目](../organizations/sharing.md)）添加到文件夹中。

{% hint style="success" %}
当从筛选器菜单中选择 **☷所有密码库**时，添加到某个文件夹的项目仍会出现在您的密码库中，删除文件夹并**不会**删除该文件夹中的项目。
{% endhint %}

## 创建文件夹 <a href="#create-a-folder" id="create-a-folder"></a>

可以从任何 Bitwarden 客户端 App 来创建、重命名和删除文件夹：

{% tabs %}
{% tab title="网页密码库" %}
要创建文件夹，请从下拉菜单选择 ✚**新增**按钮然后选择**文件夹**：

{% embed url="https://res.cloudinary.com/bw-com/image/upload/f_auto/v1/ctf/7rncvj1f8mw7/3BvTWidqL4xWQvFqBSiJIR/d68bc851d44df1b571eed16366159e0c/2024-12-02_13-50-55.png?_a=DAJCwlWIZAAB" %}
新增文件夹
{% endembed %}

创建文件夹后，您可以随时通过选择此文件夹然后单击 :pencil2:**铅笔**图标来重命名或删除文件夹：

{% embed url="https://res.cloudinary.com/bw-com/image/upload/f_auto/v1/ctf/7rncvj1f8mw7/1aG4313JkmkBvot45gZvEr/a7dc45d314407131948216acc2b2444d/2024-12-02_16-15-07.png?_a=DAJCwlWIZAAB" %}
编辑或删除文件夹
{% endembed %}
{% endtab %}

{% tab title="浏览器扩展" %}
要创建文件夹，请从下拉菜单选择 ✚**新增**按钮然后选择**文件夹**：

{% embed url="https://res.cloudinary.com/bw-com/image/upload/f_auto/v1/ctf/7rncvj1f8mw7/1aPQBd9bT7uUf20Y1fZwSB/506e7010284c1e0d83b75204bac22eaa/2024-12-02_16-13-10.png?_a=DAJCwlWIZAAB" %}
浏览器扩展新增文件夹
{% endembed %}

创建文件夹后，可以随时从**设置** → **密码库** → **文件夹**菜单中重命名或删除文件夹。
{% endtab %}

{% tab title="桌面端" %}
要创建文件夹，请从文件夹列表中选择 ✚**添加**图标：

{% embed url="https://res.cloudinary.com/bw-com/image/upload/f_auto/v1/ctf/7rncvj1f8mw7/5aN4a0qkKkJDJSVAzTy3Ix/bb59a0df1b835ac3e062a815c6e1f33a/Screen_Shot_2022-05-18_at_3.58.09_PM.png?_a=DAJCwlWIZAAB" %}
添加文件夹
{% endembed %}

创建文件夹后，您可以随时通过悬停在 :pencil2:**铅笔**图标上来**重命名或删除**文件夹：

{% embed url="https://res.cloudinary.com/bw-com/image/upload/f_auto/v1/ctf/7rncvj1f8mw7/6t2aoywIMdBPMuJktnhEqA/3f22c5b555deb62a0f0922111dd306d2/Screen_Shot_2022-05-18_at_3.58.52_PM.png?_a=DAJCwlWIZAAB" %}
编辑或删除文件夹
{% endembed %}
{% endtab %}

{% tab title="移动端" %}
要创建文件夹，请点击 **⚙️设置**菜单，点击**密码库**选项，然后点击**文件夹**选项。点击 ✚**添加**图标以添加文件夹。创建后，您可以从同一菜单中通过点击文件夹来重命名文件夹，或使用 **≡**&#x83DC;单来删除文件夹：

{% embed url="https://res.cloudinary.com/bw-com/image/upload/f_auto/v1/ctf/7rncvj1f8mw7/6IwzXSJHGmSeU7oIy4z8kZ/95620b58758e50fa0e8e22a65f2bfa15/2025-01-21_15-26-07.png?_a=DAJCwlWIZAAB" %}
移动端上的文件夹
{% endembed %}
{% endtab %}

{% tab title="CLI" %}
要创建文件夹，请使用命令：

```
bw create folder <foldername>
```

您可以使用 `bw edit <folderId>` 编辑现有文件夹，使用 `bw delete folder <folderId>` 删除文件夹。更多信息，请参阅 Bitwarden [CLI 文档](../password-manager/developer-tools/password-manager-cli.md)。
{% endtab %}
{% endtabs %}

删除文件夹不会删除其中包含的任何密码库项目，也不会删除嵌套在其中的其他文件夹或其内容。

{% hint style="info" %}
如果您是某个组织的成员，在**筛选器**菜单中，集合将显示在文件夹的下方。

文件夹和集合之间有相似之处。**文件夹用于组织个人密码库的项目**（可以包含[已共享的项目](../organizations/sharing.md)），并且对您来说是独一无二的，而集合则用于在组织成员之间共享项目。
{% endhint %}

### 嵌套文件夹 <a href="#nested-folders" id="nested-folders"></a>

文件夹可以「嵌套」，以便在密码库中合理地组织它们。嵌套文件夹的深度没有限制，但创建太多层次可能会破坏密码库的界面。

{% hint style="info" %}
在「父」文件夹中进行检索不会将嵌套在其中的文件夹中的项目作为潜在检索结果包括在内。有关更多信息，请参阅[检索密码库](search-your-vault.md)。
{% endhint %}

{% embed url="https://res.cloudinary.com/bw-com/image/upload/f_auto/v1/ctf/7rncvj1f8mw7/5blNMg0hJ9XW3Ts2qPRzF5/7a2bdfb7672c04a1a1fbae1068b8b422/2024-12-02_16-18-48.png?_a=DAJCwlWIZAAB" %}
嵌套文件夹
{% endembed %}

要创建一个嵌套文件夹，给新的文件夹起一个名称，这个名称需包括「父」文件夹，后面使用一个正斜线 (`/`) 分隔符，例如 `Personal/Email`。

如果没有相应的「父」文件夹名称，则该文件夹不会被嵌套，其标题将完整显示。

## 移动项目到文件夹 <a href="#move-items-to-a-folder" id="move-items-to-a-folder"></a>

在密码库中创建文件夹后，可以通过以下几种方式将项目移动到其中：

{% tabs %}
{% tab title="网页密码库" %}
对于网页密码库，可以任选其一：

* 导航到**添加**项目或**编辑**项目界面，从**文件夹**下拉列表中选择您的新文件夹并**保存**您的项目：

{% embed url="https://res.cloudinary.com/bw-com/image/upload/f_auto/v1/ctf/7rncvj1f8mw7/4VfciDIbEZZFAG1AXbRf3S/275100f866612da15b4714adea8f1944/2024-12-02_16-20-15.png?_a=DAJCwlWIZAAB" %}
移动项目到文件夹
{% endembed %}

* 导航到**密码库**视图，选择要移动的项目，然后使用最上面的 **≡**&#x9009;项菜单选择 **💾添加到文件夹**按钮。在移动所选按对话框中，选择要将项目移动到的文件夹：

{% embed url="https://res.cloudinary.com/bw-com/image/upload/f_auto/v1/ctf/7rncvj1f8mw7/7zQPzdrcVIbPeX5E8LqTq/ce8e8bf7188626093a675eb844d5002a/2024-12-02_16-22-24.png?_a=DAJCwlWIZAAB" %}
移动项目到文件夹
{% endembed %}
{% endtab %}

{% tab title="浏览器扩展" %}
打开要移动的密码库项目，选择**编辑**按钮，使用**文件夹**下拉菜单选择文件夹，完成后选择**保存**：

{% embed url="https://res.cloudinary.com/bw-com/image/upload/f_auto/v1/ctf/7rncvj1f8mw7/6b8EOCtuuHmulnNQNJmWWk/f24c97777972b15ee5000e575f2b242c/2024-10-29_11-48-18.png?_a=DAJCwlWIZAAB" %}
移动项目到文件夹
{% endembed %}
{% endtab %}

{% tab title="桌面端" %}
打开要移动的密码库项目，选择**文件夹**下拉列表，然后选择要将项目移动到的文件夹：

{% embed url="https://res.cloudinary.com/bw-com/image/upload/f_auto/v1/ctf/7rncvj1f8mw7/63jzyM75IRzhAbw5nNzMHx/29b8ed60015ebf272ce62cb0034ac68e/Screen_Shot_2022-05-18_at_4.00.25_PM.png?_a=DAJCwlWIZAAB" %}
移动项目到文件夹
{% endembed %}
{% endtab %}

{% tab title="移动端" %}
打开要移动的密码库项目，点击**文件夹**下拉菜单，然后选择要将项目移动到的文件夹：

{% embed url="https://res.cloudinary.com/bw-com/image/upload/f_auto/v1/ctf/7rncvj1f8mw7/169hAtd0PhW3BcYlSPy6vn/2618596e36941b06dabcb766327b664b/2025-01-22_09-44-03.png?_a=DAJCwlWIZAAB" %}
移动项目到文件夹
{% endembed %}
{% endtab %}

{% tab title="CLI" %}
使用 `bw edit` 命令来操作密码库项目 JSON 对象的 `folderId` 属性，如下例所示：

```batch
bw get item 7ac9cae8-5067-4faf-b6ab-acfd00e2c328 | jq '.folderId="3d9cecac-71a2-4637-9341-acf000eedf04"' | bw encode | bw edit item 7ac9cae8-5067-4faf-b6ab-acfd00e2c328
```

{% hint style="success" %}
使用 `edit` 功能需要：

* 使用带有您要编辑的项目的确切 `id` 的 `get` 命令。
* 知道要将其移动到的文件夹的确切 `folderId`。
* 使用 [jq 之类的命令行 JSON 处理器](https://stedolan.github.io/jq/)操作 JSON 对象（特别是 `folderId` 属性）。
* 使用 `encode` 命令对 JSON 对象的更改进行 `encode`。

如果您不熟悉对这些部分的使用，请参阅 Bitwarden [CLI 文档](../password-manager/developer-tools/password-manager-cli.md)。
{% endhint %}
{% endtab %}
{% endtabs %}

{% hint style="success" %}
[组织已与您共享](../organizations/sharing.md)的项目可以添加到您的文件夹中，这样做只会影响该项目在您的个人密码库中的显示方式（即，将项目添加到文件夹不会授予任何人对该文件夹的访问权限，也不会改变它是否在他们的密码库中的某个文件夹中）。
{% endhint %}
