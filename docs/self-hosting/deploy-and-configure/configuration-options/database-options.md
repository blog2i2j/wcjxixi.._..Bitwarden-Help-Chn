# 数据库选项

{% hint style="success" %}
对应的[官方文档地址](https://bitwarden.com/help/database-options/)
{% endhint %}

## 服务器部署的默认数据库 <a href="#default-database-for-server-deployments" id="default-database-for-server-deployments"></a>

除 [Lite](../docker/lite-deployment.md) 部署外，其他所有 Bitwarden 自托管服务器部署默认附带 MSSQL Express 镜像。这会将您的加密密码库数据与应用程序容器放置在同一位置，并通过确保更新、维护和备份与代码的其余部分同时进行，从而简化部署流程。

此默认数据库不需要额外许可，并已按照 Bitwarden 标准预先配置，以安全存储并自动备份密码库数据（[了解更多](../../backup-server-data.md)）。

### 服务器部署使用外部数据库 <a href="#using-an-external-database-for-server-deployments" id="using-an-external-database-for-server-deployments"></a>

在默认附带 MSSQL Express 镜像的自托管服务器部署中，该容器的使用是可选的。为了实现高可用性或利用现有基础设施，客户可以连接到 2022 版本的外部 MSSQL 服务器或集群（[了解更多](connect-to-an-external-mssql-database.md)）。

无论您是使用附带的 MSSQL Express 镜像还是您自己的外部 MSSQL 服务器或集群，标准 Bitwarden 部署目前都必须使用 MSSQL。

## Lite 部署的数据库 <a href="#databases-for-lite-deployments" id="databases-for-lite-deployments"></a>

Bitwarden Lite 自托管部署不附带内置数据库，但可以连接到现有的 MySQL/MariaDB、MSSQL、SQLite 或 PosgreSQL 数据库（[了解更多](../docker/lite-deployment.md)）。**只有 Lite 部署**支持这些数据库选项，标准部署需要 MSSQL。

{% hint style="info" %}
由于 Bitwarden Lite 数据库不是由应用程序容器提供或与之并置的，因此数据库维护（包括更新、维护和备份）必须完全由您管理。
{% endhint %}

## 可选的数据库任务 <a href="#optional-database-jobs" id="optional-database-jobs"></a>

### 数据库准备 <a href="#database-preparation" id="database-preparation"></a>

在非 Lite 自托管部署中，Bitwarden 会检查构建的连接字符串中指定的数据库是否存在，如果不存在，则会创建它。此任务要求配置的 SQL 用户在数据库服务器中拥有管理权限。权限不足将导致此任务失败。

如果您正在部署自己的外部数据库，请在 `global.override.env` 文件中设置以下环境变量来禁用此部署步骤：

```systemd
globalSettings__sqlServer__skipDatabasePreparation=true
```

### 数据库维护 <a href="#database-maintenance" id="database-maintenance"></a>

在所有自托管部署中，包括 Lite 部署，Bitwarden 会在数据库上运行计划任务，以执行例行维护，例如计算数据库统计信息和构建索引。这些任务要求配置的 SQL 用户在数据库服务器中拥有管理权限。权限不足将导致此任务失败，相关日志将记录到 `admin` 容器日志中。

如果您希望以单独的用户身份运行这些维护任务，请在 `global.override.env` 文件中设置以下环境变量来禁用此行为：

```systemd
globalSettings__sqlServer__disableDatabaseMaintenanceJobs=true
```

{% hint style="info" %}
如果您禁用了数据库维护任务，请定期手动检查数据库清理和索引创建情况。
{% endhint %}
