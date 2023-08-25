# 企业版 Bitwarden 功能数据表

{% hint style="success" %}
对应的[官方文档地址](https://bitwarden.com/help/article/enterprise-feature-list/)
{% endhint %}

本文档描述并引用了 Bitwarden 企业组织在几个类别中可用的功能：

### 应用程序范围和易用性 <a href="#application-range-and-ease-of-use" id="application-range-and-ease-of-use"></a>

<table><thead><tr><th width="305.15182672540476">企业版功能</th><th>描述</th></tr></thead><tbody><tr><td>部署选项</td><td>云、私有云，以及自托管。</td></tr><tr><td>Web 应用程序</td><td><a href="https://vault.bitwarden.com">https://vault.bitwarden.com</a> 或您的自托管服务器上的完全加密的云 Web 应用程序。</td></tr><tr><td>移动应用程序（带有移动登录控制）</td><td>适用于 iOS 和 Android，<a href="../getting-started/getting-started-mobile.md">了解更多</a>。</td></tr><tr><td>浏览器扩展</td><td>适用于 Chrome、Firefox、Opera、Edge、Vivaldi、Brave、Tor，以及 Safari。<a href="../getting-started/getting-started-browserext.md">了解更多</a>。</td></tr><tr><td>桌面应用程序</td><td>适用于 Windows、Mac，以及 Linux。<a href="../getting-started/getting-started-desktop.md">了解更多</a>。</td></tr><tr><td>CLI</td><td>功能齐的自文档命令行工具。<a href="../password-manager/developer-tools/password-manager-cli.md">了解更多</a>。</td></tr><tr><td>流线型 UI 设计</td><td>跨应用程序的简单统一的界面，完全易于使用。</td></tr><tr><td>员工免费家庭计划</td><td>所有企业组织成员都可以为新的或现有的个人 Bitwarden 帐户兑换免费的 Bitwarden 家庭计划。<a href="../plans-and-pricing/password-manager/redeem-families-sponsorship.md">了解更多</a>。</td></tr></tbody></table>

### 管理功能和管理能力 <a href="#administrative-features-and-capabilities" id="administrative-features-and-capabilities"></a>

<table><thead><tr><th width="194.57409144628053">企业版功能</th><th>描述</th></tr></thead><tbody><tr><td>简单的用户管理</td><td>直接从网页密码库添加或删除席位以及入职或离职用户。<a href="../organizations/user-management.md">了解更多</a>。</td></tr><tr><td>基于角色的访问控制</td><td>为组织用户分配基于角色的访问权限，包括自定义角色和精细化权限（例如隐藏密码、只读）。<a href="../admin-console/user-management/member-roles-and-permissions.md">了解更多</a>。</td></tr><tr><td>目录同步</td><td>将您的 Bitwarden 组织与您现有的用户目录同步。布建和取消布建用户、群组，以及群组关联。<a href="../directory-connector/about-directory-connector.md">了解更多</a>。</td></tr><tr><td>管理员密码重置</td><td>如果员工丢失或忘记了他们的主密码，指定的管理员可以重置最终用户帐户的主密码。<a href="../admin-console/user-management/account-recovery.md">了解更多</a>。</td></tr><tr><td>企业策略</td><td>为所有用户强制执行安全规则，例如强制使用两步登录。<a href="../organizations/enterprise-policies.md">了解更多</a>。</td></tr><tr><td>临时密码共享和生成</td><td>使用 Bitwarden Send 创建和共享临时数据。<a href="../bitwarden-send/about-send.md">了解更多</a>。</td></tr></tbody></table>

### 报告 <a href="#reporting" id="reporting"></a>

<table><thead><tr><th width="179.2770448548813">企业版功能</th><th>描述</th></tr></thead><tbody><tr><td>密码库健康报告</td><td>执行有关公开密码、重用密码、弱密码等的报告。<a href="../your-vault/vault-health-reports.md">了解更多</a>。</td></tr><tr><td>数据泄露报告</td><td>执行在已知违规行为中的已泄露数据（电子邮件地址、密码、信用卡、DoB 等）的报告。<a href="../your-vault/vault-health-reports.md">了解更多</a>。</td></tr><tr><td>事件日志</td><td>获取组织密码库内发生的事件的时间戳记录，以便在网页密码库中轻松使用或由其他系统提取。<a href="../admin-console/reporting/event-logs.md">了解更多</a>。</td></tr></tbody></table>

### 身份验证 <a href="#authentication" id="authentication"></a>

<table><thead><tr><th width="200.92256676823803">企业版功能</th><th>描述</th></tr></thead><tbody><tr><td>用于个人的 2FA</td><td>适用于任何 Bitwarden 用户的一组强大的 2FA 选项。<a href="../two-step-login/two-step-login-methods.md">了解更多</a>。</td></tr><tr><td>组织层面的 2FA</td><td>通过 Duo 为整个组织启用 2FA。<a href="../two-step-login/setup-guides/two-step-login-via-duo.md">了解更多</a>。</td></tr><tr><td>生物识别验证</td><td><p>适用于：<br>-Android（指纹解锁或面部解锁）和 iOS（触控 ID 和面容 ID）<br>-Windows 桌面应用程序（使用 Windows Hello PIN、面部识别等）和 macOS 桌面应用程序（触控 ID）<br>-Chromium、Firefox 87+ 和 Safari 浏览器扩展<br></p><p><a href="../your-vault/unlocking-with-biometrics.md">了解更多</a></p></td></tr><tr><td>SSO 登录</td><td>利用您现有的身份提供程序通过 SAML 2.0 或 OpenID Connect (OIDC) 对您的 Bitwarden 组织用户进行身份验证。<a href="../login-with-sso/about-login-with-sso.md">了解更多</a>。<br><br>使用 SSO 登录，您可以使用两个解密选项之一来确定用户在通过身份验证后如何解密密码库数据。<a href="../login-with-sso/member-decryption-options.md">了解更多</a>。</td></tr></tbody></table>

### 安全性 <a href="#security" id="security"></a>

<table><thead><tr><th width="207">企业版功能</th><th>描述</th></tr></thead><tbody><tr><td>用于登录、笔记、支付卡和身份的安全存储</td><td>Bitwarden <a href="../your-vault/vault-items.md">密码库项目</a>在存储在任何地方之前都经过加密。<a href="../security/encryption.md">了解更多</a>。</td></tr><tr><td>零知识加密</td><td>所有密码库数据都经过端到端加密。<a href="https://bitwarden.com/blog/post/bitwarden-network-security-assessment-2020/">了解更多</a>。</td></tr><tr><td>安全的密码生成器</td><td>为每个密码库项目生成安全、随机且唯一的密码。<a href="https://bitwarden.com/password-generator/">了解更多</a>。</td></tr><tr><td>加密导出</td><td>下载加密导出以安全地存储密码库数据备份。<a href="../import-export/encrypted-exports.md">了解更多</a>。</td></tr><tr><td>生物识别验证</td><td><p>适用于：<br>-Android（指纹解锁或面部解锁）和 iOS（触控 ID 和面容 ID）<br>-Windows 桌面应用程序（使用 Windows Hello PIN、面部识别等）和 macOS 桌面应用程序（触控 ID）<br>-Chromium、Firefox 87+ 和 Safari 浏览器扩展<br></p><p><a href="../your-vault/unlocking-with-biometrics.md">了解更多</a></p></td></tr><tr><td>紧急访问</td><td>用户可以指定和管理受信任的紧急联系人，紧急联系人可以在紧急情况下请求访问他们的密码库。<a href="../security/emergency-access.md">了解更多</a>。</td></tr><tr><td>账户指纹短语</td><td>在执行与加密相关或入职操作时唯一且安全地标识 Bitwarden 用户帐户的安全措施。<a href="../security/account-fingerprint-phrase.md">了解更多</a>。</td></tr><tr><td>辅助处理商</td><td>查看我们完整的辅助处理商列表：<a href="../security/who-are-bitwardens-subprocessors.md">Bitwarden 的辅助处理商</a>。</td></tr></tbody></table>

### 合规，审计，认证 <a href="#compliance-audits-certifications" id="compliance-audits-certifications"></a>

| 企业版功能                 | 描述                                                                                                |
| --------------------- | ------------------------------------------------------------------------------------------------- |
| SOC 2 Type 2          | [了解我们的 SOC 2 Type 2 认证](https://bitwarden.com/blog/post/bitwarden-achieves-soc-2-certification/)。 |
| 2018 安全评估             | [了解我们的 2018 安全评估](https://bitwarden.com/blog/post/third-party-security-audit/)。                   |
| 2020 安全评估             | [了解我们的 2020 安全评估](https://bitwarden.com/blog/post/bitwarden-network-security-assessment-2020/)。   |
| GDPR、CCPA、HIPAA 和隐私保护 | [了解我们对各种隐私框架的遵守情况](https://bitwarden.com/compliance/)。                                            |
| 白盒测试                  | 由单元测试和质量检查工程师执行。                                                                                  |
| 黑盒测试                  | 通过自动化或手动测试执行。                                                                                     |
| Bug 赏金计划              | 通过 HackerOne 实施。[了解更多](https://hackerone.com/bitwarden/?type=team)。                               |

### API 和可扩展性 <a href="#apis-and-extensibility" id="apis-and-extensibility"></a>

| 企业版功能  | 描述                                                                                 |
| ------ | ---------------------------------------------------------------------------------- |
| 编程无障碍  | 用于组织的公共和私有 API。[了解更多](../organizations/bitwarden-public-api.md)。                   |
| 命令行界面  | 功能齐全的自文档命令行工具。[了解更多](../password-manager/developer-tools/password-manager-cli.md)。 |
| 可扩展性支持 | 结合 API​​ 和 CLI 进行自动化工作流程。                                                          |

### 适应性 <a href="#resiliciency" id="resiliciency"></a>

| 企业版功能       | 描述                                    |
| ----------- | ------------------------------------- |
| 本地缓存 & 离线访问 | [了解更多](../security/security-faqs.md)。 |
