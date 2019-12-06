# Skill Framework简介<a name="hilens_05_0002"></a>

Skill Framework通过封装底层接口、实现常用的管理功能，让开发者可以在Huawei HiLens管理控制台上方便地开发技能，培育AI生态。

Skill Framework的分层结构如[图1](#fig8310203618820)所示，Skill Framework封装了底层的多媒体处理库（摄像头/麦克风驱动模块Media\_mini），以及D芯片相关的图像处理库（DVPP）和模型管理库（ModelManager），另外开发者也可以使用熟悉的视觉处理库OpenCV。在此之上，Skill Framework提供了以下6个模块供开发者使用，方便开发诸如人形检测、人脸识别、疲劳驾驶检测等技能，模块说明如下表[模块说明](#table173537486322)。

**图 1**  Skill Framework框架<a name="fig8310203618820"></a>  
![](figures/Skill-Framework框架.png "Skill-Framework框架")

**表 1**  模块说明

<a name="table173537486322"></a>
<table><thead align="left"><tr id="row193536481323"><th class="cellrowborder" valign="top" width="6.09%" id="mcps1.2.4.1.1"><p id="p1535319486328"><a name="p1535319486328"></a><a name="p1535319486328"></a>序号</p>
</th>
<th class="cellrowborder" valign="top" width="23.95%" id="mcps1.2.4.1.2"><p id="p123531048123214"><a name="p123531048123214"></a><a name="p123531048123214"></a>模块</p>
</th>
<th class="cellrowborder" valign="top" width="69.96%" id="mcps1.2.4.1.3"><p id="p4353144873214"><a name="p4353144873214"></a><a name="p4353144873214"></a>功能</p>
</th>
</tr>
</thead>
<tbody><tr id="row53539488325"><td class="cellrowborder" valign="top" width="6.09%" headers="mcps1.2.4.1.1 "><p id="p735310482327"><a name="p735310482327"></a><a name="p735310482327"></a>1</p>
</td>
<td class="cellrowborder" valign="top" width="23.95%" headers="mcps1.2.4.1.2 "><p id="p1335394820321"><a name="p1335394820321"></a><a name="p1335394820321"></a>Input Manager</p>
</td>
<td class="cellrowborder" valign="top" width="69.96%" headers="mcps1.2.4.1.3 "><p id="p183538487328"><a name="p183538487328"></a><a name="p183538487328"></a>负责视频、音频等输入数据的接入管理。</p>
</td>
</tr>
<tr id="row5353174810321"><td class="cellrowborder" valign="top" width="6.09%" headers="mcps1.2.4.1.1 "><p id="p1535312484323"><a name="p1535312484323"></a><a name="p1535312484323"></a>2</p>
</td>
<td class="cellrowborder" valign="top" width="23.95%" headers="mcps1.2.4.1.2 "><p id="p163534482329"><a name="p163534482329"></a><a name="p163534482329"></a>Media Processor</p>
</td>
<td class="cellrowborder" valign="top" width="69.96%" headers="mcps1.2.4.1.3 "><p id="p11353194853210"><a name="p11353194853210"></a><a name="p11353194853210"></a>负责视频、音频等媒体数据的处理。</p>
</td>
</tr>
<tr id="row235314481328"><td class="cellrowborder" valign="top" width="6.09%" headers="mcps1.2.4.1.1 "><p id="p12353948103213"><a name="p12353948103213"></a><a name="p12353948103213"></a>3</p>
</td>
<td class="cellrowborder" valign="top" width="23.95%" headers="mcps1.2.4.1.2 "><p id="p0353248173216"><a name="p0353248173216"></a><a name="p0353248173216"></a>Model Manager</p>
</td>
<td class="cellrowborder" valign="top" width="69.96%" headers="mcps1.2.4.1.3 "><p id="p123539485325"><a name="p123539485325"></a><a name="p123539485325"></a>负责模型的初始化与推断任务。</p>
</td>
</tr>
<tr id="row9353204813323"><td class="cellrowborder" valign="top" width="6.09%" headers="mcps1.2.4.1.1 "><p id="p1435324818328"><a name="p1435324818328"></a><a name="p1435324818328"></a>4</p>
</td>
<td class="cellrowborder" valign="top" width="23.95%" headers="mcps1.2.4.1.2 "><p id="p43532481329"><a name="p43532481329"></a><a name="p43532481329"></a>Output Manager</p>
</td>
<td class="cellrowborder" valign="top" width="69.96%" headers="mcps1.2.4.1.3 "><p id="p183531748173216"><a name="p183531748173216"></a><a name="p183531748173216"></a>负责流、文件、消息通知等输出任务的管理。</p>
</td>
</tr>
<tr id="row935344814321"><td class="cellrowborder" valign="top" width="6.09%" headers="mcps1.2.4.1.1 "><p id="p735384873216"><a name="p735384873216"></a><a name="p735384873216"></a>5</p>
</td>
<td class="cellrowborder" valign="top" width="23.95%" headers="mcps1.2.4.1.2 "><p id="p14353124863219"><a name="p14353124863219"></a><a name="p14353124863219"></a>Resource Manager</p>
</td>
<td class="cellrowborder" valign="top" width="69.96%" headers="mcps1.2.4.1.3 "><p id="p135394811329"><a name="p135394811329"></a><a name="p135394811329"></a>负责文件、图片、模型等资源的路径管理。</p>
</td>
</tr>
<tr id="row935364811328"><td class="cellrowborder" valign="top" width="6.09%" headers="mcps1.2.4.1.1 "><p id="p6353194811323"><a name="p6353194811323"></a><a name="p6353194811323"></a>6</p>
</td>
<td class="cellrowborder" valign="top" width="23.95%" headers="mcps1.2.4.1.2 "><p id="p1235384893217"><a name="p1235384893217"></a><a name="p1235384893217"></a>Logging System</p>
</td>
<td class="cellrowborder" valign="top" width="69.96%" headers="mcps1.2.4.1.3 "><p id="p203531848123217"><a name="p203531848123217"></a><a name="p203531848123217"></a>负责日志系统管理。</p>
</td>
</tr>
</tbody>
</table>

