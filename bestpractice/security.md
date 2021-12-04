# 安全指南

为了防止出现 [这种情况](https://www.v2ex.com/t/692012 ':target=_blank')，我们为您准备了一些安全设定的指南。

## 全球通用的安全准则

1. 对于暴露在网络上的任何东西，密码一定要足够强
1. 保持谦逊是美德，也是保护您不被人攻击的隐身咒
1. 如果您知道一个东西以漏洞闻名，那就为它多加防护
1. 如果没有特殊需求，使用最新版程序通常都是一个好选择  
   尤其是当您使用诸如 WordPress 这类历史悠久的项目时，您遇到陈年老代码带来漏洞的可能性将急速升高  
   请务必打开各个程序自带的更新检测，并总在第一时间进行更新

---

## frpc 访问认证

?> 建议使用 群内最新版本启动器,获得功能的完整体验

启用访问认证后，未经授权的 IP 将无法访问您的隧道，这可以有效回避密码被爆破、遭到 0day 攻击等安全风险

### 注意事项

1. 若当前 IP 因为未认证而被 frpc 拦截，直接访问隧道可能会出现各种奇怪的错误  
   具体现象取决于您穿透的应用，最常见的是连接卡住 (与于隧道不在线类似，但不完全相同)  
   启用此功能后碰到问题请先自行排查是否是未认证造成的问题
1. 重启 frpc 后授权缓存会被清空，因此所有 IP 都需要重新授权


## 远程桌面(RDP) 安全提示

映射远程桌面通常会带来出人意料的风险，因为巨硬的漏洞总是很多


**系统更新是您的朋友，不是敌人。** 如果说有一个东西总是能在暴露的风险中拯救您，那一定是阻断药……啊不，系统更新。

系统更新可能会迟到，但是只要到达，它总是能为守护您的电脑奉上您需要的力量。

如果您因为一些理由关闭了系统更新，请不要以任何形式把自己暴露在网络中。