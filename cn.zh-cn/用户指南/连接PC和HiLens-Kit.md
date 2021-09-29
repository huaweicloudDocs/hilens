# 连接PC和HiLens Kit<a name="hilens_02_0049"></a>

在注册HiLens Kit至控制台之前，您需要连接PC和HiLens Kit。

## 前提条件<a name="section10466335498"></a>

-   确保您拥有至少一台HiLens Kit设备。
-   确保华为云帐号没有欠费。
-   采用智能边缘系统注册设备，固件版本必须2.2.200.011及以上，如果低于此版本请先[升级系统固件版本](升级HiLens-Kit系统固件版本.md)。

    系统固件版本查询方式：[登录华为HiLens智能边缘管理系统用户界面](https://support.huawei.com/enterprise/zh/doc/EDOC1100133284/1e2e9a10)，进入“维护\>固件升级“页面，查看“当前版本号“。

    全新HiLens Kit硬件，推荐进行固件升级，以获取更好的稳定性。

    如果固件版本低于2.2.200.011，当前仅支持[SSH注册设备](使用SSH注册设备.md)。SSH方式注册成功后，后续您仍可以升级系统固件版本，相关方法和风险参考[升级HiLens Kit系统固件版本](升级HiLens-Kit系统固件版本.md)。

-   使用智能边缘系统注册设备默认注册至北京四区域。

    如果不能接受该限制，请选择[使用SSH注册设备](使用SSH注册设备.md)。如果要注册到其他区域，需要先通过SSH工具修改设备配置参考[切换设备注册区域至北京一（可选）](SSH登录HiLens-Kit设备.md#section191304259256)。


## 网线连接PC与HiLens Kit<a name="section578116398810"></a>

HiLens Kit后面板接口如[图1](#fig062502229)和[表1](#table98731719132214)所示。

**图 1**  后面板接口<a name="fig062502229"></a>  
![](figures/后面板接口.png "后面板接口")

**表 1**  后面板接口说明

<a name="table98731719132214"></a>
<table><thead align="left"><tr id="row28731419142217"><th class="cellrowborder" valign="top" width="33.18%" id="mcps1.2.3.1.1"><p id="p4873101952211"><a name="p4873101952211"></a><a name="p4873101952211"></a>接口</p>
</th>
<th class="cellrowborder" valign="top" width="66.82000000000001%" id="mcps1.2.3.1.2"><p id="p1787319196224"><a name="p1787319196224"></a><a name="p1787319196224"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row1287312194225"><td class="cellrowborder" valign="top" width="33.18%" headers="mcps1.2.3.1.1 "><p id="p487317192224"><a name="p487317192224"></a><a name="p487317192224"></a>1</p>
</td>
<td class="cellrowborder" valign="top" width="66.82000000000001%" headers="mcps1.2.3.1.2 "><p id="p1087351911221"><a name="p1087351911221"></a><a name="p1087351911221"></a>电源开关</p>
</td>
</tr>
<tr id="row1687391962213"><td class="cellrowborder" valign="top" width="33.18%" headers="mcps1.2.3.1.1 "><p id="p10874719112220"><a name="p10874719112220"></a><a name="p10874719112220"></a>2</p>
</td>
<td class="cellrowborder" valign="top" width="66.82000000000001%" headers="mcps1.2.3.1.2 "><p id="p138742019162217"><a name="p138742019162217"></a><a name="p138742019162217"></a>电源接口</p>
</td>
</tr>
<tr id="row1687417194228"><td class="cellrowborder" valign="top" width="33.18%" headers="mcps1.2.3.1.1 "><p id="p14874161916223"><a name="p14874161916223"></a><a name="p14874161916223"></a>3</p>
</td>
<td class="cellrowborder" valign="top" width="66.82000000000001%" headers="mcps1.2.3.1.2 "><p id="p58741119162219"><a name="p58741119162219"></a><a name="p58741119162219"></a>管理网口</p>
</td>
</tr>
</tbody>
</table>

1.  将DC 12V的电源适配器的端口插入HiLens Kit后面板的电源接口。
2.  打开HiLens Kit的电源开关（按住开关键1到2秒放开）。
3.  将网线的一端连接到设备的管理网口上，另一端连接到PC的以太网口上。

## 互通PC与HiLens Kit网络<a name="section1622718539"></a>

设置PC机的IP地址、子网掩码或者路由，使PC机能和设备网络互通。

1.  单击PC右下角网络图标![](figures/zh-cn_image_0266550871.png)，单击“网络和Internet设置“。
2.  在“网络和Internet设置“页面，单击“更改适配器设置“，进入“网络连接“页面。
3.  设置HiLens Kit的网络连接，即HiLens Kit用网线连到PC后，在“网络连接“页面上会显示HiLens Kit对应的网络连接![](figures/zh-cn_image_0266553472.png)，右键单击该网络连接（一般命名为“本地连接“），单击“属性“，弹出“属性“窗口。
4.  在“属性“设置窗口中，双击“Intenet 协议版本4（TCP/IPv4）“，选择“使用下面的IP地址“，在右侧输入框中输入一个和设备**同一个网段**的IP（注：非端侧设备IP），单击“子网掩码“文本框，自动生成子网掩码，单击“确定“，完成网络属性修改。

    设备的初始IP地址请参见[HiLens Kit 用户指南\>默认数据](https://support.huawei.com/enterprise/zh/doc/EDOC1100112066/2347bab9)中“管理网口初始IP地址“的“默认值“。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >-   只有“本地连接属性\>Intenet 协议版本4（TCP/IPv4）\>属性“中的IP和HiLens Kit设备IP在同一网段，才能从电脑SSH连接到HiLens Kit设备。**同一个网段**指本地连接IP的前三段地址要与设备IP一致。例如，设备IP是192.168.2.111，那么与设备IP为同一网段的IP，即“本地连接属性\>Intenet 协议版本4（TCP/IPv4）\>属性“中的IP，可以是192.168.2.x，其中x是2-255中除111之外的整数。
    >-   如果设备IP已修改，此处“本地连接属性\>Intenet 协议版本4（TCP/IPv4）\>属性“中的IP应填写与修改后的设备IP为同一网段的IP。修改IP的具体步骤请见[配置有线网络](https://support.huaweicloud.com/usermanual-hilens/hilens_02_0080.html)。

    **图 2**  修改网络属性<a name="fig1550171195313"></a>  
    ![](figures/修改网络属性.png "修改网络属性")


## 后续操作<a name="section1530164116444"></a>

使用智能边缘系统注册设备需要升级HiLens Kit系统固件版本至2.2.200.011。详情请见[升级HiLens Kit系统固件版本](升级HiLens-Kit系统固件版本.md)。

