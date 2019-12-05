# 从OBS下载文件<a name="hilens_05_0030"></a>

从OBS下载文件。

-   **接口调用**

    hilens.download\_from\_obs\(url, download\_to\)

-   **参数说明**

    **表 1**  参数说明

    <a name="table13539181462716"></a>
    <table><thead align="left"><tr id="row2540614192716"><th class="cellrowborder" valign="top" width="16.21162116211621%" id="mcps1.2.5.1.1"><p id="p1654016149272"><a name="p1654016149272"></a><a name="p1654016149272"></a><strong id="b42342054117"><a name="b42342054117"></a><a name="b42342054117"></a>参数名</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="16.31163116311631%" id="mcps1.2.5.1.2"><p id="p1319483954019"><a name="p1319483954019"></a><a name="p1319483954019"></a><strong id="b578816214110"><a name="b578816214110"></a><a name="b578816214110"></a>是否必选</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="24.71247124712471%" id="mcps1.2.5.1.3"><p id="p998113813400"><a name="p998113813400"></a><a name="p998113813400"></a><strong id="b923813590407"><a name="b923813590407"></a><a name="b923813590407"></a>参数类型</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="42.76427642764276%" id="mcps1.2.5.1.4"><p id="p1454061414277"><a name="p1454061414277"></a><a name="p1454061414277"></a><strong id="b175919114120"><a name="b175919114120"></a><a name="b175919114120"></a>描述</strong></p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row115403147277"><td class="cellrowborder" valign="top" width="16.21162116211621%" headers="mcps1.2.5.1.1 "><p id="p95401141277"><a name="p95401141277"></a><a name="p95401141277"></a>url</p>
    </td>
    <td class="cellrowborder" valign="top" width="16.31163116311631%" headers="mcps1.2.5.1.2 "><p id="p15195203912405"><a name="p15195203912405"></a><a name="p15195203912405"></a>是</p>
    </td>
    <td class="cellrowborder" valign="top" width="24.71247124712471%" headers="mcps1.2.5.1.3 "><p id="p398283814408"><a name="p398283814408"></a><a name="p398283814408"></a>字符串</p>
    </td>
    <td class="cellrowborder" valign="top" width="42.76427642764276%" headers="mcps1.2.5.1.4 "><p id="p15540914182716"><a name="p15540914182716"></a><a name="p15540914182716"></a>OBS资源的链接。</p>
    </td>
    </tr>
    <tr id="row1354018144275"><td class="cellrowborder" valign="top" width="16.21162116211621%" headers="mcps1.2.5.1.1 "><p id="p17540714152718"><a name="p17540714152718"></a><a name="p17540714152718"></a>download_to</p>
    </td>
    <td class="cellrowborder" valign="top" width="16.31163116311631%" headers="mcps1.2.5.1.2 "><p id="p7195103944011"><a name="p7195103944011"></a><a name="p7195103944011"></a>是</p>
    </td>
    <td class="cellrowborder" valign="top" width="24.71247124712471%" headers="mcps1.2.5.1.3 "><p id="p10982738164015"><a name="p10982738164015"></a><a name="p10982738164015"></a>字符串</p>
    </td>
    <td class="cellrowborder" valign="top" width="42.76427642764276%" headers="mcps1.2.5.1.4 "><p id="p454071419270"><a name="p454071419270"></a><a name="p454071419270"></a>指定文件下载后放置的目录。</p>
    </td>
    </tr>
    </tbody>
    </table>

-   **返回值**

    0为成功，其他为失败。


