# 环境变量

{% hint style="success" %}
对应的[官方文档地址](https://bitwarden.com/help/article/environment-variables/)
{% endhint %}

Bitwarden 的某些功能无法通过 `bitwarden.sh` 安装程序进行配置。需要通过编辑环境文件 (`./bwdata/env/global.override.env`) 来配置这些设置。`global.override.env` 中预置了一些可配置的变量（参阅[已有变量](environment-variables.md#included-variables)），还有一些额外的变量可以手动添加（参阅[可选变量](environment-variables.md#optional-variables)）。

**每当您对 `global.override.env` 做了修改后，请执行 `./bitwarden.sh rebuild` 以应用您的更改。**

{% hint style="info" %}
本文中的信息可能不适用于 Bitwarden Lite 自托管部署。
{% endhint %}

## 已有变量 <a href="#included-variables" id="included-variables"></a>

以下变量是 `global.override.env` 中已经存在的变量：

| 变量                                             | 描述                                                                                                                                                                                                                                           |
| ---------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `globalSettings__baseServiceUri__vault=`       | 输入您的 Bitwarden 实例的域名。如果未配置，域名将默认为 localhost。请勿包含尾部斜杠。                                                                                                                                                                                        |
| `globalSettings__sqlServer__connectionString=` | 使用此字段[连接到外部 MSSQL 数据库](connect-to-an-external-mssql-database.md)。                                                                                                                                                                            |
| `globalSettings__oidcIdentityClientKey=`       | 随机生成的 OpenID Connect 客户端密钥。更多信息，请参阅 [OpenID 文档](https://openid.net/specs/openid-connect-registration-1_0.html#RegistrationResponse)。                                                                                                         |
| `globalSettings__duo__aKey=`                   | 随机生成的 Duo 密钥。更多信息，请参阅 [Duo 文档](https://duo.com/docs/duoweb-v2#1.-generate-an-akey)。                                                                                                                                                          |
| `globalSettings__yubico__clientId=`            | <p>YubiCloud 验证服务或自托管的 Yubico 验证服务器的客户端 ID。</p><p><br>如果是 YubiCloud，请在<a href="https://upgrade.yubico.com/getapikey/">此处</a>获取您的客户端 ID 和安全密钥。</p><p><br>如果是自托管 Yubico 验证服务器，请参阅可选变量 <code>globalSettings__yubico__validationUrls</code>。</p> |
| `globalSettings__yubico__key=`                 | <p>YubiCloud 验证服务或自托管的 Yubico 验证服务器的安全密钥。</p><p><br>如果是 YubiCloud，请在<a href="https://upgrade.yubico.com/getapikey/">此处</a>获取您的客户端 ID 和安全密钥。</p><p><br>如果是自托管 Yubico 验证服务器，请参阅可选变量 <code>globalSettings__yubico__validationUrls</code>。</p>   |
| `globalSettings__mail__replyToEmail=`          | 用于邀请的电子邮箱地址，通常为 `no_reply@smpt__host`。                                                                                                                                                                                                       |
| `globalSettings__mail__smtp__host=`            | 您的 SMTP 服务器的主机名（推荐）或 IP 地址。                                                                                                                                                                                                                  |
| `globalSettings__mail__smtp__port=`            | SMTP 服务器使用的 SMTP 端口。                                                                                                                                                                                                                         |
| `globalSettings__mail__smtp__ssl=`             | <p>（布尔值）您的 SMTP 服务器是否使用加密协议：<br><code>true</code> = SSL<br><code>false</code> = TLS</p>                                                                                                                                                      |
| `globalSettings__mail__smtp__username=`        | `smtp__host` 的有效用户名。                                                                                                                                                                                                                         |
| `globalSettings__mail__smtp__password=`        | `smtp__host` 的有效密码。SMTP 密码不支持美元符号 `$` 字符。                                                                                                                                                                                                    |
| `globalSettings__disableUserRegistration=`     | 指定为 `true` 将禁用新用户通过注册页面在此实例上注册账户。                                                                                                                                                                                                            |
| `globalSettings__hibpApiKey=`                  | 您的 HaveIBeenPwned (HIBP) API 密钥，可在[此处](https://haveibeenpwned.com/API/Key)获取。该密钥允许用户运行[数据泄露报告](../../../password-manager/your-vault/security-tools/vault-health-reports.md#data-breach-report-individual-vaults-only)，并在创建账户时检查其主密码是否存在泄露。   |
| `adminSettings__admins=`                       | 可以访问[系统管理员门户](../../system-administrator-portal.md)的电子邮箱地址。                                                                                                                                                                                  |

## 可选变量 <a href="#optional-variables" id="optional-variables"></a>

以下变量在 `global.override.env` 中尚不存在，但可以手动添加：

| 变量                                                           | 描述                                                                                                                                                                                                                                                                                          |
| ------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `globalSettings__logDirectory=`                              | 指定保存容器日志文件的目录。这必须是容器内的一个目录，默认为 `globalSettings__logDirectory=etc/bitwarden/logs`。                                                                                                                                                                                                           |
| `globalSettings__logRollBySizeLimit=`                        | 指定容器日志文件的大小限制以字节为单位（例如 `globalSettings__logRollBySizeLimit=1073741824`）。                                                                                                                                                                                                                    |
| `globalSettings__mail__smtp__trustServer=`                   | 指定为 `true` 将以显式信任 SMTP 服务器提供的证书（**不建议用于生产 环境**）。                                                                                                                                                                                                                                            |
| `globalSettings__mail__smtp__sslOverride=`                   | 指定为 `true` 将在端口 25 上使用 SSL（而不是 TLS）。                                                                                                                                                                                                                                                        |
| `globalSettings__mail__smtp__startTls=`                      | 指定为 `true` 将强制使用 STARTTLS（随机 TLS）。                                                                                                                                                                                                                                                          |
| `globalSettings__organizationInviteExpirationHours=`         | 指定组织邀请到期的小时数（默认为 `120`）。                                                                                                                                                                                                                                                                    |
| `globalSettings__yubico__validationUrls__0=`                 | <p>自托管 Yubico 验证服务器的主 URL。例如：<code>globalSettings__yubico__validationUrls__0=https://your.url.com/wsapi/2.0/verify</code>。</p><p></p><p>通过创建递增的环境变量来添加其他验证服务器 URL，例如：  <code>globalSettings__yubico__validationUrls__1=</code>，<code>globalSettings__yubico__validationUrls__2=</code>。</p> |
| `globalSettings__enableCloudCommunication=`                  | 设置为 `true` 以允许您的服务器和我们的云端系统之间进行通信。这样做可以[开启计费和许可证同步](../../plan-for-deployment/self-host-an-organization.md#step-4-setup-billing-and-license-sync)。                                                                                                                                          |
| `adminSettings__deleteTrashDaysAgo=`                         | 指定多少天后从回收站永久删除项目。默认为 `adminSettings__deleteTrashDaysAgo=30`。                                                                                                                                                                                                                                |
| `globalSettings__sso__enforceSsoPolicyForAllUsers=`          | 指定为 `true` 以对所有者和管理员角色强制执行[要求 SSO 身份验证](../../../admin-console/oversight-visibility/enterprise-policies.md#require-single-sign-on-authentication)策略。                                                                                                                                        |
| `globalSettings__baseServiceUri__cloudRegion=`               | <p>指定为 <code>US</code> 或 <code>EU</code>，以指定自托管服务器应超链接到哪个云端服务器。</p><p></p><p>如果使用 EU 服务器，还需要设置其他一些变量，如<a href="../../../security/server-geographies.md#connect-your-self-hosted-server">此处</a>所述。</p>                                                                                       |
| `globalSettings__sqlServer__DisableDatabaseMaintenanceJobs=` | <p>指定为 <code>true</code> 以跳过数据库中统计和索引重建任务的应用程序端维护。</p><p></p><p>这些任务需要提升的 MSSQL 权限，如果该值设为 <code>true</code>，则应重新配置为以数据库用户身份运行。<a href="database-options.md">了解更多</a>。</p>                                                                                                                   |
| `globalSettings__sqlServer__SkipDatabasePreparation=`        | <p>指定为 <code>true</code> 可跳过应用程序端数据库准备。如果未指定，数据库准备将在安装时检查 <code>globalSettings__sqlServer__connectionString=</code> 中指定名称的数据库是否存在，如果不存在，则创建一个。</p><p></p><p>这项任务需要提升的 MSSQL 权限，如果该值设置为 <code>true</code>，则在初始化安装之前，指定的数据库必须存在。<a href="database-options.md">了解更多</a>。</p>                   |

### 要求身份验证的负载均衡器 <a href="#load-balancers-requiring-authentication" id="load-balancers-requiring-authentication"></a>

无法访问共享 Cookie 存储的 Bitwarden 客户端（例如桌面和移动客户端）无法与使用要求身份验证的负载均衡器的自托管服务器通信。要启动 SSO 会话并将其 Cookie 复制到 Bitwarden 客户端 Cookie 存储中，请将以下变量添加到 `global.override.env` 文件中：

| 变量                                                              | 描述                                                    |
| --------------------------------------------------------------- | ----------------------------------------------------- |
| `globalSettings__communication__bootstrap=`                     | <p><br>要启用此功能，请设置为 <code>ssoCookieVendor</code> 。</p> |
| `globalSettings__communication__ssoCookieVendor__cookieName=`   | 身份提供者设置的 SSO Cookie 名称（例如， `sso_token` ）。             |
| `globalSettings__communication__ssoCookieVendor__cookieDomain=` | 读取 SSO Cookie 的域名（例如， `example.com` ）。                |

### 刷新令牌变量 <a href="#refresh-token-variables" id="refresh-token-variables"></a>

刷新令牌变量可用于更改令牌的超时时间。管理员可利用这些值实现诸如强制用户每日登录等功能。使用以下变量配置服务器对刷新令牌的处理方式：

| 变量                                                                         | 描述                                                                                                                                                                                                                                                                               |
| -------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `globalSettings__IdentityServer__ApplyAbsoluteRefreshTokenOnRefreshToken=` | <p>指定为 <code>true</code> 仅使用指定的绝对有效期来处理刷新令牌，并忽略基于使用情况的过期滑动。</p><p></p><p>当为 true 时，仅考虑 <code>__AbsoluteRefreshTokenLifetimeSeconds=</code> 来确定行为。</p><p></p><p>指定为 <code>false</code> 允许刷新令牌在它们被使用时过期滑动（即在指定时间段内延长有效期）。</p><p></p><p>当为 <code>false</code> 时，将考虑以下两种选项来确定行为。</p> |
| `globalSettings__IdentityServer__AbsoluteRefreshTokenLifetimeSeconds=`     | <p>指定一个整数。无论是否允许滑动，刷新令牌将在该整数绝对生命周期（以秒为单位）后过期。</p><p></p><p>当且仅当 <code>__ApplyAbsoluteRefreshTokenOnRefreshToken=true</code> 时，此变量才可能为 <code>0</code> ，在这种情况下，刷新令牌总是被拒绝。</p>                                                                                                      |
| `globalSettings__IdentityServer__SlidingRefreshTokenLifetimeSeconds=`      | <p>指定一个大于 <code>0</code> 的整数。刷新令牌在使用时将根据该整数（以秒为单位）延长其有效期。</p><p></p><p>刷新令牌总是会在其配置的绝对生命周期后过期，无论此处设置如何。</p>                                                                                                                                                                       |
