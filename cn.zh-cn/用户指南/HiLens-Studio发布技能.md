# HiLens Studio发布技能<a name="hilens_02_0089"></a>

针对已经在HiLens Studio中调试运行好的技能代码，您可以选择把技能发布到华为HiLens平台的技能市场，平台审核通过后，您分享的技能可供其它用户购买使用。

## 前提条件<a name="section32731194720"></a>

-   保证华为云帐号处于不欠费状态。在华为HiLens控制台发布技能时，会占用OBS资源，需要收取一定费用，收费规则请参见[对象存储服务 OBS](https://www.huaweicloud.com/pricing.html?tab=detail#/obs)。
-   已完成[技能开发](新建技能项目.md)，且技能已完成[代码调试](使用手机实时视频流编写-调试代码.md)，调试结果满足业务诉求。

## 背景信息<a name="section131910248178"></a>

-   发布至华为HiLens 技能市场的技能在3个工作日内审核，审核通过后，发布在华为HiLens技能市场的技能在“技能市场“列表中展示。
-   发布的技能名称不能与华为HiLens技能市场中其他技能重复。

## 发布技能至技能市场<a name="section060212192033"></a>

1.  登录华为HiLens管理控制台，单击左侧导航栏“技能开发\>HiLens Studio“，开始启动HiLens Studio。
2.  在HiLens Studio界面，选择需要发布的技能，单击“Operation“列的“Release“。

    **图 1**  发布技能-34<a name="fig1369533513416"></a>  
    ![](figures/发布技能-34.png "发布技能-34")

    也可以单击项目名称，进入技能项目后，单击HiLens Studio界面右侧![](figures/zh-cn_image_0250541553.png)，在“HiLens  Widget“  区单击“Release“。

    弹出“发布技能“窗口。

    **图 2**  发布技能-35<a name="fig13193330142"></a>  
    ![](figures/发布技能-35.png "发布技能-35")

3.  按[表1](#table1249718511464)设置对应的发布信息，单击“确定“。

    **图 3**  发布技能-36<a name="fig196461118194613"></a>  
    ![](figures/发布技能-36.png "发布技能-36")

    **表 1**  发布至技能市场参数说明

    <a name="table1249718511464"></a>
    <table><thead align="left"><tr id="row16530205120464"><th class="cellrowborder" valign="top" width="32.32%" id="mcps1.2.3.1.1"><p id="p1253012519468"><a name="p1253012519468"></a><a name="p1253012519468"></a>参数字段</p>
    </th>
    <th class="cellrowborder" valign="top" width="67.67999999999999%" id="mcps1.2.3.1.2"><p id="p353075113465"><a name="p353075113465"></a><a name="p353075113465"></a>说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row553095115466"><td class="cellrowborder" valign="top" width="32.32%" headers="mcps1.2.3.1.1 "><p id="p9530195112463"><a name="p9530195112463"></a><a name="p9530195112463"></a>计费策略</p>
    </td>
    <td class="cellrowborder" valign="top" width="67.67999999999999%" headers="mcps1.2.3.1.2 "><p id="p17530185134618"><a name="p17530185134618"></a><a name="p17530185134618"></a>技能发布在技能市场的计费策略。可选择<span class="parmvalue" id="parmvalue53751712165120"><a name="parmvalue53751712165120"></a><a name="parmvalue53751712165120"></a>“免费”</span>和<span class="parmvalue" id="parmvalue14766121485114"><a name="parmvalue14766121485114"></a><a name="parmvalue14766121485114"></a>“收费”</span>。</p>
    </td>
    </tr>
    <tr id="row453095124612"><td class="cellrowborder" valign="top" width="32.32%" headers="mcps1.2.3.1.1 "><p id="p1653085184618"><a name="p1653085184618"></a><a name="p1653085184618"></a>规格限制</p>
    </td>
    <td class="cellrowborder" valign="top" width="67.67999999999999%" headers="mcps1.2.3.1.2 "><p id="p1853045113462"><a name="p1853045113462"></a><a name="p1853045113462"></a>技能在同一设备上最多可以处理视频的路数，或最大并发量。</p>
    </td>
    </tr>
    <tr id="row1153075144614"><td class="cellrowborder" valign="top" width="32.32%" headers="mcps1.2.3.1.1 "><p id="p115300516463"><a name="p115300516463"></a><a name="p115300516463"></a>计量单位</p>
    </td>
    <td class="cellrowborder" valign="top" width="67.67999999999999%" headers="mcps1.2.3.1.2 "><p id="p1753011518465"><a name="p1753011518465"></a><a name="p1753011518465"></a>表示可用在设备上的规格。有<span class="parmvalue" id="parmvalue17672134595114"><a name="parmvalue17672134595114"></a><a name="parmvalue17672134595114"></a>“路数”</span>和<span class="parmvalue" id="parmvalue15031450115117"><a name="parmvalue15031450115117"></a><a name="parmvalue15031450115117"></a>“并发量”</span>两种计量方式。若以<span class="parmvalue" id="parmvalue5612552514"><a name="parmvalue5612552514"></a><a name="parmvalue5612552514"></a>“路数”</span>规格，可安装在设备上使用一路视频。</p>
    </td>
    </tr>
    <tr id="row195301510466"><td class="cellrowborder" valign="top" width="32.32%" headers="mcps1.2.3.1.1 "><p id="p1153045115463"><a name="p1153045115463"></a><a name="p1153045115463"></a>云服务类型</p>
    </td>
    <td class="cellrowborder" rowspan="3" valign="top" width="67.67999999999999%" headers="mcps1.2.3.1.2 "><p id="p18530151174612"><a name="p18530151174612"></a><a name="p18530151174612"></a><span class="parmvalue" id="parmvalue89171359105119"><a name="parmvalue89171359105119"></a><a name="parmvalue89171359105119"></a>“收费”</span>技能需要开发者联系华为HiLens工作人员录入技能产品信息，然后返回一个资源编码，然后把编码填入<span class="parmvalue" id="parmvalue10163156115212"><a name="parmvalue10163156115212"></a><a name="parmvalue10163156115212"></a>“云服务类型”</span>、<span class="parmvalue" id="parmvalue6218131116523"><a name="parmvalue6218131116523"></a><a name="parmvalue6218131116523"></a>“资源类型”</span>、<span class="parmvalue" id="parmvalue5411805215"><a name="parmvalue5411805215"></a><a name="parmvalue5411805215"></a>“资源规格编码”</span>三个字段。</p>
    </td>
    </tr>
    <tr id="row1153019513463"><td class="cellrowborder" valign="top" headers="mcps1.2.3.1.1 "><p id="p10530251164617"><a name="p10530251164617"></a><a name="p10530251164617"></a>资源类型</p>
    </td>
    </tr>
    <tr id="row453085110463"><td class="cellrowborder" valign="top" headers="mcps1.2.3.1.1 "><p id="p175307514461"><a name="p175307514461"></a><a name="p175307514461"></a>资源规格编码</p>
    </td>
    </tr>
    <tr id="row453016511462"><td class="cellrowborder" valign="top" width="32.32%" headers="mcps1.2.3.1.1 "><p id="p2530145124616"><a name="p2530145124616"></a><a name="p2530145124616"></a>隐私声明</p>
    </td>
    <td class="cellrowborder" valign="top" width="67.67999999999999%" headers="mcps1.2.3.1.2 "><p id="p1653045114465"><a name="p1653045114465"></a><a name="p1653045114465"></a>技能涉及到的用户隐私声明。</p>
    </td>
    </tr>
    </tbody>
    </table>

    技能发布成功后，会弹出“发布成功“，发布的技能将展示在华为HiLens控制台的“产品订购\>技能市场“页面。


