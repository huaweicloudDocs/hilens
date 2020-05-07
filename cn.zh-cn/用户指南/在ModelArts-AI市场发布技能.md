# 在ModelArts AI市场发布技能<a name="hilens_02_0077"></a>

开发者完成技能的开发、调试后，可以把自己的技能分享发布至ModelArts AI市场中，同时您可以设置相关费用，基于其他用户的订购，可收到相应的报酬。

## 前提条件<a name="section32731194720"></a>

-   已完成[技能开发](新建技能.md)，且技能已完成[安装调试](部署和调试技能.md)，调试结果满足业务诉求。

## 发布技能<a name="section18884121511187"></a>

1.  进入[ModelArts控制台](https://console.huaweicloud.com/modelarts/?region=cn-north-4#/dashboard)，单击左侧导航栏的“AI市场“，系统默认进入“ModelHub\>公共“页签。
2.  单击“新建“，进入“新建云端模型“页面。
3.  按[表1](#table124211163244)填写技能的相关信息，然后单击“立即创建“。

    **表 1**  参数说明

    <a name="table124211163244"></a>
    <table><thead align="left"><tr id="row34261642417"><th class="cellrowborder" valign="top" width="27.93%" id="mcps1.2.3.1.1"><p id="p342141619242"><a name="p342141619242"></a><a name="p342141619242"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="72.07000000000001%" id="mcps1.2.3.1.2"><p id="p142716122413"><a name="p142716122413"></a><a name="p142716122413"></a>说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row94231614241"><td class="cellrowborder" valign="top" width="27.93%" headers="mcps1.2.3.1.1 "><p id="p188081740709"><a name="p188081740709"></a><a name="p188081740709"></a><span class="parmname" id="parmname119428381124"><a name="parmname119428381124"></a><a name="parmname119428381124"></a>“商品类别”</span></p>
    </td>
    <td class="cellrowborder" valign="top" width="72.07000000000001%" headers="mcps1.2.3.1.2 "><p id="p385866103119"><a name="p385866103119"></a><a name="p385866103119"></a>选择HiLens技能，可用于Huawei HiLens服务。</p>
    </td>
    </tr>
    <tr id="row14241662419"><td class="cellrowborder" valign="top" width="27.93%" headers="mcps1.2.3.1.1 "><p id="p280819401004"><a name="p280819401004"></a><a name="p280819401004"></a><span class="parmname" id="parmname570055119404"><a name="parmname570055119404"></a><a name="parmname570055119404"></a>“商品标题”</span></p>
    </td>
    <td class="cellrowborder" valign="top" width="72.07000000000001%" headers="mcps1.2.3.1.2 "><p id="p128085406010"><a name="p128085406010"></a><a name="p128085406010"></a>在市场显示的技能名称，建议按照您的技能实现目的设置。</p>
    </td>
    </tr>
    <tr id="row5425164245"><td class="cellrowborder" valign="top" width="27.93%" headers="mcps1.2.3.1.1 "><p id="p18082401408"><a name="p18082401408"></a><a name="p18082401408"></a><span class="parmname" id="parmname127025516402"><a name="parmname127025516402"></a><a name="parmname127025516402"></a>“HiLens区域”</span></p>
    </td>
    <td class="cellrowborder" valign="top" width="72.07000000000001%" headers="mcps1.2.3.1.2 "><p id="p158085405013"><a name="p158085405013"></a><a name="p158085405013"></a>目前Huawei HiLens只支持<span class="parmname" id="parmname206199231620"><a name="parmname206199231620"></a><a name="parmname206199231620"></a>“cn-north-1”</span>和<span class="parmname" id="parmname0142726420"><a name="parmname0142726420"></a><a name="parmname0142726420"></a>“cn-north-4”</span>，因此此参数的可选值只有这两个。</p>
    </td>
    </tr>
    <tr id="row142616192410"><td class="cellrowborder" valign="top" width="27.93%" headers="mcps1.2.3.1.1 "><p id="p68088401018"><a name="p68088401018"></a><a name="p68088401018"></a><span class="parmname" id="parmname0509348154316"><a name="parmname0509348154316"></a><a name="parmname0509348154316"></a>“技能名称”</span></p>
    </td>
    <td class="cellrowborder" valign="top" width="72.07000000000001%" headers="mcps1.2.3.1.2 "><p id="p97791329121"><a name="p97791329121"></a><a name="p97791329121"></a>选择技能的名称。搜索的技能名称来源于Huawei HiLens控制台的<span class="parmname" id="parmname12250125713124"><a name="parmname12250125713124"></a><a name="parmname12250125713124"></a>“技能开发&gt;技能管理”</span>，并快速获取您发布的技能。</p>
    </td>
    </tr>
    <tr id="row1443171642416"><td class="cellrowborder" valign="top" width="27.93%" headers="mcps1.2.3.1.1 "><p id="p138084401105"><a name="p138084401105"></a><a name="p138084401105"></a><span class="parmname" id="parmname135091948104318"><a name="parmname135091948104318"></a><a name="parmname135091948104318"></a>“技能版本”</span></p>
    </td>
    <td class="cellrowborder" valign="top" width="72.07000000000001%" headers="mcps1.2.3.1.2 "><p id="p580817401201"><a name="p580817401201"></a><a name="p580817401201"></a>在选择对应的技能后，系统自动获取技能版本。此处的<span class="parmname" id="parmname75091948154317"><a name="parmname75091948154317"></a><a name="parmname75091948154317"></a>“技能版本”</span>和<span class="parmname" id="parmname19509248194317"><a name="parmname19509248194317"></a><a name="parmname19509248194317"></a>“技能名称”</span>与Huawei HiLens的<span class="parmname" id="parmname14510648144312"><a name="parmname14510648144312"></a><a name="parmname14510648144312"></a>“技能管理”</span>页面一致。</p>
    </td>
    </tr>
    <tr id="row5431916122413"><td class="cellrowborder" valign="top" width="27.93%" headers="mcps1.2.3.1.1 "><p id="p1545103114212"><a name="p1545103114212"></a><a name="p1545103114212"></a><span class="parmname" id="parmname551024884313"><a name="parmname551024884313"></a><a name="parmname551024884313"></a>“技能ID”</span></p>
    </td>
    <td class="cellrowborder" valign="top" width="72.07000000000001%" headers="mcps1.2.3.1.2 "><p id="p1054514311622"><a name="p1054514311622"></a><a name="p1054514311622"></a>系统自动定义，根据您选择<span class="parmname" id="parmname1451016485439"><a name="parmname1451016485439"></a><a name="parmname1451016485439"></a>“技能名称”</span>和<span class="parmname" id="parmname195101148154315"><a name="parmname195101148154315"></a><a name="parmname195101148154315"></a>“技能版本”</span>会显示其详细对应的ID。</p>
    </td>
    </tr>
    <tr id="row44381616244"><td class="cellrowborder" valign="top" width="27.93%" headers="mcps1.2.3.1.1 "><p id="p75467319219"><a name="p75467319219"></a><a name="p75467319219"></a><span class="parmname" id="parmname1570845154011"><a name="parmname1570845154011"></a><a name="parmname1570845154011"></a>“所有者”</span></p>
    </td>
    <td class="cellrowborder" valign="top" width="72.07000000000001%" headers="mcps1.2.3.1.2 "><p id="p14546031828"><a name="p14546031828"></a><a name="p14546031828"></a>此技能的拥有者名称。此处不可编辑。</p>
    </td>
    </tr>
    <tr id="row526732311304"><td class="cellrowborder" valign="top" width="27.93%" headers="mcps1.2.3.1.1 "><p id="p165461531622"><a name="p165461531622"></a><a name="p165461531622"></a><span class="parmname" id="parmname070918513404"><a name="parmname070918513404"></a><a name="parmname070918513404"></a>“权限”</span></p>
    </td>
    <td class="cellrowborder" valign="top" width="72.07000000000001%" headers="mcps1.2.3.1.2 "><p id="p954613314218"><a name="p954613314218"></a><a name="p954613314218"></a>设置此技能的公开权限。可选：<span class="parmname" id="parmname1174820824017"><a name="parmname1174820824017"></a><a name="parmname1174820824017"></a>“公开”</span>、<span class="parmname" id="parmname0210151174013"><a name="parmname0210151174013"></a><a name="parmname0210151174013"></a>“私有”</span>或者<span class="parmname" id="parmname1739313924012"><a name="parmname1739313924012"></a><a name="parmname1739313924012"></a>“白名单用户组”</span>。</p>
    <a name="ul1391317012413"></a><a name="ul1391317012413"></a><ul id="ul1391317012413"><li><span class="parmname" id="parmname1864732110405"><a name="parmname1864732110405"></a><a name="parmname1864732110405"></a>“公开”</span>：表示所有可以使用AI市场的用户都可以看到并使用您的技能。</li><li><span class="parmname" id="parmname695042394020"><a name="parmname695042394020"></a><a name="parmname695042394020"></a>“私有”</span>：表示只有当前账号可以使用此技能。</li><li><span class="parmname" id="parmname1776913613404"><a name="parmname1776913613404"></a><a name="parmname1776913613404"></a>“白名单用户组”</span>：针对ModelArts白名单列表的用户，都可以使用您新建的技能。</li></ul>
    </td>
    </tr>
    </tbody>
    </table>

    技能创建成功后，技能将展示在ModelArtsAI市场的“ModelHub\>我的发布“页面。


## 查看我的技能<a name="section12192652114815"></a>

如果您已经有将技能发布至AI市场，那么您可以进入ModelArtsAI市场的“ModelHub \> 我的发布“页面，查看您发布的技能。可单击技能进入技能详情页。

## 编辑已发布的技能<a name="section7171556161411"></a>

如果您已经将技能发布至AI市场，您可以进入ModelArtsAI市场的“ModelHub \> 我的发布“页面，编辑发布技能的描述、价格、版本等信息。编辑“价格“后，基于其他用户的订购，您可收到相应的报酬。

1.  在ModelArtsAI市场的“ModelHub \> 我的发布“页面，选择并单击您所发布的技能卡片，进入技能详情页。
2.  在技能详情页，单击“描述“、“价格“、“版本“各个区域右上角的编辑，对技能的各个特性进行编辑。

## 查看我的售出<a name="section1980697165115"></a>

针对您发布的技能，您可以查看您的技能售出至哪些订单。

进入[AI市场订阅中心](https://support.huaweicloud.com/engineers-modelarts/modelarts_23_0171.html#modelarts_23_0171__section84714813227)，单击“我的售出“，默认可查看相关的订单列表。

