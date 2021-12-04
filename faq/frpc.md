# frpc 常见问题

### 如何通过一个 frpc 开启多条隧道

?> 一个 frpc 只能连接一个 **节点**，但可以连接多条 **隧道**  
详见 [其他常见问题-一个 frpc 可以连接多条隧道吗](/faq/misc#一个-frpc-可以连接多条隧道吗)

如果您使用 **配置文件** 启动 frpc，可以简单的对配置文件进行合并，例如：

<table style="border-style: none;">
<tr style="border-style: none;">
<td style="border-style: none;">
隧道 1 的配置文件如下：

```ini
[common]
server_addr = zz1.mossfrp.cn
server_port = 4000
// 其余部分省略

[MossFrp-2]
type = tcp
local_ip = 127.0.0.1
local_port = 2333
remote_port = 2333
// 其余部分省略
```
</td>
<td style="border-style: none;">
隧道 2 的配置文件如下：

```ini
[common]
server_addr = zz1.mossfrp.cn
server_port = 4000
// 其余部分省略

[MossFrp-1]
type = udp
local_ip = 127.0.0.1
local_port = 520
remote_port = 520
// 其余部分省略
```
</td>
</tr>
</table>
由于两个隧道均位于同一节点，我们可以保留一个 `[common]` 段并将剩余部分合并，得到以下配置文件：

```ini
[common]
server_addr = zz1.mossfrp.cn
server_port = 4000
// 其余部分省略

[MossFrp-1]
type = tcp
local_ip = 127.0.0.1
local_port = 2333
remote_port = 2333
// 其余部分省略

[MossFrp-2]
type = udp
local_ip = 127.0.0.1
local_port = 520
remote_port = 520
// 其余部分省略

```

使用此配置文件启动 frpc，就可以同时连接两条隧道了。

### ARM 运行提示 Illegal instruction

首先，请确认您下载的文件 MD5 与软件下载页面显示的 MD5 相同。

如果您的[架构](usage/linux)显示为 `armv7l`，请下载 `arm_garbage` 版本重试。否则，请联系管理员。

