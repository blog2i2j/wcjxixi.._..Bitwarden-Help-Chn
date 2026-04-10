# 停用浏览器的内置密码管理器

{% hint style="success" %}
对应的[官方文档地址](https://bitwarden.com/help/article/disable-browser-autofill/)
{% endhint %}

如果您是 Bitwarden 的新手，很可能您使用的网页浏览器一直在保存和自动填充您的密码。大多数网页浏览器默认启用了这一功能，但专家们普遍认为，[内置的密码管理器比 Bitwarden 这样的专业解决方案要脆弱](https://www.wired.com/2016/08/browser-password-manager-probably-isnt-enough/)。我们建议停用浏览器的内置密码管理器，以提高您的安全性并防止干扰您的 Bitwarden 体验。

{% hint style="info" %}
Bitwarden 浏览器扩展可在托管终端上部署。了解有关[在托管设备上部署 Bitwarden 浏览器扩展](../../../admin-console/deploy-client-apps/deploy-browser-extensions/)的更多信息。
{% endhint %}

## 手动禁用浏览器的内置密码管理器 <a href="#manually-disable-a-browsers-built-in-password-manager" id="manually-disable-a-browsers-built-in-password-manager"></a>

了解如何禁用主流浏览器的内置密码管理器：

{% hint style="success" %}
很多流行的浏览器，包括 Edge、Opera 和 Brave，都使用一个被称为「Chromium」的谷歌 Chrome 框架。如果您正在使用这些浏览器之一，请参考 **Chrome/Chromium** 部分的说明。
{% endhint %}

{% tabs %}
{% tab title="Chrome/Chromium" %}
在 Chrome 浏览器或任何基于 Chromium 的浏览器（如 Edge、Opera、Brave）的地址栏中输入  `chrome://password-manager/settings`（将 `chrome` 替换为浏览器名称（例如 `brave://password-manager/settings`））导航到**密码**页面。对于 Edge 用户，导航到 `edge://wallet/settings`。

在此页面上，切换**提示保存密码**选项和**自动登录**选项开关为关闭状态：

{% embed url="https://res.cloudinary.com/bw-com/image/upload/f_auto/v1/ctf/7rncvj1f8mw7/6bpi4fkyZhnkhW5RBtugDW/d8e2de4536d6a34f092fd9d5975fd04a/chrome-disable-autofill.png?_a=DAJCwlWIZAAB" %}
Chrome 密码选项
{% endembed %}

此页面还将列出被浏览器存储的所有**已保存的密码**：

{% embed url="https://res.cloudinary.com/bw-com/image/upload/f_auto/v1/ctf/7rncvj1f8mw7/4P5alfndwwNgCpTYrSCg61/b3545839a8429f28ee7b6ac66559c3ce/chrome-delete-passwords.png?_a=DAJCwlWIZAAB" %}
Chrme 已保存的密码
{% endembed %}

如果您还没有将这些密码保存到 Bitwarden 中，请[将它们导出](../../import-and-export/import-guides/import-data-from-chrome.md#export-from-chrome)，为将来导入 Bitwarden 做准备。导出后，您应该从浏览器的存储中删除这些密码。
{% endtab %}

{% tab title="Edge" %}
虽然 Edge 浏览器基于 Chromium 内核，但操作步骤略有不同。请导航到 `edge://wallet/settings`。在此页面上，选择 **Microsoft 密码管理器**：

{% embed url="https://bitwarden.com/assets/6tRRYJbZ2xmQZ0ehL2xbvh/4c9c416b6e52c9bd1b3eaf9b75eaaca7/edge-disable-autosave.png?w=1400&fm=avif" %}
Edge 禁用密码
{% endembed %}

然后，将**要求保存密码**和**自动填充密码和通行密钥**的开关设置为**关闭**：

{% embed url="https://bitwarden.com/assets/3minVF9zEGs9SuGDSQ9FAE/4c3e66b91f7905a5f65ff164afbb3e01/edge_disable_all.png?w=1400&fm=avif" %}
切换保存密码
{% endembed %}
{% endtab %}

{% tab title="Firefox" %}
在 Firefox 中，导航到**首选项** → **隐私和安全**，向下滚动并取消勾选**密码**、**付款方式**和**地址及更多**部分中所有预先勾选的选项：

{% embed url="https://bitwarden.com/assets/72yK5CCMKa9pcfCcdvUZqL/95494d5079e32ae509ea62347ccc9ee8/Firefox_settings.png?w=681&fm=avif" %}
Firefox 密码选项
{% endembed %}

{% hint style="success" %}
Bitwarden Password Manager 为高级用户提供各种[报告](../../your-vault/security-tools/vault-health-reports.md)，如「泄露密码」报告和「重复使用的密码」报告，并**为所有用户提供免费的数据泄露报告**。
{% endhint %}

您还可以通过选择**已保存的密码**按钮来查看 Firefox 已经保存了哪些登录信息：

{% embed url="https://bitwarden.com/assets/5UrQ6bGCjV0VdHvy6rzece/a2148eaa8dcaaf4f7158e8d806dcb97b/2025-08-06_16-53-15.png?w=550&fm=avif" %}
Firefox 已保存的登录信息
{% endembed %}

如果您还没有将这些密码保存到 Bitwarden 中，请[将它们导出](../../import-and-export/import-guides/import-data-from-firefox.md)，以便将来导入 Bitwarden。导出后，您应该从 Firefox 中 **🗑️移除**这些密码。
{% endtab %}

{% tab title="Safari" %}
在 Safari 中，从菜单栏打开**设置**，然后导航到**自动填充**选项卡。在这个选项卡上，取消勾选所有预先勾选的选项：

{% embed url="https://images.ctfassets.net/7rncvj1f8mw7/4nuEz911vsIAUegHVL0Zec/7d663935c4f9e65297c14598f1037b72/safari-disable.png?fm=webp&h=460&q=50&w=919" %}
Safari 密码选项
{% endembed %}

您还可以通过导航到**密码**选项卡来了解 Safari 已经保存了哪些密码：

{% embed url="https://images.ctfassets.net/7rncvj1f8mw7/6eZMZC98Grc7sbdHbBfXtK/4c72d19c26e56ad7dfb3267f466bd119/safari-delete.png?fm=webp&h=671&q=50&w=919" %}
Safari 已保存的密码
{% endembed %}

如果您还没有将这些密码保存到 Bitwarden 中，请在 Bitwarden 中为这些密码创建登录项目。所有密码都保存到 Bitwarden 中后，从 Safari 中**移除**这些密码。
{% endtab %}

{% tab title="Vivaldi" %}
在 Vivaldi 中，打开 **⚙️Vivaldi 设置**窗口，然后从左侧导航中选择 **👁‍🗨隐私**。向下滚动到密码部分并取消选中**保存网页密码**选项：

{% embed url="https://res.cloudinary.com/bw-com/image/upload/f_auto/v1/ctf/7rncvj1f8mw7/6nk9FVDeg8XaUz22Xahr8T/ee0f597cc264da5a30853588d541f074/vivaldi-disable.png?_a=DAJCwlWIZAAB" %}
Vivaldi 密码选项
{% endembed %}

您还可以通过选择**显示已保存的密码**按钮来了解 Vivaldi 已经保存了哪些密码：

{% embed url="https://res.cloudinary.com/bw-com/image/upload/f_auto/v1/ctf/7rncvj1f8mw7/1j5qvcTAVsXficByKFewec/fd6f86731a9e15d38e0cbc39f4f64197/vivaldi-delete.png?_a=DAJCwlWIZAAB" %}
Vivaldi 已保存的密码
{% endembed %}

如果您还没有将这些密码保存到 Bitwarden 中，请在 Bitwarden 中为这些密码创建登录项目。所有密码都保存到 Bitwarden 中后，从 Vivaldi 中**移除**这些密码。[了解如何操作](https://help.vivaldi.com/zh-hans/desktop/privacy/password-management/#Deleting_passwords)。
{% endtab %}

{% tab title="Tor" %}
虽然 Tor 与 Firefox 共享同一来源，但 Tor 是独立的，因为它默认不保存您的登录信息。如果您没有手动配置过 Tor 来保存和自动填充登录信息，那么您已经做好了一切准备。

如果您配置过，请在地址栏中输入 `about:preferences#privacy` 导航到**密码**页面，然后向下滚动到登录和密码部分。取消勾选所有您已勾选的选项：

{% embed url="https://res.cloudinary.com/bw-com/image/upload/f_auto/v1/ctf/7rncvj1f8mw7/4FcJnbhCUhDNITJjiy9ciD/d0f83af69188afaf619788c7e60c9a1b/tor-disable.png?_a=DAJCwlWIZAAB" %}
Tor 密码选项
{% endembed %}

您还可以通过选择**已保存的登录...** 按钮来了解 Tor 已经保存了哪些登录信息：

{% embed url="https://res.cloudinary.com/bw-com/image/upload/f_auto/v1/ctf/7rncvj1f8mw7/3NHOIo5RIwTjVecqRPeT5Y/6c1e26dc5385006a498b77c48e1048c2/tor-delete.png?_a=DAJCwlWIZAAB" %}
Tor 已保存的密码
{% endembed %}

如果您还没有将这些密码保存到 Bitwarden 中，请在 Bitwarden 中为这些密码创建登录项目。所有密码都保存到 Bitwarden 中后，从 Tor 中 **🗑️移除**这些密码。
{% endtab %}

{% tab title="DuckDuckGo" %}
在 DuckDuckGo 中，导航至**设置** → **自动填充**。在此页面中，取消选中**用户名和密码**复选框。

{% embed url="https://res.cloudinary.com/bw-com/image/upload/f_auto/v1/ctf/7rncvj1f8mw7/6kAbV4w8EiJX20O9VZOQyl/c6df545c4bc464122b250527b80494d3/Screenshot_2023-11-03_at_11.06.54_AM.png?_a=DAJCwlWIZAAB" %}
禁用 DuckDuckGo 密码管理器
{% endembed %}

您可以通过选择**导出密码**来创建现有数据的备份。创建备份文件后，选择**查看自动填充内容...** 并删除已存储的自动填充数据，以移除之前保存的建议。

在「Password Manager」部分，macOS 用户可以选择使用 Bitwarden。[此处](../../more/more-platforms/duckduckgo-macos-browser-integration.md)了解更多有关 Bitwarden DuckDuckGo macOS 浏览器集成的信息。
{% endtab %}
{% endtabs %}

## 将 Bitwarden 设置为 Chrome 中的默认密码管理器 <a href="#make-bitwarden-your-default-password-manager-in-chrome" id="make-bitwarden-your-default-password-manager-in-chrome"></a>

{% hint style="info" %}
将 **Bitwarden 设置为默认密码管理器**选项仅适用于 Chrome 浏览器扩展。对于其他浏览器，[请手动禁用其内置密码管理器](disable-a-browsers-built-in-password-manager.md#manually-disable-a-browsers-built-in-password-manager)。
{% endhint %}

Chrome 上的 Bitwarden 浏览器扩展有一个内置设置，可以禁用浏览器的默认密码管理器。要使用此设置：

1、导航至 Bitwarden 浏览器扩展中的 **⚙️设置**选项卡，然后选择**自动填充**。

2、点击以启用**将 Bitwarden 设置为您的默认密码管理器**。

{% embed url="https://bitwarden.com/assets/5fyBdu5X6JCLu2UsaqYUO0/abfb44cb460314112805bfd0312c1f8f/2025-10-14_12-44-35.png?w=459&fm=avif" %}
将 Bitwarden 设置为默认密码管理器
{% endembed %}

3、屏幕上将出现一个对话框，选择**允许**以授予 Bitwarden 更改浏览器设置的权限。
