# 网络要求

{% hint style="success" %}
对应的[官方文档地址](https://bitwarden.com/help/networking-requirements/)
{% endhint %}

在自托管环境中部署 Bitwarden，需要您的网络基础设施支持特定的协议、端口和通信模式。本文概述了自托管 Bitwarden 部署的网络要求及兼容性注意事项。某些客户端侧的要求也可能适用于使用 Bitwarden Cloud 的组织，这些要求已在各相关条目中注明。

## 协议要求 <a href="#protocol-requirements" id="protocol-requirements"></a>

以下部分描述了部署自托管 Bitwarden 服务器时的严格协议要求：

### 端口 <a href="#ports" id="ports"></a>

Bitwarden **必须使用**两个开放的端口用于通信，一个用于 HTTP（默认 `80`），另一个用于 HTTPS（默认 `443`）。Bitwarden 不支持仅在单一端口可用的情况下运行，但可以在安装过程中更改 HTTP 和 HTTPS 端口的默认值：

<table><thead><tr><th width="321.20001220703125">部署方式</th><th>配置非默认端口的方法</th></tr></thead><tbody><tr><td>Docker、标准 (Linux &#x26; Windows)</td><td>编辑 <code>./bwdata/config.yml</code> 中的 <code>http_port=</code> 和 <code>https_port=</code>，然后运行重建命令。</td></tr><tr><td>Docker、手动 (Linux)</td><td>在同一目录中创建 <code>docker-compose.yml</code> 的副本，然后将其重命名为 <code>docker-compose.override.yml</code>。在覆盖文件中，编辑 <code>nginx</code> 端口映射。这些更改将在运行时合并。</td></tr><tr><td>Docker、离线 (Linux &#x26; Windows)</td><td>在同一目录中创建 <code>docker-compose.yml</code> 的副本，然后将其重命名为 <code>docker-compose.override.yml</code>。在覆盖文件中，编辑 <code>nginx</code> 端口映射。这些更改将在运行时合并。</td></tr><tr><td>Helm</td><td>端口暴露由您的 Kubernetes Ingress Controller 控制，而非 Bitwarden 服务。</td></tr><tr><td>Lite</td><td>在 <code>docker run</code> 命令或 <code>docker-compose.yml</code> 文件中设置运行时使用的端口。</td></tr></tbody></table>

### HTTP 方法 <a href="#http-verbs" id="http-verbs"></a>

{% hint style="info" %}
此要求同样适用于云端客户。
{% endhint %}

Bitwarden **不支持**在对 HTTP 方法进行限制或白名单控制的环境中运行。Bitwarden 在整个产品中会使用多种 HTTP 方法。具体使用哪些方法取决于所调用的功能，并且可能会随着现有功能或未来功能的支持而发生变化。

> **\[译者注]**：**HTTP Verbs**（也叫 **HTTP Methods，HTTP 方法**），指的是在 HTTP 请求中告诉服务器「要做什么操作」。常见的有：GET（获取数据）、POST（提交数据）、PUT（更新数据）、DELETE（删除数据）、PATCH（部分更新）。

### WebSocket 连接 <a href="#websocket-connections" id="websocket-connections"></a>

{% hint style="info" %}
此要求同样适用于云端客户。
{% endhint %}

Bitwarden **不支持**在 WebSocket 连接被阻止的环境中运行。Bitwarden 客户端与自托管服务器之间需要建立 WebSocket（`wss://`）连接。

## 中间网络设备 <a href="#intermediary-network-device" id="intermediary-network-device"></a>

以下部分描述了在自托管部署中必须如何配置中间网络设备：

### 反向代理 <a href="#reverse-proxies" id="reverse-proxies"></a>

Bitwarden **支持**在反向代理后面运行，但使用反向代理时，**要求**将所有标头（包括 `Host:`）不做任何修改地传递给 Bitwarden 的 `nginx` 容器。

### 正向代理 <a href="#forward-proxies" id="forward-proxies"></a>

Bitwarden **支持**在正向代理后面运行，但在此类环境中，强烈建议采用以下两种部署策略之一：

* 按照 [Linux](deploy-and-configure/docker/linux-offline-deployment.md) 或 [Windows](deploy-and-configure/docker/windows-offline-deployment.md) 离线部署说明。
* 按照使用[带正向代理的 Docker Compose](deploy-and-configure/docker/configure-self-hosted-environment-with-forward-proxy.md) 部署的说明。

### 防火墙白名单 <a href="#whitelist-firewalls" id="whitelist-firewalls"></a>

Bitwarden **支持**在配置为允许[必要流量](../security/trusted-communications/bitwarden-addresses.md)的白名单防火墙后面运行，但在此类环境中，强烈建议采用以下两种部署策略之一：

* 按照 [Linux](deploy-and-configure/docker/linux-offline-deployment.md) 或 [Windows](deploy-and-configure/docker/windows-offline-deployment.md) 离线部署说明。
* 按照使用[带正向代理的 Docker Compose](deploy-and-configure/docker/configure-self-hosted-environment-with-forward-proxy.md) 部署的说明。

### 网络应用程序防火墙 & 入侵防御系统 <a href="#web-application-firewalls-and-intrusion-prevention-systems" id="web-application-firewalls-and-intrusion-prevention-systems"></a>

{% hint style="info" %}
此要求同样适用于云端客户。
{% endhint %}

Bitwarden **兼容**在网络应用防火墙 (WAF) 或入侵防御系统 (IPS) 后面运行，但在此类环境中，应在 Bitwarden 服务器正式上线前将 WAF 或 IPS 设置为学习（也称为「训练」或「模拟」）模式。这将使管理员有机会在 Bitwarden 服务器处于测试阶段时审查规则集，从而降低服务器正式上线且 WAF 或 IPS 处于主动拦截状态时，加密负载、访问令牌或其他加密数据传输被阻止的可能性。

## 其他网络平台 <a href="#other-network-platforms" id="other-network-platforms"></a>

以下部分描述了网络上的其他设备如何与自托管 Bitwarden 服务器交互：

### 端点检测、电子邮件扫描 & 防病毒 <a href="#endpoint-detection-mail-scanning-and-anti-virus" id="endpoint-detection-mail-scanning-and-anti-virus"></a>

{% hint style="info" %}
此要求同样适用于云端客户。
{% endhint %}

端点检测 & 响应、邮件扫描和反病毒平台被报告会干扰 Bitwarden 容器的正常运行；具体而言，报告包括 Windows 反病毒平台因 Bitwarden 容器基于 Linux 而将其标记为可疑，以及电子邮件扫描平台在邀请电子邮件中编辑或重新格式化超链接。

**请勿禁用这些解决方案**，除非在故障排除过程中 Bitwarden 支持团队建议这样做。但如果您遇到这些问题，请检查您的端点检测、电子邮件扫描和防病毒平台是否存在与 Bitwarden 正常操作相关的误报。

### 中间人代理 <a href="#man-in-the-middle-proxies" id="man-in-the-middle-proxies"></a>

在部署了中间人 ( MITM) 代理（例如 ZScaler）的环境中运行 Bitwarden 可能存在风险，具体取决于您组织的配置。在此类网络连接上， **应禁用记录 Bitwarden 流量的完整数据** ，以保护关键安全技术，例如 Bitwarden 流量的传输层加密。

> **\[译者注]**：**中间人 ( MITM) 代理**，一种「主动充当中间人」的代理服务器，用来拦截、查看甚至修改通信内容，具体例如解密 HTTPS（前提是安装了企业证书），然后检查内容（是否有病毒/敏感信息），最后决定是否放行。它并不一定是攻击，也可能是合法工具（比如企业安全审计）。

## 环境因素 <a href="#environmental-factors" id="environmental-factors"></a>

以下部分描述了自托管 Bitwarden 服务器如何在特定环境中运行：

### 网闸环境 <a href="#air-gapped-environments" id="air-gapped-environments"></a>

Bitwarden **支持**在网闸或离线环境中运行，但不建议在标准的「在线」部署与离线部署之间进行迁移。请使用以下文档之一，以在离线环境中进行部署：

* [Linux 离线部署指南](deploy-and-configure/docker/linux-offline-deployment.md)
* [Windows 离线部署指南](deploy-and-configure/docker/windows-offline-deployment.md)

> **\[译者注]**：[网闸](https://zh.wikipedia.org/wiki/%E7%BD%91%E9%97%B8) (air-gapped) 网络，也叫物理隔离的网络。是指与外部网络（如互联网或其他外部系统）完全隔离的计算机网络。这种隔离通过物理或逻辑手段实现，确保网络无法与外部环境进行数据交换，从而增强安全性。
