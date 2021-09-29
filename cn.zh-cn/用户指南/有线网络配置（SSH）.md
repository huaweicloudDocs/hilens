# 有线网络配置（SSH）<a name="hilens_02_0104"></a>

HiLens Kit有两种组网方式，分为无线和有线两种方式连接路由器，本章介绍有线网络配置方式。

>![](public_sys-resources/icon-note.gif) **说明：** 
>不能同时使用无线网络和有线网络连接同一个路由器，无线连接会自动删除默认网关，再次使用有线网络时需要配置默认网关。**推荐使用无线连接到路由器，以免更新设备IP后遗忘或丢失IP。**
>无线网络配置请参见[无线网络配置（SSH）](无线网络配置（SSH）.md)。

## 配置说明<a name="section1680115213310"></a>

**针对使用有线网络直连路由器的方式，需要修改设备IP，使设备IP与路由器IP在同一网段。**

同一个网段指设备连接IP的前三段地址要与路由器IP一致。例如，设备IP是192.168.2.111，那么路由器IP可以是192.168.2.x，其中x是2-255中除111之外的整数。

## 前提条件<a name="section769233118233"></a>

-   网线连接PC和设备，详细操作请参见[连接PC和HiLens Kit-1](连接PC和HiLens-Kit-1.md)。

## 操作步骤<a name="section1397583520441"></a>

1.  登录华为HiLens智能边缘管理系统，在本地PC中打开浏览器。在地址栏中输入华为HiLens智能边缘管理系统的地址，地址格式为“**https**://_华为HiLens__智能边缘管理系统的访问IP地址_”（默认IP为192.168.2.111）。按“Enter“键。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >如果浏览器显示“此网站的安全证书有问题”，请单击“继续浏览此网站\(不推荐\)”。

2.  在系统登录界面中，配置登录信息。

    在“用户名”和“密码”输入框中输入登录的用户名和密码。

    初识用户名和密码请见[默认数据](https://support.huawei.com/enterprise/zh/doc/EDOC1100112066/2347bab9)。

    **图 1**  登录华为HiLens智能边缘管理系统-7<a name="fig26071839446"></a>  
    ![](figures/登录华为HiLens智能边缘管理系统-7.png "登录华为HiLens智能边缘管理系统-7")

3.  在主菜单中选择“管理\>网络\>有线网络“。

    进入“有线网络“配置页面。

    **图 2**  有线连接路由器-8<a name="fig14701172017471"></a>  
    ![](figures/有线连接路由器-8.png "有线连接路由器-8")

4.  单击检测网络状态后的“检测“，检查网络是否连接。
5.  修改IP地址。
    1.  单击待修改IP地址后的“修改”。
    2.  按[表1](#table3402103588)修改“IP地址“。本示例使用路由器IP是“192.168.2.1“，如[图3](#fig1640315019583)所示，单击“确定“，完成修改设备IP。
    3.  单击“保存“，重启系统，使IP配置生效。

        **表 1**  修改IP参数

        <a name="table3402103588"></a>
        <table><thead align="left"><tr id="row164021200580"><th class="cellrowborder" valign="top" width="25.41%" id="mcps1.2.3.1.1"><p id="p174021304582"><a name="p174021304582"></a><a name="p174021304582"></a>参数</p>
        </th>
        <th class="cellrowborder" valign="top" width="74.59%" id="mcps1.2.3.1.2"><p id="p54021095817"><a name="p54021095817"></a><a name="p54021095817"></a>说明</p>
        </th>
        </tr>
        </thead>
        <tbody><tr id="row1540213017589"><td class="cellrowborder" valign="top" width="25.41%" headers="mcps1.2.3.1.1 "><p id="p94021302589"><a name="p94021302589"></a><a name="p94021302589"></a>用途</p>
        </td>
        <td class="cellrowborder" valign="top" width="74.59%" headers="mcps1.2.3.1.2 "><p id="p1740240135815"><a name="p1740240135815"></a><a name="p1740240135815"></a>IP地址的用途。</p>
        <p id="p174021209584"><a name="p174021209584"></a><a name="p174021209584"></a>支持输入英文、数字和下划线字符，字符串长度1~32个字符。</p>
        </td>
        </tr>
        <tr id="row124021205586"><td class="cellrowborder" valign="top" width="25.41%" headers="mcps1.2.3.1.1 "><p id="p3402602582"><a name="p3402602582"></a><a name="p3402602582"></a>IP地址</p>
        </td>
        <td class="cellrowborder" valign="top" width="74.59%" headers="mcps1.2.3.1.2 "><p id="p24025095815"><a name="p24025095815"></a><a name="p24025095815"></a><span>需要修改的IPv4地址。</span></p>
        <p id="p340218005817"><a name="p340218005817"></a><a name="p340218005817"></a>此处IP地址应和路由器IP在同一网段的IP地址。</p>
        </td>
        </tr>
        <tr id="row240220011588"><td class="cellrowborder" valign="top" width="25.41%" headers="mcps1.2.3.1.1 "><p id="p1740211075818"><a name="p1740211075818"></a><a name="p1740211075818"></a>默认网关</p>
        </td>
        <td class="cellrowborder" valign="top" width="74.59%" headers="mcps1.2.3.1.2 "><p id="p13402170125811"><a name="p13402170125811"></a><a name="p13402170125811"></a>该IP地址对应的默认网关。</p>
        <div class="note" id="note44021605580"><a name="note44021605580"></a><a name="note44021605580"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p1140219017588"><a name="p1140219017588"></a><a name="p1140219017588"></a>请确保默认网关全局唯一。</p>
        </div></div>
        </td>
        </tr>
        </tbody>
        </table>

        **图 3**  修改IP地址-9<a name="fig1640315019583"></a>  
        ![](figures/修改IP地址-9.png "修改IP地址-9")

6.  拔出PC侧网线，断开设备与PC的网线连接，然后网线连接设备与路由器。
7.  连接完成后，SSH登录设备。执行命令检查是否连接成功。

    **ping 8.8.8.8**

    或者

    **ping www.huaweicloud.com**

    如果设备连接成功，其提示信息将显示如下类似信息。

    **图 4**  有线连接提示信息<a name="fig1828701316377"></a>  
    ![](figures/有线连接提示信息.png "有线连接提示信息")

    如果设备连接失败，请执行下一步。

8.  使用SSH远程配置DNS。
    1.  在PuTTY里进入文件

        **vi /etc/resolv.conf**

    2.  删掉原有内容，并修改为

        **nameserver 8.8.8.8**

    3.  如[图5](#fig8505163020373)所示，并保存退出。重新执行上一步检查设备是否连接成功。

        **图 5**  配置DNS内容<a name="fig8505163020373"></a>  
        ![](figures/配置DNS内容.png "配置DNS内容")



## 后续操作<a name="section7091215289"></a>

注册HiLens Kit，详情请见[SSH注册HiLens Kit](SSH注册HiLens-Kit.md)。

