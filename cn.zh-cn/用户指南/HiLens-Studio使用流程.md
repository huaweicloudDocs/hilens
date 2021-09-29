# HiLens Studio使用流程<a name="hilens_02_0086"></a>

HiLens Studio 是一个提供给开发者的多语言类集成开发环境，包括代码编辑器、编译器、调试器等，开发者可以在HiLens Studio 中编写和调试技能代码。针对调试好的技能代码，开发者也可以在HiLens Studio中发布技能、部署并运行技能到端侧设备上。

>![](public_sys-resources/icon-note.gif) **说明：** 
>HiLens Studio当前支持Python 3.7和C++技能的开发、调试。

## 功能介绍<a name="section948951294712"></a>

HiLens Studio界面如[图1](#fig19734153464515)所示，功能介绍请参见[图1](#fig19734153464515)和[表1](#table104748295414)。

**图 1**  HiLens Studio界面<a name="fig19734153464515"></a>  
![](figures/HiLens-Studio界面.png "HiLens-Studio界面")

**表 1**  功能区域介绍

<a name="table104748295414"></a>
<table><thead align="left"><tr id="row204758211544"><th class="cellrowborder" valign="top" id="mcps1.2.4.1.1"><p id="p7475162155417"><a name="p7475162155417"></a><a name="p7475162155417"></a>区域</p>
</th>
<th class="cellrowborder" colspan="2" valign="top" id="mcps1.2.4.1.2"><p id="p1947513210543"><a name="p1947513210543"></a><a name="p1947513210543"></a>功能说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row7475522547"><td class="cellrowborder" rowspan="4" valign="top" headers="mcps1.2.4.1.1 "><p id="p15475102115418"><a name="p15475102115418"></a><a name="p15475102115418"></a>1</p>
<p id="p993351613578"><a name="p993351613578"></a><a name="p993351613578"></a></p>
<p id="p3663193045814"><a name="p3663193045814"></a><a name="p3663193045814"></a></p>
<p id="p127232581763"><a name="p127232581763"></a><a name="p127232581763"></a></p>
</td>
<td class="cellrowborder" colspan="2" valign="top" headers="mcps1.2.4.1.2 "><p id="p331521614318"><a name="p331521614318"></a><a name="p331521614318"></a>单击<a name="image1362871512018"></a><a name="image1362871512018"></a><span><img id="image1362871512018" src="figures/zh-cn_image_0250530700.png" width="12.847534000000001" height="14.619626000000002"></span>查看开发项目的文件目录，详情请参见<a href="使用手机实时视频流编写-调试代码.md#section31895539159">项目文件目录说明</a>。</p>
</td>
</tr>
<tr id="row3933916205717"><td class="cellrowborder" colspan="2" valign="top" headers="mcps1.2.4.1.2 "><p id="p1093351617575"><a name="p1093351617575"></a><a name="p1093351617575"></a>单击<a name="image19895104417013"></a><a name="image19895104417013"></a><span><img id="image19895104417013" src="figures/zh-cn_image_0250530848.png" width="12.187189" height="13.622126000000002"></span>可在搜索框中搜索您想要查看的项目内容。</p>
</td>
</tr>
<tr id="row10662630175813"><td class="cellrowborder" colspan="2" valign="top" headers="mcps1.2.4.1.2 "><p id="p14663133035811"><a name="p14663133035811"></a><a name="p14663133035811"></a>单击<a name="image1064112711116"></a><a name="image1064112711116"></a><span><img id="image1064112711116" src="figures/zh-cn_image_0252544794.png" width="15.150961" height="19.607126"></span>查看代码来源。</p>
</td>
</tr>
<tr id="row072235813611"><td class="cellrowborder" colspan="2" valign="top" headers="mcps1.2.4.1.2 "><p id="p1772317585618"><a name="p1772317585618"></a><a name="p1772317585618"></a>单击<a name="image133561888141"></a><a name="image133561888141"></a><span><img id="image133561888141" src="figures/zh-cn_image_0250536297.png" width="17.103268" height="16.614626"></span>在该页签下可调试技能代码，详情请参见<a href="使用手机实时视频流编写-调试代码.md#section343343721619"> 断点调试代码</a>。</p>
</td>
</tr>
<tr id="row54755216543"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p16475820544"><a name="p16475820544"></a><a name="p16475820544"></a>2</p>
</td>
<td class="cellrowborder" colspan="2" valign="top" headers="mcps1.2.4.1.2 "><p id="p134754265413"><a name="p134754265413"></a><a name="p134754265413"></a>代码编辑区，可在该区域内直接编辑代码。</p>
</td>
</tr>
<tr id="row19475924545"><td class="cellrowborder" rowspan="2" valign="top" headers="mcps1.2.4.1.1 "><p id="p647522165414"><a name="p647522165414"></a><a name="p647522165414"></a>3</p>
<p id="p354848204"><a name="p354848204"></a><a name="p354848204"></a></p>
</td>
<td class="cellrowborder" colspan="2" valign="top" headers="mcps1.2.4.1.2 "><p id="p347510217544"><a name="p347510217544"></a><a name="p347510217544"></a>单击<a name="image12562165810145"></a><a name="image12562165810145"></a><span><img id="image12562165810145" src="figures/zh-cn_image_0250536481.png" width="21.749357000000003" height="20.604626000000003"></span>切换至该页签，可针对当前编辑好的技能代码<a href="HiLens-Studio发布技能.md">发布技能</a>、<a href="HiLens-Studio安装技能.md">安装技能</a>和<a href="HiLens-Studio启动或停止技能.md">启动技能</a>。</p>
</td>
</tr>
<tr id="row15481188018"><td class="cellrowborder" colspan="2" valign="top" headers="mcps1.2.4.1.2 "><p id="p354818304"><a name="p354818304"></a><a name="p354818304"></a>单击<a name="image691222119158"></a><a name="image691222119158"></a><span><img id="image691222119158" src="figures/zh-cn_image_0250536711.png" width="22.845011000000003" height="16.614626"></span>切换至该页签，查看当前文件概览。</p>
</td>
</tr>
<tr id="row44752235417"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p54755225411"><a name="p54755225411"></a><a name="p54755225411"></a>4</p>
</td>
<td class="cellrowborder" colspan="2" valign="top" headers="mcps1.2.4.1.2 "><p id="p1447517210544"><a name="p1447517210544"></a><a name="p1447517210544"></a>调试区，可在该区域内查看代码调试结果。</p>
</td>
</tr>
</tbody>
</table>

## 使用HiLens Studio 开发技能<a name="section1618620412136"></a>

本章节介绍在HiLens Studio开发技能。

使用HiLens Studio开发技能流程如[图2](#fig261128121615)所示，流程说明请参见[表2](#table10326435153411)。

>![](public_sys-resources/icon-note.gif) **说明：** 
>本章节仅介绍在HiLens Studio中开发技能所涉及的操作。在控制台新建技能的具体操作请参见[控制台开发技能](控制台开发技能.md)。

**图 2**  使用HiLens Studio 开发技能流程<a name="fig261128121615"></a>  
![](figures/使用HiLens-Studio-开发技能流程.png "使用HiLens-Studio-开发技能流程")

**表 2**  使用HiLens Studio 开发技能流程说明

<a name="table10326435153411"></a>
<table><thead align="left"><tr id="row13275352343"><th class="cellrowborder" valign="top" width="22.24222422242224%" id="mcps1.2.4.1.1"><p id="p13327535163413"><a name="p13327535163413"></a><a name="p13327535163413"></a>流程</p>
</th>
<th class="cellrowborder" valign="top" width="44.42444244424442%" id="mcps1.2.4.1.2"><p id="p14327035183414"><a name="p14327035183414"></a><a name="p14327035183414"></a>说明</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.3"><p id="p1032714357348"><a name="p1032714357348"></a><a name="p1032714357348"></a>详细指导</p>
</th>
</tr>
</thead>
<tbody><tr id="row13775521210"><td class="cellrowborder" valign="top" width="22.24222422242224%" headers="mcps1.2.4.1.1 "><p id="p1117303493919"><a name="p1117303493919"></a><a name="p1117303493919"></a>准备工作</p>
</td>
<td class="cellrowborder" valign="top" width="44.42444244424442%" headers="mcps1.2.4.1.2 "><a name="ul14532341184712"></a><a name="ul14532341184712"></a><ul id="ul14532341184712"><li>购买HiLens Kit<p id="p12927125810488"><a name="p12927125810488"></a><a name="p12927125810488"></a>将开发好的技能安装至设备前提条件是购买HiLens  Kit设备。</p>
</li><li>购买HiLens端边云协同平台服务并激活设备<p id="p35701239115011"><a name="p35701239115011"></a><a name="p35701239115011"></a>当您注册的设备超过1台时，需购买HiLens端边云协同平台服务，在设备管理页面对指定设备进行权限激活后，该设备即可安装您自行开发的技能。</p>
</li></ul>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p317310343397"><a name="p317310343397"></a><a name="p317310343397"></a><a href="订购HiLens-Kit.md">订购HiLens Kit</a></p>
<p id="p12301151512484"><a name="p12301151512484"></a><a name="p12301151512484"></a><a href="订购HiLens端边云协同平台服务.md">订购HiLens端边云协同平台服务</a></p>
<p id="p1764472314813"><a name="p1764472314813"></a><a name="p1764472314813"></a><a href="激活设备（购买端边云协同平台服务）.md">激活设备（购买端边云协同平台服务）</a></p>
</td>
</tr>
<tr id="row9327103593413"><td class="cellrowborder" valign="top" width="22.24222422242224%" headers="mcps1.2.4.1.1 "><p id="p33275354344"><a name="p33275354344"></a><a name="p33275354344"></a>连接端侧和云侧</p>
</td>
<td class="cellrowborder" valign="top" width="44.42444244424442%" headers="mcps1.2.4.1.2 "><p id="p18327183543415"><a name="p18327183543415"></a><a name="p18327183543415"></a>首先，连接您购买的HiLens Kit，并将<span id="text1753953112810"><a name="text1753953112810"></a><a name="text1753953112810"></a>HiLens Kit</span>注册到华为HiLens平台，连接端侧与云侧。</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p1753919322811"><a name="p1753919322811"></a><a name="p1753919322811"></a><a href="HiLens-Kit注册流程.md">HiLens Kit注册流程</a></p>
<p id="p103114268452"><a name="p103114268452"></a><a name="p103114268452"></a><a href="智能边缘系统注册设备.md">智能边缘系统注册设备</a></p>
<p id="p105319359458"><a name="p105319359458"></a><a name="p105319359458"></a><a href="使用SSH注册设备.md">使用SSH注册设备</a></p>
</td>
</tr>
<tr id="row173277352341"><td class="cellrowborder" valign="top" width="22.24222422242224%" headers="mcps1.2.4.1.1 "><p id="p732793553419"><a name="p732793553419"></a><a name="p732793553419"></a>开发技能</p>
</td>
<td class="cellrowborder" valign="top" width="44.42444244424442%" headers="mcps1.2.4.1.2 "><p id="p1632717355349"><a name="p1632717355349"></a><a name="p1632717355349"></a>使用HiLens Studio开发技能，开发者可以新建技能项目，在HiLens Studio编写和调试技能代码，针对HDMI输出的技能，在HiLens Studio中还可以运行技能并查看输出数据。</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p474416401677"><a name="p474416401677"></a><a name="p474416401677"></a><a href="新建技能项目.md">新建技能项目</a></p>
<p id="p326715428467"><a name="p326715428467"></a><a name="p326715428467"></a><a href="管理模型.md">管理模型</a></p>
<p id="p6879195014110"><a name="p6879195014110"></a><a name="p6879195014110"></a><a href="使用手机实时视频流编写-调试代码.md">使用手机实时视频流编写/调试代码</a></p>
</td>
</tr>
<tr id="row23274359349"><td class="cellrowborder" valign="top" width="22.24222422242224%" headers="mcps1.2.4.1.1 "><p id="p53273355346"><a name="p53273355346"></a><a name="p53273355346"></a>安装技能</p>
</td>
<td class="cellrowborder" valign="top" width="44.42444244424442%" headers="mcps1.2.4.1.2 "><p id="p8327103553419"><a name="p8327103553419"></a><a name="p8327103553419"></a>在HiLens Studio中编辑完技能代码，可以直接把技能安装到设备上。</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p1332713523412"><a name="p1332713523412"></a><a name="p1332713523412"></a><a href="HiLens-Studio安装技能.md">HiLens Studio安装技能</a></p>
</td>
</tr>
<tr id="row15327203553412"><td class="cellrowborder" valign="top" width="22.24222422242224%" headers="mcps1.2.4.1.1 "><p id="p3327735153416"><a name="p3327735153416"></a><a name="p3327735153416"></a>启动技能</p>
</td>
<td class="cellrowborder" valign="top" width="44.42444244424442%" headers="mcps1.2.4.1.2 "><p id="p1332718355348"><a name="p1332718355348"></a><a name="p1332718355348"></a>把技能安装至设备后，可以直接在HiLens Studio中启动技能，查看技能运行效果。</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p0327203593420"><a name="p0327203593420"></a><a name="p0327203593420"></a><a href="HiLens-Studio启动或停止技能.md">HiLens Studio启动或停止技能</a></p>
</td>
</tr>
<tr id="row17327635203410"><td class="cellrowborder" valign="top" width="22.24222422242224%" headers="mcps1.2.4.1.1 "><p id="p12327035163411"><a name="p12327035163411"></a><a name="p12327035163411"></a>发布技能</p>
</td>
<td class="cellrowborder" valign="top" width="44.42444244424442%" headers="mcps1.2.4.1.2 "><p id="p123271035183414"><a name="p123271035183414"></a><a name="p123271035183414"></a>针对已经调试好的技能，可以在HiLens Studio中发布技能至华为HiLens平台技能市场，供其他用户使用。</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p17327173593416"><a name="p17327173593416"></a><a name="p17327173593416"></a><a href="HiLens-Studio发布技能.md">HiLens Studio发布技能</a></p>
</td>
</tr>
</tbody>
</table>

