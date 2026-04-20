# =管理组织中的订阅席位

{% hint style="success" %}
对应的[官方文档地址](https://bitwarden.com/help/manage-subscription-seats-in-your-organization/)
{% endhint %}

用户席位是 Bitwarden 组织中单个用户的计费许可。当用户受邀加入您的组织时，他们将占用一个用户席位，并根据您的特定方案获得 Bitwarden 功能的访问权限。用户席位的总数决定了有多少用户可以加入您的组织。因此，用户席位并非永久绑定于特定成员。

{% hint style="info" %}
本文仅讨论邀请用户和管理您的订阅席位数量的可用方法之一：

* 所有组织都可以[手动邀请用户](../admin-console/manage-members/user-management.md)和更新[席位数量](manage-subscription-seats-in-your-organization.md)。
* 团队版和企业版组织可以使用 [SCIM](../admin-console/manage-members/scim/about-scim.md)。
* 团队版和企业版组织可以 [Directory Connector](../admin-console/manage-members/directory-connector/about-directory-connector.md)。
* 企业版组织可以[使用 JIT](../admin-console/login-with-sso/jit-provisioning.md)。
{% endhint %}

## 用户席位计费 <a href="#user-seat-billing" id="user-seat-billing"></a>



### 新用户席位计费 <a href="#billing-for-new-user-seats" id="billing-for-new-user-seats"></a>



### 已移除用户席位的信用额度 <a href="#credit-for-removed-user-seats" id="credit-for-removed-user-seats"></a>

### 自托管计费 <a href="#self-hosted-billing" id="self-hosted-billing"></a>

自托管组织拥有的席位数量始终与其对应的云端组织保持一致。这意味着自托管组织不会自动扩展用户。相反，您必须使用云管理控制台来管理您的席位数量。

要快速反映在云端管理控制台中对席位数量所做的更改，您可以设置[计费同步](../self-hosting/licensing-on-premise.md#zi-dong-tong-bu)。这将无需[重新上传许可证](../self-hosting/licensing-on-premise.md#shou-dong-geng-xin)。

## 手动添加或移除席位 <a href="#manually-add-or-remove-seats" id="manually-add-or-remove-seats"></a>

要为您的组织手动添加或移除席位：

1、登录到 Bitwarden 网页 App，然后使用产品切换器打开管理员控制台：

<div align="left" data-with-frame="true"><figure><img src="https://bitwarden.com/assets/2uxBDdQa6lu0IgIEfcwMPP/e3de3361749b6496155e25edcfdcf08b/2024-12-02_11-19-56.png?w=1013&#x26;fm=avif" alt=""><figcaption><p>产品切换器</p></figcaption></figure></div>

2、前往**计费** → **订阅**。

3、在**订阅席位**中输入您所需的用户席位总数：

<figure><img src="https://bitwarden.com/assets/6IiAvwCX2KbCTUAbAnY4yV/81614bb5a44c64cdc387ba9cee5663eb/Set_Subscription_seats.png?w=1400&#x26;fm=avif" alt=""><figcaption></figcaption></figure>

4、选择**保存**。

{% hint style="info" %}
如果勾选了**限制订阅**，则**订阅席位**中的数量必须等于或低于您的席位限制。如需您需要添加更多用户席位，请提高**席位限制**。
{% endhint %}

## 设置席位限制 <a href="#set-a-seat-limit" id="set-a-seat-limit"></a>

您可以选择通过设置可添加您的组织的用户席位的上限来控制订阅成本。达到指定的限制后，除非提高该限制，否则将无法邀请新的用户。

要为您的组织可自动扩展到的席位数量设置限制：

1、登录到 Bitwarden 网页 App，然后使用产品切换器打开管理员控制台：

<div align="left" data-with-frame="true"><figure><img src="https://bitwarden.com/assets/2uxBDdQa6lu0IgIEfcwMPP/e3de3361749b6496155e25edcfdcf08b/2024-12-02_11-19-56.png?w=1013&#x26;fm=avif" alt=""><figcaption></figcaption></figure></div>

2、前往**计费** → **订阅**。

3、检查限制订阅（可选）。

4、在**席位限制（可选）**&#x4E2D;输入您所需的最大用户席位数量：

<div align="left" data-with-frame="true"><figure><img src="https://bitwarden.com/assets/5DBnJW1y9welOF6hrDKrrh/06cade0656921a06d5bc43d3b9d26a62/Set_Seat_limit.png?w=1400&#x26;fm=avif" alt=""><figcaption><p>设置席位限制</p></figcaption></figure></div>

5、选择**保存**。
