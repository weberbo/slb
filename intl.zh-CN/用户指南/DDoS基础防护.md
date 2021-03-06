# DDoS基础防护 {#concept_qtj_cqn_vdb .concept}

负载均衡控制台可以查看公网负载均衡实例的云盾阈值。

## DDoS基础防护介绍 {#section_cnq_p3c_wdb .section}

阿里云免费为负载均衡服务提供最高5G的DDoS基础防护。如下图所示，所有来自Internet的流量都要先经过云盾再到达负载均衡，云盾会针对常见的攻击进行清洗过滤。云盾DDoS基础防护可以防御SYN Flood、UDP Flood、ACK Flood、ICMP Flood 和DNS Flood等DDoS攻击。

![](../DNSLB11827830/images/2870_zh-CN.jpeg)

云盾DDoS基础防护根据公网负载均衡实例的带宽设定清洗阈值和黑洞阈值。当入方向流量达到阈值上限时，触发清洗和黑洞：

-   清洗：当来自Internet的攻击流量较大或符合某些特定攻击流量模型特征时，云盾将会针攻击流量启动清洗操作，清洗包括攻击报文过滤、流量限速、包限速等。
-   黑洞：当来自Internet的攻击流量非常大时，为保护整个集群的安全，流量将会被黑洞处理，即所有入流量全部被丢弃。

阈值的计算遵循如下两个原则：

-   根据SLB实例所购买的带宽来决定阈值的高低，即SLB的出方向带宽，当实例的带宽较高时，各类阈值较高，当实例的带宽较低时，各类阈值相应的会变低。
-   根据用户的安全信誉分来决定黑洞阈值的高低。

    **说明：** 注意安全信誉分仅影响黑洞阈值，不影响清洗阈值。


完成以下操作，计算阈值：

1.  SLB后台根据用户购买的带宽给出能够满足实例正常工作的阈值建议值。

    **说明：** 如果用户购买的是按流量计费实例，出带宽为实例所在地域所支持的带宽峰值上限，目前国内地域带宽上限都是峰值5G，详情参见[各地域带宽峰值限制](intl.zh-CN/产品限制/各地域带宽峰值限制.md#)。

    -   SLB带宽与BPS清洗阈值之间的关系
        -   当SLB带宽<100Mbps时，清洗BPS默认阈值 = 120Mbps
        -   当SLB带宽\>100Mbps时，清洗BPS默认阈值 = 带宽值\*1.2
    -   SLB带宽与PPS清洗阈值之间的关系

        清洗PPS阈值 = （SLB带宽值/500）\*150000

        带宽值单位为Mbps。

    -   SLB带宽与黑洞BPS阈值之间的关系
        -   当SLB带宽<1Gbps时，黑洞BPS默认阈值 = 2Gbps
        -   当SLB带宽\>1Gbps时，黑洞BPS默认阈值 = MAX\(SLB带宽值\*1.5,2G\)
2.  云盾根据SLB给出的建议值，结合用户安全信誉分和各地域的资源情况，计算出最终的阈值。
    -   云盾评估BPS和PPS阈值的规则

        BPS最小值为1000M，PPS最小值为30万个。

        -   当SLB传入的参考阈值小于上述最小值时，取上述最小值。
        -   当SLB传入的参考阈值高于上述最小值时，取SLB传入的参考阈值。
    -   云盾根据用户的安全信誉分来决定黑洞阈值的高低。

## 查看防护阈值 {#section_f35_ljc_wdb .section}

使用子账号登录阿里云控制台后，若无法在控制台上查看防护阈值，需要先对子账号授权。详情参见[授予云盾基础防护只读权限](#section_c4n_wjc_wdb)。

完成以下操作查看防护阈值：

1.  登录[负载均衡管理控制台](https://slb.console.aliyun.com/)。
2.  选择地域，查看该地域的所有实例。
3.  将鼠标移至目标实例的云盾图标，查看BPS清洗阈值、PPS清洗阈值和黑洞阈值。您可以单击DDoS控制台链接查看更多信息。
    -   BPS清洗阈值：入方向流量超过了BPS清洗阈值时，触发清洗。
    -   PPS清洗阈值：入方向数据包数超过了PPS清洗阈值时，触发清洗。
    -   黑洞阈值：入方向流量超过黑洞阈值时将触发黑洞。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15694/15452112977339_zh-CN.png)


## 授权云盾基础防护只读权限 {#section_c4n_wjc_wdb .section}

完成以下操作授予子账号只读访问云盾DDoS基础防护\(Anti-DDoS Basic\)的权限：

**说明：** 使用主账号进行授权。

1.  使用主账号登录访问控制RAM管理控制台。
2.  在左侧导航栏，单击**用户管理**，找到目标子账号，然后单击**管理**。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/4157/15452112972872_zh-CN.png)

3.  单击**用户授权策略**，然后单击**编辑授权策略**。
4.  在弹出的对话框，在可授权策略列表中搜索**AliyunYundunDDosReadOnlyAccess**，将其加入到已授权策略列表。单击**确定**。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/4157/15452112972873_zh-CN.png)


## 查看安全信誉分 {#section_chv_cjy_gfb .section}

安全信誉分是阿里云对用户的安全信誉做出的评级，结合历史攻击、会员消费、活跃度、安全等级和使用预期等指标综合给出的一个信用评级，用户的安全信誉等级越高，用户则可以拥有更大的免费黑洞阈值，和更短的黑洞时长（被黑洞后多久可以解除黑洞状态）。

完成以下操作，查看安全信誉分：

1.  登录[DDoS基础防护控制台](https://yundun.console.aliyun.com/?p=ddosnext#/instance/cn-hangzhou)。
2.  选择**基础防护** \> **实例**。
3.  单击**安全信誉**链接，查看当前账号的安全信誉分。

    **说明：** 安全信誉值是分地域的。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15694/154521129712959_zh-CN.png)


