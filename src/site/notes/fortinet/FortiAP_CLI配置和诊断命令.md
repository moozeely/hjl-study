---
{"dg-publish":true,"permalink":"/fortinet/FortiAP_CLI配置和诊断命令/"}
---

7.4.2 

FortiAP CLI 通过使用配置和诊断命令操作的变量来控制无线电和网络操作。

配置命令

|                  |                        |
| ---------------- | ---------------------- |
| 命令               | 描述                     |
| cfg -s           | 列出最常用设置的变量以及未使用默认值的变量。 |
| cfg -a var=value | 添加或更改变量值。              |
| cfg -c           | 将更改提交到 flash。          |
| cfg -x           | 将设置重置为出厂默认设置。          |
| cfg -r var       | 删除变量。                  |
| cfg -e           | 导出变量。                  |
| cfg -h           | 显示所有配置命令的帮助和配置变量的完整列表。 |

配置变量

|   |   |
|---|---|
|变量|描述和价值|
|AC_CTL_PORT|WiFi 控制器控制 （CAPWAP） 端口。<br><br>默认值：5246。|
|AC_DATA_CHAN_SEC|支持的数据通道安全策略。<br><br>clear - 明文<br><br>dtls - DTLS（加密）<br><br>ipsec - IPsec VPN<br><br>ipsec-sn - 包含 FortiAP 序列号的 IPsec VPN。|
|AC_DISCOVERY_TYPE|0 - 自动 - 循环浏览所有发现类型，直到成功。<br><br>1 - 静态。指定 WiFi 控制器<br><br>2 - DHCP<br><br>3 - DNS<br><br>5 - 广播<br><br>6 - 组播<br><br>7-福蒂云|
|AC_HOSTNAME_1<br><br>AC_HOSTNAME_2<br><br>AC_HOSTNAME_3|用于静态发现的 WiFi 控制器主机名。|
|AC_IPADDR_1<br><br>AC_IPADDR_2<br><br>AC_IPADDR_3|用于静态发现的 WiFi 控制器 IP 地址。|
|AC_DISCOVERY_DHCP_OPTION_CODE|DHCP 服务器的选项代码。<br><br>默认值：138。|
|AC_DISCOVERY_MC_ADDR|用于控制器发现的组播地址。<br><br>默认值：224.0.1.140。|
|ADDR_MODE|FortiAP 设备如何获取其 IP 地址和网络掩码。<br><br>DHCP - FortiGate 接口分配地址。<br><br>STATIC - 在AP_IPADDR和AP_NETMASK中指定。<br><br>默认值：DHCP。|
|ADMIN_TIMEOUT|管理超时（以分钟为单位）。适用于 GUI 会话。<br><br>默认值：5 分钟。|
|AP_IPADDR<br><br>AP_NETMASK<br><br>IPGW|当 FortiAP 单元 IP 地址、网络掩码和默认网关ADDR_MODE STATIC 时，这些变量会设置 FortiAP 单元 IP 地址、网络掩码和默认网关。<br><br>AP_IPADDR默认值：192.168.1.2。<br><br>AP_NETMASK默认值：255.255.255.0。<br><br>IPGW 的默认值：192.168.1.1。|
|ALLOW_HTTPS|0 - HTTPS 禁用<br><br>1 - 启用 HTTPS<br><br>2 - 由空调控制<br><br>默认值：2。|
|ALLOW_SSH|0 - SSH 禁用<br><br>1 - 启用 SSH<br><br>2 - 由空调控制<br><br>默认值：2。|
|AP_MGMT_VLAN_ID|非零值将 VLAN ID 应用于设备管理。请参阅[保留 VLAN ID。](https://docs.fortinet.com/document/fortiap/7.4.2/fortiwifi-and-fortiap-configuration-guide/621215/wireless-network-configuration#ReservedVLAN)<br><br>默认值：0。|
|AP_MODE|FortiAP 操作模式。<br><br>0 - 精简 AP<br><br>2 - 非托管站点勘测模式。请参阅 SURVEY 变量。<br><br>默认值：0。|
|BAUD_RATE|控制台数据速率：9600、19200、38400、57600 或 115200 波特。<br><br>默认值：9600。|
|DNS_SERVER|客户端的 DNS 服务器。如果ADDR_MODE是 DHCP，则会自动分配 DNS 服务器。|
|FAP_ETHER_TRUNK|在 FortiAP-U 型号上配置端口行为。<br><br>0 - 虚拟开关。默认模式。<br><br>1 - 以太硬件绑定。支持 LAN1 和 LAN2 端口上的静态以太网通道绑定。仅适用于部分 FortiAP-U 型号。<br><br>2 - 以太坊 802.3ad 键合。在 LAN1 和 LAN2 端口上支持 IEEE 802.3ad 链路聚合控制协议 （LACP）。<br><br>3 - 启用 WAN-LAN。支持将第二个WAN端口配置为LAN（WAN-LAN模式配置）。|
|FIPS_CC|启用联邦 FortiAP 型号上的信息处理标准 （FIPS） 模式。<br><br>1 - 启用 FIPS 模式。<br><br>自 禁用 FIPS 模式，将 FortiAP 恢复出厂设置。<br><br>注意：FAP-431F 和 FAP-433F 不支持 FIPS 模式。|
|FIRMWARE_UPGRADE|默认值：0。|
|LED_STATE|启用/禁用状态 LED。<br><br>0 - LED 启用<br><br>1 - LED 已禁用<br><br>2 - 遵循交流电设置|
|LOGIN_PASSWD|管理员登录密码。默认情况下，此值为空。|
|STP_MODE|生成树协议。<br><br>0 - 关闭<br><br>1 - 开|
|TPM|仅限 Wi-Fi 6E 型号：启用受信任的平台模块 （TPM）。<br><br>1 - 启用 TPM<br><br>0 - 禁用 TPM<br><br>默认值：0。|
|WANLAN_MODE|在 FortiAP、FortiAP-S 和 FortiAP-W2 型号上配置端口行为。<br><br>WAN-ONLY - 默认模式<br><br>WAN-LAN - 将LAN端口桥接到传入的WAN接口<br><br>AGGREGATE - 启用链路聚合|
|WTP_LOCATION|描述 AP 位置的可选字符串。|
|网格变量||
|MESH_AP_BGSCAN|启用或禁用后台网状网络根 AP 扫描。<br><br>0 - 已禁用<br><br>1 - 已启用|
|MESH_AP_BGSCAN_RSSI|如果根AP信号较弱，且低于接收信号强度指示器（RSSI）阈值，WiFi驱动会立即启动新一轮扫描并忽略 配置的延迟。设置介于 0 和 127 之间的值。MESH_AP_BGSCAN_PERIOD<br><br>新一轮扫描完成后，将扫描完成事件传递给 wtp 守护程序以触发 漫游。|
|MESH_AP_BGSCAN_PERIOD|扫描之间出现延迟期的时间（以秒为单位）。将值设置在 1 和 3600 之间。|
|MESH_AP_BGSCAN_IDLE|时间（以毫秒为单位）。将值设置在 0 和 1000 之间。|
|MESH_AP_BGSCAN_INTV|通道扫描之间的时间（以毫秒为单位）。将值设置在 200 和 16000 之间。|
|MESH_AP_BGSCAN_DUR|无线电将继续扫描频道的时间（以毫秒为单位）。将值设置在 10 和 200 之间。|
|MESH_AP_BSSID|WiFi MAC 地址。|
|MESH_AP_PASSWD|用于网状回程的预共享密钥。|
|MESH_AP_SCANCHANLIST|指定要扫描的通道。|
|MESH_AP_SECURITY|配置网状回程SSID的安全模式。<br><br>0 - 开盘<br><br>1 - WPA/WPA2 个人<br><br>2 - WPA3-SAE<br><br>默认值：0。|
|MESH_AP_SSID|用于网状回程的 SSID。<br><br>默认值：fortinet.mesh.root。|
|MESH_AP_TYPE|回程到控制器的通信类型：<br><br>0 - 以太网<br><br>1 - WiFi网状网络<br><br>2 - 以太网，支持网状备份<br><br>默认值：0。|
|MESH_ETH_BRIDGE|1 - 将网状 WiFi SSID 桥接到 FortiAP 以太网端口。这可用于点对点网桥配置。仅当 MESH_AP_TYPE =1 时才可用。<br><br>0 - 无 WiFi-以太网网桥<br><br>默认值：0。|
|MESH_MAX_HOPS|数据包可以在网格上的节点之间传递的最大次数。<br><br>默认值：4。|
|将以下因素相加，FortiAP 与得分最低的网格 AP 相关联。||
|MESH_SCORE_HOP_WEIGHT|来自根的网格跃点数的乘数。默认值：50。|
|MESH_SCORE_CHAN_WEIGHT|AP 总 RSSI 乘法器。默认值：1。|
|MESH_SCORE_RATE_WEIGHT|信标数据速率倍增器。默认值：1。|
|MESH_SCORE_BAND_WEIGHT|频段权重（0 表示 2.4 GHz，1 表示 5 GHz）乘法器。默认值：100。|
|MESH_SCORE_RSSI_WEIGHT|AP 信道 RSSI 乘法器。默认值：100。|
|调查变量||
|SURVEY_SSID|SSID在现场勘测模式下广播（AP_MODE=2）。|
|SURVEY_TX_POWER|现场勘测模式下的发射机功率 （AP_MODE=2）。|
|SURVEY_TX_POWER_24|2.4 GHz 发射机功率，用于现场勘测 SSID，单位为 dBm。默认值 = 30。|
|SURVEY_TX_POWER_50|用于现场勘测的 5 GHz 发射机功率 SSID，单位为 dBm。默认值 = 30。|
|SURVEY_TX_POWER_60|用于现场勘测的 6 GHz 发射机功率 SSID，单位为 dBm。默认值 = 30。|
|SURVEY_BEACON_INTV|现场勘测信标间隔（以秒为单位）。默认值：100 毫秒。|
|SURVEY_CH_24|2.4 GHz频段的现场勘测发射信道。默认值：6。|
|SURVEY_CH_50|5 GHz频段的现场勘测发射信道。默认值：36。|
|SURVEY_CH_60|6 GHz频段的现场勘测发射信道。默认值：36。|
|SURVEY_CW_24|2.4 GHz 信道绑定带宽，用于现场勘测 SSID。<br><br>0 - 20兆赫<br><br>1 - 40兆赫<br><br>默认值 = 0|
|SURVEY_CW_50|5 GHz 信道绑定带宽，用于现场勘测 SSID。<br><br>0 - 20兆赫<br><br>1 - 40兆赫<br><br>2 - 80兆赫<br><br>3 - 160兆赫<br><br>默认值 = 0|
|SURVEY_CW_60|用于现场勘测 SSID 的 6 GHz 信道绑定带宽。<br><br>0 - 20兆赫<br><br>1 - 40兆赫<br><br>2 - 80兆赫<br><br>3 - 160兆赫<br><br>默认值 = 0|

诊断命令

|   |   |
|---|---|
|命令|描述|
|fap-tech|显示用于调试目的的统一日志命令输出。|
|cw_diag admin-timeout [30]|设置 shell 空闲超时（以分钟为单位）。|
|cw_diag baudrate [9600 \| 19200 \| 38400 \| 57600 \| 115200]|设置控制台波特率。|
|cw_diag debug ping_ac|启用 AC IP ping 检查并设置 ping 间隔（默认禁用）。|
|cw_diag help|显示所有诊断命令的帮助。|
|cw_diag plain-ctl [0\|1]|显示或更改当前的普通控件设置。|
|cw_diag sniff [0\|1\|2]|启用或禁用嗅探数据包。|
|cw_diag sniff-cfg ip port|设置嗅探服务器 IP 和端口。|
|cw_diag stats wl_intf|显示wl_intf状态。|
|cw_diag uptime|显示守护程序正常运行时间。|
|cw_diag wlanfw-dump <TFTP server IP>|将目标断言日志上传到指定的 TFTP 服务器。|
|cw_diag -c acs-chan-stats|检查CAPWAP与AC控制器的实时连接状态。|
|cw_diag -c ap-scan|显示扫描的 AP。|
|cw_diag -c ap-suppress|显示被禁止的 AP。|
|cw_diag -c arp-req|显示扫描的 arp 请求。|
|cw_diag -c atf|在 FortiAP 级别显示通话时间公平性信息。|
|cw_diag -c ble-scan|显示已扫描的低功耗蓝牙 （BLE） 设备，这些设备已报告给 FortiPresence。|
|cw_diag -c bonjour|在控制平面中显示当前的 Bonjour 网关配置。|
|cw_diag -c darrp|显示 DARRP 无线电频道。|
|cw_diag -c fortipresence|显示 FortiPresence 统计信息，包括报告的 BLE 设备。|
|cw_diag -c k-lan-host|显示连接到 FortiAP LAN2 的客户端的有线客户端信息|
|cw_diag -c k-qos wlan00|验证是否将 vmn-dscp-marking 值推送到 FortiAP。|
|cw_diag -c mesh|显示网格状态。|
|cw_diag -c mesh-ap|显示网状 ap 候选项。|
|cw_diag -c mesh-veth-acinfo|显示网状 veth ac 信息和网状以太类型。|
|cw_diag -c mesh-veth-host|显示网格 veth 主机。|
|cw_diag -c mesh-veth-vap|显示网格 veth vap。|
|cw_diag -c radio-cfg|在控制平面中显示当前的无线电配置参数。|
|cw_diag -c scan-clr-all|刷新所有扫描的 A/STA/ARP。|
|cw_diag -c snmp|显示 SNMP 支持的配置详细信息。|
|cw_diag -c sta-cap|显示扫描的 STA 功能。|
|cw_diag -c sta-deauth|取消对 STA 的身份验证。|
|cw_diag -c sta-scan|显示扫描的 STA。|
|cw_diag -c temperature|显示工作温度。|
|cw_diag -c vap-cfg|在控制平面中显示当前 VAP。|
|cw_diag -c vlan-probe-cmd <action> <interface ID> <start Vlan ID> <end Vlan ID> <retry> <timeout>|启动 VLAN 探测。<br><br>“操作”值列表：<br><br>- 0-开始<br>- 1-停<br><br>示例命令：cw_diag -c vlan-probe-cmd 0 eth0 2 300 3 10<br><br>示例输出：VLAN 探测：start intf [eth0] vlan range[2,300] retries[3] timeout[10] ...|
|cw_diag -c vlan-probe-rpt|显示 VLAN 探测报告。|
|cw_diag -c wids|显示扫描的 WIDS 检测。|
|cw_diag -c wtp-cfg|在控制平面中显示当前的 wtp 配置参数。|
|cw_diag --clog <on\|off>|打开或关闭控制台日志消息。|

来自 <[https://docs.fortinet.com/document/fortiap/7.4.2/fortiwifi-and-fortiap-configuration-guide/65088/fortiap-cli-configuration-and-diagnostics-commands](https://docs.fortinet.com/document/fortiap/7.4.2/fortiwifi-and-fortiap-configuration-guide/65088/fortiap-cli-configuration-and-diagnostics-commands)>