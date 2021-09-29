# 导入/转换ModelArts开发模型<a name="hilens_02_0149"></a>

技能可以抽象地理解为算法模型+逻辑代码。算法模型负责关键的AI推理，逻辑代码负责处理模型推理的结果。因此在HiLens Studio开发技能时，需要将模型导入HiLens Studio。

本章节介绍如何将在ModelArts开发的模型导入HiLens Studio，以及针对非“om“格式的模型，如何在HiLens Studio进行模型转换。

## 前提条件<a name="section128954834511"></a>

已在ModelArts在线训练算法模型，训练模型可参见《[ModelArts文档](https://support.huaweicloud.com/engineers-modelarts/modelarts_23_0044.html)》。如果要使用ModelArts的预置算法，当前华为HiLens平台仅支持转换如下预置算法：

-   [yolov3\_resnet18（检测物体类别和位置）](https://support.huaweicloud.com/engineers-modelarts/modelarts_23_0158.html#section1)
-   [ResNet\_v1\_50（图像分类）](https://support.huaweicloud.com/engineers-modelarts/modelarts_23_0158.html#section7)

>![](public_sys-resources/icon-note.gif) **说明：** 
>-   暂不支持导入ModelArts中“自动学习“训练的模型。
>-   华为HiLens 只能导入ModelArts中训练的模型文件，不能导入ModelArts的模型。

## 导入（转换）模型<a name="section152740295517"></a>

1.  在HiLens Studio界面左侧，单击![](figures/zh-cn_image_0000001138665273.png)。

    页面左侧将显示您在ModelArts训练好的模型列表。

    **图 1**  模型列表<a name="fig0601191812210"></a>  
    ![](figures/模型列表.png "模型列表")

2.  选择待导入、转换的模型，单击“Operation“列的“Apply“。
    -   如果是“om“格式的模型，待模型导入成功后，HiLens Studio右下角会提示“Model imported successfully.“，文件夹“model“下会显示新导入的模型文件。
    -   如果是非“om“格式的模型，会弹出“Convert Model“对话框。

        按[表1](#table16577161142912)填写模型转换的信息，单击“OK“。

        **表 1**  Convert Model参数说明

        <a name="table16577161142912"></a>
        <table><thead align="left"><tr id="row115771911102912"><th class="cellrowborder" valign="top" width="19.63%" id="mcps1.2.3.1.1"><p id="p1757731192916"><a name="p1757731192916"></a><a name="p1757731192916"></a>参数</p>
        </th>
        <th class="cellrowborder" valign="top" width="80.36999999999999%" id="mcps1.2.3.1.2"><p id="p757714112297"><a name="p757714112297"></a><a name="p757714112297"></a>说明</p>
        </th>
        </tr>
        </thead>
        <tbody><tr id="row105771011132919"><td class="cellrowborder" valign="top" width="19.63%" headers="mcps1.2.3.1.1 "><p id="p19577171112298"><a name="p19577171112298"></a><a name="p19577171112298"></a>Model Path</p>
        </td>
        <td class="cellrowborder" valign="top" width="80.36999999999999%" headers="mcps1.2.3.1.2 "><p id="p1357719119291"><a name="p1357719119291"></a><a name="p1357719119291"></a>待转换的模型文件在技能项目文件中的位置。一般将模型导入至文件夹<span class="filepath" id="filepath6895122019347"><a name="filepath6895122019347"></a><a name="filepath6895122019347"></a>“save_model”</span>。</p>
        </td>
        </tr>
        <tr id="row85777110293"><td class="cellrowborder" valign="top" width="19.63%" headers="mcps1.2.3.1.1 "><p id="p95771119297"><a name="p95771119297"></a><a name="p95771119297"></a>Configuration</p>
        </td>
        <td class="cellrowborder" valign="top" width="80.36999999999999%" headers="mcps1.2.3.1.2 "><p id="p10577161120294"><a name="p10577161120294"></a><a name="p10577161120294"></a>待转换模型的配置文件在技能项目文件中的位置。例如<span class="filepath" id="filepath22718392515"><a name="filepath22718392515"></a><a name="filepath22718392515"></a>“save_model/aipp_rgb.cfg”</span>。</p>
        </td>
        </tr>
        <tr id="row5577191192911"><td class="cellrowborder" valign="top" width="19.63%" headers="mcps1.2.3.1.1 "><p id="p1257712113294"><a name="p1257712113294"></a><a name="p1257712113294"></a>Output Path</p>
        </td>
        <td class="cellrowborder" valign="top" width="80.36999999999999%" headers="mcps1.2.3.1.2 "><p id="p957713116292"><a name="p957713116292"></a><a name="p957713116292"></a>模型转换后输出位置。</p>
        </td>
        </tr>
        <tr id="row175771711182912"><td class="cellrowborder" valign="top" width="19.63%" headers="mcps1.2.3.1.1 "><p id="p115778111293"><a name="p115778111293"></a><a name="p115778111293"></a>Type</p>
        </td>
        <td class="cellrowborder" valign="top" width="80.36999999999999%" headers="mcps1.2.3.1.2 "><p id="p17577141118290"><a name="p17577141118290"></a><a name="p17577141118290"></a>模型转换的类型，包括<span class="parmname" id="parmname1746010242498"><a name="parmname1746010242498"></a><a name="parmname1746010242498"></a>“TF-FrozenGraph-To-Ascend-HiLens”</span>、<span class="parmname" id="parmname529114280493"><a name="parmname529114280493"></a><a name="parmname529114280493"></a>“Caffe to Ascend”</span>。</p>
        <a name="ul83281052615"></a><a name="ul83281052615"></a><ul id="ul83281052615"><li><span class="parmname" id="parmname1617114814393"><a name="parmname1617114814393"></a><a name="parmname1617114814393"></a>“TF-FrozenGraph-To-Ascend-HiLens”</span><p id="p91524274115"><a name="p91524274115"></a><a name="p91524274115"></a>支持将Tensorflow frozen graph模型转换成可在ascend芯片上运行的模型。</p>
        </li><li><span class="parmname" id="parmname19991754133918"><a name="parmname19991754133918"></a><a name="parmname19991754133918"></a>“Caffe to Ascend”</span><p id="p18561818171214"><a name="p18561818171214"></a><a name="p18561818171214"></a>支持将Caffe模型转换成可在ascend芯片上运行的模型。</p>
        </li></ul>
        </td>
        </tr>
        <tr id="row657715118296"><td class="cellrowborder" valign="top" width="19.63%" headers="mcps1.2.3.1.1 "><p id="p968310433313"><a name="p968310433313"></a><a name="p968310433313"></a>Advanced Options</p>
        </td>
        <td class="cellrowborder" valign="top" width="80.36999999999999%" headers="mcps1.2.3.1.2 "><p id="p557710114297"><a name="p557710114297"></a><a name="p557710114297"></a>当模型转换类型为<span class="parmname" id="parmname15308203564119"><a name="parmname15308203564119"></a><a name="parmname15308203564119"></a>“TF-FrozenGraph-To-Ascend-HiLens”</span>时，可填写高级选项，包括张量形状、转换输出节点等参数选项，详情请见<a href="#table19918847567">表2</a>。</p>
        </td>
        </tr>
        </tbody>
        </table>

        **表 2**  Advanced Options

        <a name="table19918847567"></a>
        <table><thead align="left"><tr id="row1491819412562"><th class="cellrowborder" valign="top" width="28.720000000000002%" id="mcps1.2.3.1.1"><p id="p1991818418566"><a name="p1991818418566"></a><a name="p1991818418566"></a>参数名称</p>
        </th>
        <th class="cellrowborder" valign="top" width="71.28%" id="mcps1.2.3.1.2"><p id="p591820418563"><a name="p591820418563"></a><a name="p591820418563"></a>参数说明</p>
        </th>
        </tr>
        </thead>
        <tbody><tr id="row179181943566"><td class="cellrowborder" valign="top" width="28.720000000000002%" headers="mcps1.2.3.1.1 "><p id="p871810117214"><a name="p871810117214"></a><a name="p871810117214"></a>Input Tensor Shape</p>
        </td>
        <td class="cellrowborder" valign="top" width="71.28%" headers="mcps1.2.3.1.2 "><p id="p392111815543"><a name="p392111815543"></a><a name="p392111815543"></a>输入张量形状。若在上文<span class="parmname" id="parmname99241814547"><a name="parmname99241814547"></a><a name="parmname99241814547"></a>“模型来源”</span>中，选择需要转换格式的模型（非om格式模型），并且转换类型是<span class="parmvalue" id="parmvalue19231810544"><a name="parmvalue19231810544"></a><a name="parmvalue19231810544"></a>“Tensorflow frozen graph 转 Ascend”</span>或<span class="parmvalue" id="parmvalue19923180541"><a name="parmvalue19923180541"></a><a name="parmvalue19923180541"></a>“Tensorflow SavedModel 转 Ascend”</span>时，需要填写输入张量形状。</p>
        <p id="p1473134815588"><a name="p1473134815588"></a><a name="p1473134815588"></a>张量形状即模型输入数据的shape，输入数据格式为NHWC，如<span class="parmvalue" id="parmvalue26131539125915"><a name="parmvalue26131539125915"></a><a name="parmvalue26131539125915"></a>“input_name:1,224,224,3”</span>，必填项。<span class="parmname" id="parmname247354855816"><a name="parmname247354855816"></a><a name="parmname247354855816"></a>“input_name”</span>必须是转换前的网络模型中的节点名称。当模型存在动态shape输入时必须提供。例如<span class="parmname" id="parmname1147319489586"><a name="parmname1147319489586"></a><a name="parmname1147319489586"></a>“input_name1:?,h,w,c”</span>，该参数必填，其中<span class="parmvalue" id="parmvalue178333514591"><a name="parmvalue178333514591"></a><a name="parmvalue178333514591"></a>“?”</span>为batch数，表示1次处理的图片数量，需要根据实际情况填写，用于将动态shape的原始模型转换为固定shape的离线模型。</p>
        <p id="p165045379578"><a name="p165045379578"></a><a name="p165045379578"></a>如果存在多个输入，请以分号（;）隔开。</p>
        </td>
        </tr>
        <tr id="row29181549566"><td class="cellrowborder" valign="top" width="28.720000000000002%" headers="mcps1.2.3.1.1 "><p id="p1555418106408"><a name="p1555418106408"></a><a name="p1555418106408"></a>out_nodes</p>
        </td>
        <td class="cellrowborder" valign="top" width="71.28%" headers="mcps1.2.3.1.2 "><p id="p65541310104017"><a name="p65541310104017"></a><a name="p65541310104017"></a>转换输出节点，即指定输出节点,例如<span class="parmvalue" id="parmvalue14701257318"><a name="parmvalue14701257318"></a><a name="parmvalue14701257318"></a>“node_name1:0;node_name1:1;node_name2:0”</span>，其中<span class="parmvalue" id="parmvalue1647111513318"><a name="parmvalue1647111513318"></a><a name="parmvalue1647111513318"></a>“node_name”</span>必须是模型转换前的网络模型中的节点名称,冒号后的数字表示第几个输出,例如<span class="parmvalue" id="parmvalue1747145833"><a name="parmvalue1747145833"></a><a name="parmvalue1747145833"></a>“node_name1:0”</span>，表示节点名称为<span class="parmvalue" id="parmvalue144711151632"><a name="parmvalue144711151632"></a><a name="parmvalue144711151632"></a>“node_name1”</span>的第0个输出。</p>
        </td>
        </tr>
        <tr id="row99183465617"><td class="cellrowborder" valign="top" width="28.720000000000002%" headers="mcps1.2.3.1.1 "><p id="p9197131824017"><a name="p9197131824017"></a><a name="p9197131824017"></a>input_format</p>
        </td>
        <td class="cellrowborder" valign="top" width="71.28%" headers="mcps1.2.3.1.2 "><p id="p92497924214"><a name="p92497924214"></a><a name="p92497924214"></a>输入数据格式，默认是<span class="parmvalue" id="parmvalue1453810914314"><a name="parmvalue1453810914314"></a><a name="parmvalue1453810914314"></a>“NHWC”</span>,如果实际是<span class="parmvalue" id="parmvalue45391291039"><a name="parmvalue45391291039"></a><a name="parmvalue45391291039"></a>“NCHW”</span>的话,需要通过此参数指定<span class="parmvalue" id="parmvalue19539119838"><a name="parmvalue19539119838"></a><a name="parmvalue19539119838"></a>“NCHW”</span>。</p>
        </td>
        </tr>
        <tr id="row18918154115619"><td class="cellrowborder" valign="top" width="28.720000000000002%" headers="mcps1.2.3.1.1 "><p id="p7523142554011"><a name="p7523142554011"></a><a name="p7523142554011"></a>net_format</p>
        </td>
        <td class="cellrowborder" valign="top" width="71.28%" headers="mcps1.2.3.1.2 "><p id="p105299116454"><a name="p105299116454"></a><a name="p105299116454"></a>优选数据格式，即指定网络算子优先选用的数据格式，<span class="parmvalue" id="parmvalue10539109639"><a name="parmvalue10539109639"></a><a name="parmvalue10539109639"></a>“ND(N=4)”</span>和<span class="parmvalue" id="parmvalue5539391836"><a name="parmvalue5539391836"></a><a name="parmvalue5539391836"></a>“5D”</span>。仅在网络中算子的输入数据同时支持<span class="parmvalue" id="parmvalue125391494311"><a name="parmvalue125391494311"></a><a name="parmvalue125391494311"></a>“ND”</span>和<span class="parmvalue" id="parmvalue195391191636"><a name="parmvalue195391191636"></a><a name="parmvalue195391191636"></a>“5D”</span>两种格式时，指定该参数才生效。<span class="parmvalue" id="parmvalue17539109536"><a name="parmvalue17539109536"></a><a name="parmvalue17539109536"></a>“ND”</span>表示模型中算子按<span class="parmvalue" id="parmvalue1753911914319"><a name="parmvalue1753911914319"></a><a name="parmvalue1753911914319"></a>“NCHW”</span>转换成通用格式，<span class="parmvalue" id="parmvalue35391918320"><a name="parmvalue35391918320"></a><a name="parmvalue35391918320"></a>“5D”</span>表示模型中算子按华为自研的5维转换成华为格式。<span class="parmvalue" id="parmvalue165402091431"><a name="parmvalue165402091431"></a><a name="parmvalue165402091431"></a>“5D”</span>为默认值。</p>
        </td>
        </tr>
        <tr id="row1918142564"><td class="cellrowborder" valign="top" width="28.720000000000002%" headers="mcps1.2.3.1.1 "><p id="p18936427164016"><a name="p18936427164016"></a><a name="p18936427164016"></a>fp16_high_precsion</p>
        </td>
        <td class="cellrowborder" valign="top" width="71.28%" headers="mcps1.2.3.1.2 "><p id="p1066211754619"><a name="p1066211754619"></a><a name="p1066211754619"></a>生成高精度模型，指定是否生成高精度<span class="parmvalue" id="parmvalue13907913418"><a name="parmvalue13907913418"></a><a name="parmvalue13907913418"></a>“FP16 Davinci”</span>模型。</p>
        <a name="ul209184513417"></a><a name="ul209184513417"></a><ul id="ul209184513417"><li>0为默认值，表示生成普通<span class="parmvalue" id="parmvalue1564191215419"><a name="parmvalue1564191215419"></a><a name="parmvalue1564191215419"></a>“FP16 Davinci”</span>模型，推理性能更好。</li><li>1表示生成高精度<span class="parmvalue" id="parmvalue7881161748"><a name="parmvalue7881161748"></a><a name="parmvalue7881161748"></a>“FP16 Davinci”</span>模型，推理精度更好。</li></ul>
        </td>
        </tr>
        <tr id="row1391834125614"><td class="cellrowborder" valign="top" width="28.720000000000002%" headers="mcps1.2.3.1.1 "><p id="p17962329134020"><a name="p17962329134020"></a><a name="p17962329134020"></a>output_type</p>
        </td>
        <td class="cellrowborder" valign="top" width="71.28%" headers="mcps1.2.3.1.2 "><p id="p89621529144012"><a name="p89621529144012"></a><a name="p89621529144012"></a>网络输出数据类型，<span class="parmvalue" id="parmvalue5338114934"><a name="parmvalue5338114934"></a><a name="parmvalue5338114934"></a>“FP32”</span>为默认值,推荐分类网络、检测网络使用；图像超分辨率网络，推荐使用<span class="parmvalue" id="parmvalue18338161414310"><a name="parmvalue18338161414310"></a><a name="parmvalue18338161414310"></a>“UINT8”</span>，推理性能更好。</p>
        </td>
        </tr>
        </tbody>
        </table>



