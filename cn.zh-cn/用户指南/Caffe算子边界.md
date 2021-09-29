# Caffe算子边界<a name="hilens_02_0059"></a>

对于Caffe框架，当算子的输入维度不是4时，如果存在axis参数，不能使用负数。

“.om”模型支持的Caffe算子边界如[表1](#table153119587174)所示。

**表 1**  Caffe算子边界

<a name="table153119587174"></a>
<table><thead align="left"><tr id="row124520151817"><th class="cellrowborder" valign="top" width="10%" id="mcps1.2.5.1.1"><p id="p11245180181818"><a name="p11245180181818"></a><a name="p11245180181818"></a><strong id="b1624580101815"><a name="b1624580101815"></a><a name="b1624580101815"></a>序号</strong></p>
</th>
<th class="cellrowborder" valign="top" width="14.499999999999998%" id="mcps1.2.5.1.2"><p id="p192451406189"><a name="p192451406189"></a><a name="p192451406189"></a><strong id="b524580141818"><a name="b524580141818"></a><a name="b524580141818"></a>算子</strong></p>
</th>
<th class="cellrowborder" valign="top" width="27.16%" id="mcps1.2.5.1.3"><p id="p824518017189"><a name="p824518017189"></a><a name="p824518017189"></a><strong id="b624514011184"><a name="b624514011184"></a><a name="b624514011184"></a>含义</strong></p>
</th>
<th class="cellrowborder" valign="top" width="48.339999999999996%" id="mcps1.2.5.1.4"><p id="p1924520071818"><a name="p1924520071818"></a><a name="p1924520071818"></a><strong id="b324515011811"><a name="b324515011811"></a><a name="b324515011811"></a>边界</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="row102457010189"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p1124560131817"><a name="p1124560131817"></a><a name="p1124560131817"></a>1</p>
</td>
<td class="cellrowborder" valign="top" width="14.499999999999998%" headers="mcps1.2.5.1.2 "><p id="p9245809184"><a name="p9245809184"></a><a name="p9245809184"></a>Absval</p>
</td>
<td class="cellrowborder" valign="top" width="27.16%" headers="mcps1.2.5.1.3 "><p id="p924618011813"><a name="p924618011813"></a><a name="p924618011813"></a>对输入求绝对值</p>
</td>
<td class="cellrowborder" valign="top" width="48.339999999999996%" headers="mcps1.2.5.1.4 "><p id="p1324618041815"><a name="p1324618041815"></a><a name="p1324618041815"></a>【输入】</p>
<p id="p1324670181812"><a name="p1324670181812"></a><a name="p1324670181812"></a>1个输入</p>
<p id="p1324618091818"><a name="p1324618091818"></a><a name="p1324618091818"></a>【参数】</p>
<p id="p1937113413205"><a name="p1937113413205"></a><a name="p1937113413205"></a>engine：枚举型，默认为0（DEFAULT=0，CAFFE=1，CUDNN=2），可选</p>
<p id="p92466081817"><a name="p92466081817"></a><a name="p92466081817"></a>【约束】</p>
<p id="p172467021810"><a name="p172467021810"></a><a name="p172467021810"></a>无限制</p>
<p id="p112468014185"><a name="p112468014185"></a><a name="p112468014185"></a>【量化工具支持】</p>
<p id="p6246109180"><a name="p6246109180"></a><a name="p6246109180"></a>是</p>
</td>
</tr>
<tr id="row182464041820"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p724615015187"><a name="p724615015187"></a><a name="p724615015187"></a>2</p>
</td>
<td class="cellrowborder" valign="top" width="14.499999999999998%" headers="mcps1.2.5.1.2 "><p id="p52469051810"><a name="p52469051810"></a><a name="p52469051810"></a>Argmax</p>
</td>
<td class="cellrowborder" valign="top" width="27.16%" headers="mcps1.2.5.1.3 "><p id="p10246170111814"><a name="p10246170111814"></a><a name="p10246170111814"></a>返回输入的最大值对应的索引序号</p>
</td>
<td class="cellrowborder" valign="top" width="48.339999999999996%" headers="mcps1.2.5.1.4 "><p id="p52461003185"><a name="p52461003185"></a><a name="p52461003185"></a>【输入】</p>
<p id="p82461206184"><a name="p82461206184"></a><a name="p82461206184"></a>1个输入</p>
<p id="p1624618091816"><a name="p1624618091816"></a><a name="p1624618091816"></a>【参数】</p>
<a name="ul9629129256"></a><a name="ul9629129256"></a><ul id="ul9629129256"><li>out_max_val：布尔型，默认为false，可选</li><li>top_k：unit32，默认为1，可选</li><li>axis：int32，可选</li></ul>
<p id="p11302191711239"><a name="p11302191711239"></a><a name="p11302191711239"></a>【约束】</p>
<p id="p761216524227"><a name="p761216524227"></a><a name="p761216524227"></a>无限制</p>
<p id="p19612652112214"><a name="p19612652112214"></a><a name="p19612652112214"></a>【量化工具支持】</p>
<p id="p106131352102218"><a name="p106131352102218"></a><a name="p106131352102218"></a>否</p>
</td>
</tr>
<tr id="row7246205182"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p024611051815"><a name="p024611051815"></a><a name="p024611051815"></a>3</p>
</td>
<td class="cellrowborder" valign="top" width="14.499999999999998%" headers="mcps1.2.5.1.2 "><p id="p924610015186"><a name="p924610015186"></a><a name="p924610015186"></a>BatchNorm</p>
</td>
<td class="cellrowborder" valign="top" width="27.16%" headers="mcps1.2.5.1.3 "><p id="p17246204183"><a name="p17246204183"></a><a name="p17246204183"></a>对输入做标准化</p>
<p id="p1246110201819"><a name="p1246110201819"></a><a name="p1246110201819"></a>（x - avg（x））/x的标准差</p>
</td>
<td class="cellrowborder" valign="top" width="48.339999999999996%" headers="mcps1.2.5.1.4 "><p id="p1024618031816"><a name="p1024618031816"></a><a name="p1024618031816"></a>【输入】</p>
<p id="p024615020182"><a name="p024615020182"></a><a name="p024615020182"></a>1个输入</p>
<p id="p132468015180"><a name="p132468015180"></a><a name="p132468015180"></a>【参数】</p>
<a name="ul081055482513"></a><a name="ul081055482513"></a><ul id="ul081055482513"><li>use_global_stats：布尔型，必须为true</li><li>moving_average_fraction：float，默认为0.999，可选</li><li>eps：float，默认为1e-5，可选</li></ul>
<p id="p1247130111819"><a name="p1247130111819"></a><a name="p1247130111819"></a>【约束】</p>
<p id="p172479011819"><a name="p172479011819"></a><a name="p172479011819"></a>仅支持对C维度方向做归一化</p>
<p id="p15247701186"><a name="p15247701186"></a><a name="p15247701186"></a>【量化工具支持】</p>
<p id="p224718011185"><a name="p224718011185"></a><a name="p224718011185"></a>是</p>
</td>
</tr>
<tr id="row132474031810"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p1024770171817"><a name="p1024770171817"></a><a name="p1024770171817"></a>4</p>
</td>
<td class="cellrowborder" valign="top" width="14.499999999999998%" headers="mcps1.2.5.1.2 "><p id="p1724712041814"><a name="p1724712041814"></a><a name="p1724712041814"></a>Concat</p>
</td>
<td class="cellrowborder" valign="top" width="27.16%" headers="mcps1.2.5.1.3 "><p id="p52471207181"><a name="p52471207181"></a><a name="p52471207181"></a>输入数据按维度拼接</p>
</td>
<td class="cellrowborder" valign="top" width="48.339999999999996%" headers="mcps1.2.5.1.4 "><p id="p224717011188"><a name="p224717011188"></a><a name="p224717011188"></a>【输入】</p>
<p id="p1824750101820"><a name="p1824750101820"></a><a name="p1824750101820"></a>多个输入</p>
<p id="p12471203189"><a name="p12471203189"></a><a name="p12471203189"></a>【参数】</p>
<a name="ul52419517262"></a><a name="ul52419517262"></a><ul id="ul52419517262"><li>concat_dim：uint32，默认为1，取值：大于0，可选</li><li>axis：int32，默认1，可选；与concat_dim功能相同，二者择其一；axis==-1时，输入维度必须等于4，否则结果可能错误</li></ul>
<p id="p8247307180"><a name="p8247307180"></a><a name="p8247307180"></a>【约束】</p>
<a name="ul471751662610"></a><a name="ul471751662610"></a><ul id="ul471751662610"><li>输入的tensor，除了进行concat的维度外，其他维度的size必须相等</li><li>输入tensor的个数范围不超过[1，1000]</li></ul>
<p id="p142479019184"><a name="p142479019184"></a><a name="p142479019184"></a>【量化工具支持】</p>
<p id="p52471700180"><a name="p52471700180"></a><a name="p52471700180"></a>是</p>
</td>
</tr>
<tr id="row224710012187"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p3247180111817"><a name="p3247180111817"></a><a name="p3247180111817"></a>5</p>
</td>
<td class="cellrowborder" valign="top" width="14.499999999999998%" headers="mcps1.2.5.1.2 "><p id="p16247200181812"><a name="p16247200181812"></a><a name="p16247200181812"></a>DepthwiseConvolution</p>
</td>
<td class="cellrowborder" valign="top" width="27.16%" headers="mcps1.2.5.1.3 "><p id="p2024713012180"><a name="p2024713012180"></a><a name="p2024713012180"></a>深度卷积</p>
</td>
<td class="cellrowborder" valign="top" width="48.339999999999996%" headers="mcps1.2.5.1.4 "><p id="p024710111811"><a name="p024710111811"></a><a name="p024710111811"></a>【输入】</p>
<p id="p224717011816"><a name="p224717011816"></a><a name="p224717011816"></a>1个输入，且filter为常量，维度为4</p>
<p id="p224711016188"><a name="p224711016188"></a><a name="p224711016188"></a>【参数】</p>
<a name="ul10580193232620"></a><a name="ul10580193232620"></a><ul id="ul10580193232620"><li>num_output：uint32，可选</li><li>bias_term：布尔型，默认为true，可选</li><li>pad：uint32，默认为0；数组</li><li>kernel_size：uint32；数组</li><li>stride：uint32，默认为1；数组</li><li>dilation：uint32，默认为1；数组</li><li>pad_h：uint32，默认为0，可选（仅2D）</li><li>pad_w：uint32，默认为0，可选（仅2D）</li><li>kernel_h：uint32，可选（仅2D）</li><li>kernel_w：uint32，可选（仅2D）</li><li>stride_h：uint32，可选（仅2D）</li><li>stride_w：uint32，可选（仅2D）</li><li>group：uint32，默认为1，可选</li><li>weight_filler：类型为FillerParameter，可选</li><li>bias_filler：类型为FillerParameter，可选</li><li>engine：枚举型，默认为0（DEFAULT=0，CAFFE=1，CUDNN=2），可选</li><li>force_nd_im2col：布尔型，默认为false，可选</li><li>axis：int32，默认为1，可选</li></ul>
<p id="p182481205186"><a name="p182481205186"></a><a name="p182481205186"></a>【约束】</p>
<p id="p22480061813"><a name="p22480061813"></a><a name="p22480061813"></a>filterN=inputC=group</p>
<p id="p924820011183"><a name="p924820011183"></a><a name="p924820011183"></a>【量化工具支持】</p>
<p id="p202482019186"><a name="p202482019186"></a><a name="p202482019186"></a>是</p>
</td>
</tr>
<tr id="row172481601180"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p6248100171811"><a name="p6248100171811"></a><a name="p6248100171811"></a>6</p>
</td>
<td class="cellrowborder" valign="top" width="14.499999999999998%" headers="mcps1.2.5.1.2 "><p id="p22487013185"><a name="p22487013185"></a><a name="p22487013185"></a>Convolution</p>
</td>
<td class="cellrowborder" valign="top" width="27.16%" headers="mcps1.2.5.1.3 "><p id="p82483015185"><a name="p82483015185"></a><a name="p82483015185"></a>卷积</p>
</td>
<td class="cellrowborder" valign="top" width="48.339999999999996%" headers="mcps1.2.5.1.4 "><p id="p172489041815"><a name="p172489041815"></a><a name="p172489041815"></a>【输入】</p>
<p id="p102482016187"><a name="p102482016187"></a><a name="p102482016187"></a>1个输入，且filter为常量，维度为4</p>
<p id="p52488019187"><a name="p52488019187"></a><a name="p52488019187"></a>【参数】</p>
<a name="ul413453422712"></a><a name="ul413453422712"></a><ul id="ul413453422712"><li>num_output：uint32，可选</li><li>bias_term：布尔型，默认为true，可选</li><li>pad：uint32，默认为0；数组</li><li>kernel_size：uint32；数组</li><li>stride：uint32，默认为1；数组</li><li>dilation：uint32，默认为1；数组</li><li>pad_h：uint32，默认为0，可选（仅2D）</li><li>pad_w：uint32，默认为0，可选（仅2D）</li><li>kernel_h：uint32，可选（仅2D）</li><li>kernel_w：uint32，可选（仅2D）</li><li>stride_h：uint32，可选（仅2D）</li><li>stride_w：uint32，可选（仅2D）</li><li>group：uint32，默认为1，可选</li><li>weight_filler：类型为FillerParameter，可选</li><li>bias_filler：类型为FillerParameter，可选</li><li>engine：枚举型，默认为0（DEFAULT=0，CAFFE=1，CUDNN=2），可选</li><li>force_nd_im2col：布尔型，默认为false，可选</li><li>axis：int32，默认为1，可选</li></ul>
<p id="p49189227275"><a name="p49189227275"></a><a name="p49189227275"></a>【约束】</p>
<a name="ul8670171615273"></a><a name="ul8670171615273"></a><ul id="ul8670171615273"><li>（inputW + padWHead + padWTail） &gt;= （（（FilterW- 1） * dilationW） + 1）</li><li>（inputW + padWHead + padWTail） /StrideW + 1 &lt;= 2147483647</li><li>（inputH + padHHead + padHTail） &gt;= （（（FilterH- 1） * dilationH） + 1）</li><li>（inputH + padHHead + padHTail） /StrideH + 1 &lt;= 2147483647</li><li>0 &lt;= Pad &lt; 256， 0 &lt; FilterSize &lt; 256， 0 &lt; Stride &lt; 64， 1 &lt;= dilationsize &lt; 256</li></ul>
<p id="p92498051816"><a name="p92498051816"></a><a name="p92498051816"></a>【量化工具支持】</p>
<p id="p202493021818"><a name="p202493021818"></a><a name="p202493021818"></a>是</p>
</td>
</tr>
<tr id="row112491507180"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p172491703183"><a name="p172491703183"></a><a name="p172491703183"></a>7</p>
</td>
<td class="cellrowborder" valign="top" width="14.499999999999998%" headers="mcps1.2.5.1.2 "><p id="p1524920191817"><a name="p1524920191817"></a><a name="p1524920191817"></a>Crop</p>
</td>
<td class="cellrowborder" valign="top" width="27.16%" headers="mcps1.2.5.1.3 "><p id="p1724910018188"><a name="p1724910018188"></a><a name="p1724910018188"></a>截取</p>
</td>
<td class="cellrowborder" valign="top" width="48.339999999999996%" headers="mcps1.2.5.1.4 "><p id="p824990191811"><a name="p824990191811"></a><a name="p824990191811"></a>【输入】</p>
<p id="p024920191820"><a name="p024920191820"></a><a name="p024920191820"></a>2个输入</p>
<p id="p8249409182"><a name="p8249409182"></a><a name="p8249409182"></a>【参数】</p>
<a name="ul1147916527274"></a><a name="ul1147916527274"></a><ul id="ul1147916527274"><li>axis：int32，默认为2，axis=-1，input dim必须等于4，可选</li><li>offset：uint32，数组</li></ul>
<p id="p725000111813"><a name="p725000111813"></a><a name="p725000111813"></a>【约束】</p>
<p id="p325016011184"><a name="p325016011184"></a><a name="p325016011184"></a>无限制</p>
<p id="p4250170141816"><a name="p4250170141816"></a><a name="p4250170141816"></a>【量化工具支持】</p>
<p id="p19250180171817"><a name="p19250180171817"></a><a name="p19250180171817"></a>否</p>
</td>
</tr>
<tr id="row1225018013184"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p162503061818"><a name="p162503061818"></a><a name="p162503061818"></a>8</p>
</td>
<td class="cellrowborder" valign="top" width="14.499999999999998%" headers="mcps1.2.5.1.2 "><p id="p1025070141810"><a name="p1025070141810"></a><a name="p1025070141810"></a>Deconvolution</p>
</td>
<td class="cellrowborder" valign="top" width="27.16%" headers="mcps1.2.5.1.3 "><p id="p625012018183"><a name="p625012018183"></a><a name="p625012018183"></a>反卷积</p>
</td>
<td class="cellrowborder" valign="top" width="48.339999999999996%" headers="mcps1.2.5.1.4 "><p id="p1625030141815"><a name="p1625030141815"></a><a name="p1625030141815"></a>【输入】</p>
<p id="p2025016011181"><a name="p2025016011181"></a><a name="p2025016011181"></a>1个输入，且filter为常量，维度为4</p>
<p id="p1325012051818"><a name="p1325012051818"></a><a name="p1325012051818"></a>【参数】</p>
<a name="ul1973203102813"></a><a name="ul1973203102813"></a><ul id="ul1973203102813"><li>num_output：uint32，可选</li><li>bias_term：布尔型，默认为true，可选</li><li>pad：uint32，默认为0；数组</li><li>kernel_size：uint32；数组</li><li>stride：uint32，默认为1；数组</li><li>dilation：uint32，默认为1；数组</li><li>pad_h：uint32，默认为0，可选（仅2D）</li><li>pad_w：uint32，默认为0，可选（仅2D）</li><li>kernel_h：uint32，可选（仅2D）</li><li>kernel_w：uint32，可选（仅2D）</li><li>stride_h：uint32，可选（仅2D）</li><li>stride_w：uint32，可选（仅2D）</li><li>group：uint32，默认为1，可选</li><li>weight_filler：类型为FillerParameter，可选</li><li>bias_filler：类型为FillerParameter，可选</li><li>engine：枚举型，默认为0（DEFAULT=0，CAFFE=1，CUDNN=2），可选</li><li>force_nd_im2col：布尔型，默认为false，可选</li><li>axis：int32，默认为1，可选</li></ul>
<p id="p1525100181816"><a name="p1525100181816"></a><a name="p1525100181816"></a>【约束】</p>
<a name="ul3110121212818"></a><a name="ul3110121212818"></a><ul id="ul3110121212818"><li>group = 1</li><li>dilation = 1</li><li>filterH - padHHead - 1 &gt;= 0</li><li>filterW - padWHead - 1 &gt;= 0</li></ul>
<p id="p1225140121820"><a name="p1225140121820"></a><a name="p1225140121820"></a>还有一条约束涉及中间变量，公式如下：</p>
<a name="ol18286152552817"></a><a name="ol18286152552817"></a><ol id="ol18286152552817"><li>a = ALIGN（filter_num，16） * ALIGN（filter_c，16） * filter_h * filter_w * 2</li><li>如果ALIGN（filter_c，16）%32 = 0，a = a/2</li><li>conv_input_width=（反卷积输入w - 1） * strideW + 1</li><li>b = （conv_input_width） * filter_h * ALIGN（filter_num，16） * 2 * 2</li><li>a + b &lt;= 1024*1024</li></ol>
<p id="p1525213081813"><a name="p1525213081813"></a><a name="p1525213081813"></a>【量化工具支持】</p>
<p id="p15252150161811"><a name="p15252150161811"></a><a name="p15252150161811"></a>是</p>
</td>
</tr>
<tr id="row425210011180"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p425214041813"><a name="p425214041813"></a><a name="p425214041813"></a>9</p>
</td>
<td class="cellrowborder" valign="top" width="14.499999999999998%" headers="mcps1.2.5.1.2 "><p id="p32526081817"><a name="p32526081817"></a><a name="p32526081817"></a>DetectionOutput</p>
</td>
<td class="cellrowborder" valign="top" width="27.16%" headers="mcps1.2.5.1.3 "><p id="p125215016189"><a name="p125215016189"></a><a name="p125215016189"></a>检测结果输出FSR</p>
</td>
<td class="cellrowborder" valign="top" width="48.339999999999996%" headers="mcps1.2.5.1.4 "><p id="p1225280131815"><a name="p1225280131815"></a><a name="p1225280131815"></a>【输入】</p>
<p id="p125215071819"><a name="p125215071819"></a><a name="p125215071819"></a>3个输入</p>
<p id="p102526013187"><a name="p102526013187"></a><a name="p102526013187"></a>【参数】</p>
<a name="ul621184418282"></a><a name="ul621184418282"></a><ul id="ul621184418282"><li>num_classes：必选，类型：int32，要预测的类数</li><li>share_location：可选，类型：bool，默认为true（表示不同类间共享bounding box）</li><li>background_label_id：可选，类型：int32，默认为0</li><li>nms_param：可选，非最大抑制</li><li>save_output_param：可选，用于保存检测结果</li><li>code_type：可选，默认为CENTER_SIZE</li><li>variance_encoded_in_target：可选，类型：bool，默认为true；如果为true，方差编码在目标中，否则需要相应地调整预测偏移量</li><li>keep_top_k：可选，类型：int32，在nms步骤后每个图像要保留的总bbox数</li><li>confidence_threshold：可选，类型：float，仅考虑置信度大于阈值的检测；如果没有设置，考虑所有的box</li><li>nms_threshold：可选，类型：float</li><li>top_k：可选，类型：int32</li><li>boxes：可选，类型：int32，默认为1</li><li>relative：可选，类型：bool，默认为true</li><li>objectness_threshold，可选，类型：float，默认为0.5</li><li>class_threshold：可选，类型：float，默认为0.5</li><li>biases：数组</li><li>general_nms_param：可选</li></ul>
<p id="p112541906183"><a name="p112541906183"></a><a name="p112541906183"></a>【约束】</p>
<a name="ul6411152122814"></a><a name="ul6411152122814"></a><ul id="ul6411152122814"><li>支持fasterrcnn网络</li><li>非极大值抑制比nmsThreshold∈（0，1）</li><li>概率阈值postConfThreshold∈（0，1）</li><li>类别&gt;=2</li><li>最大支持1024个框输入</li><li>输出的w维度是16</li></ul>
<p id="p172564081817"><a name="p172564081817"></a><a name="p172564081817"></a>【量化工具支持】</p>
<p id="p12256703182"><a name="p12256703182"></a><a name="p12256703182"></a>是</p>
</td>
</tr>
<tr id="row22564011181"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p6256906183"><a name="p6256906183"></a><a name="p6256906183"></a>10</p>
</td>
<td class="cellrowborder" valign="top" width="14.499999999999998%" headers="mcps1.2.5.1.2 "><p id="p92562000185"><a name="p92562000185"></a><a name="p92562000185"></a>Eltwise</p>
</td>
<td class="cellrowborder" valign="top" width="27.16%" headers="mcps1.2.5.1.3 "><p id="p125610020187"><a name="p125610020187"></a><a name="p125610020187"></a>按元素操作层（求和、乘积、最大值）</p>
</td>
<td class="cellrowborder" valign="top" width="48.339999999999996%" headers="mcps1.2.5.1.4 "><p id="p425715051816"><a name="p425715051816"></a><a name="p425715051816"></a>【输入】</p>
<p id="p102577001819"><a name="p102577001819"></a><a name="p102577001819"></a>至少2个输入</p>
<p id="p9257190191810"><a name="p9257190191810"></a><a name="p9257190191810"></a>【参数】</p>
<a name="ul41351013298"></a><a name="ul41351013298"></a><ul id="ul41351013298"><li>operation：可选，类型：枚举型（PROD = 0； SUM = 1； MAX = 2），默认为SUM</li><li>coeff：数组；类型：float</li><li>stable_prod_grad：可选，类型：bool，默认为true</li></ul>
<p id="p1325715081819"><a name="p1325715081819"></a><a name="p1325715081819"></a>【约束】</p>
<a name="ul552035142918"></a><a name="ul552035142918"></a><ul id="ul552035142918"><li>最大支持4个输入</li><li>与原生算子相比，不支持stable_prod_grad参数</li><li>支持prod、sum、max三种模式</li></ul>
<p id="p2257170121812"><a name="p2257170121812"></a><a name="p2257170121812"></a>【量化工具支持】</p>
<p id="p162579021816"><a name="p162579021816"></a><a name="p162579021816"></a>是</p>
</td>
</tr>
<tr id="row42577021815"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p82571015185"><a name="p82571015185"></a><a name="p82571015185"></a>11</p>
</td>
<td class="cellrowborder" valign="top" width="14.499999999999998%" headers="mcps1.2.5.1.2 "><p id="p1425750151818"><a name="p1425750151818"></a><a name="p1425750151818"></a>Elu</p>
</td>
<td class="cellrowborder" valign="top" width="27.16%" headers="mcps1.2.5.1.3 "><p id="p425780101814"><a name="p425780101814"></a><a name="p425780101814"></a>激活函数</p>
</td>
<td class="cellrowborder" valign="top" width="48.339999999999996%" headers="mcps1.2.5.1.4 "><p id="p525715011811"><a name="p525715011811"></a><a name="p525715011811"></a>【输入】</p>
<p id="p1425711091811"><a name="p1425711091811"></a><a name="p1425711091811"></a>1个输入</p>
<p id="p1425711071817"><a name="p1425711071817"></a><a name="p1425711071817"></a>【参数】</p>
<p id="p025717017181"><a name="p025717017181"></a><a name="p025717017181"></a>alpha （optional）：类型：float，默认为1</p>
<p id="p1025780131815"><a name="p1025780131815"></a><a name="p1025780131815"></a>【约束】</p>
<p id="p825714017184"><a name="p825714017184"></a><a name="p825714017184"></a>无限制</p>
<p id="p162573061812"><a name="p162573061812"></a><a name="p162573061812"></a>【量化工具支持】</p>
<p id="p19257705185"><a name="p19257705185"></a><a name="p19257705185"></a>否</p>
</td>
</tr>
<tr id="row19257601185"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p112579014183"><a name="p112579014183"></a><a name="p112579014183"></a>12</p>
</td>
<td class="cellrowborder" valign="top" width="14.499999999999998%" headers="mcps1.2.5.1.2 "><p id="p1025720031813"><a name="p1025720031813"></a><a name="p1025720031813"></a>Exp</p>
</td>
<td class="cellrowborder" valign="top" width="27.16%" headers="mcps1.2.5.1.3 "><p id="p025715014180"><a name="p025715014180"></a><a name="p025715014180"></a>对输入求以e为底的x次方值</p>
</td>
<td class="cellrowborder" valign="top" width="48.339999999999996%" headers="mcps1.2.5.1.4 "><p id="p1325780161811"><a name="p1325780161811"></a><a name="p1325780161811"></a>【输入】</p>
<p id="p72577012187"><a name="p72577012187"></a><a name="p72577012187"></a>1个输入</p>
<p id="p1325740171813"><a name="p1325740171813"></a><a name="p1325740171813"></a>【参数】</p>
<a name="ul18971213152919"></a><a name="ul18971213152919"></a><ul id="ul18971213152919"><li>base：可选，类型：float，默认为-1.0</li><li>scale：可选，类型：float，默认为1.0</li><li>shift：可选，类型：float，默认为0.0</li></ul>
<p id="p72571201189"><a name="p72571201189"></a><a name="p72571201189"></a>【约束】</p>
<p id="p725711014189"><a name="p725711014189"></a><a name="p725711014189"></a>无限制</p>
<p id="p13257100141811"><a name="p13257100141811"></a><a name="p13257100141811"></a>【量化工具支持】</p>
<p id="p112571505180"><a name="p112571505180"></a><a name="p112571505180"></a>否</p>
</td>
</tr>
<tr id="row1625720012189"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p11258405181"><a name="p11258405181"></a><a name="p11258405181"></a>13</p>
</td>
<td class="cellrowborder" valign="top" width="14.499999999999998%" headers="mcps1.2.5.1.2 "><p id="p10258140121812"><a name="p10258140121812"></a><a name="p10258140121812"></a>Flatten</p>
</td>
<td class="cellrowborder" valign="top" width="27.16%" headers="mcps1.2.5.1.3 "><p id="p02581302184"><a name="p02581302184"></a><a name="p02581302184"></a>输入n*c*h*w 变为向量 n* （c*h*w）</p>
</td>
<td class="cellrowborder" valign="top" width="48.339999999999996%" headers="mcps1.2.5.1.4 "><p id="p9258110191816"><a name="p9258110191816"></a><a name="p9258110191816"></a>【输入】</p>
<p id="p182582013181"><a name="p182582013181"></a><a name="p182582013181"></a>1个输入</p>
<p id="p18258706187"><a name="p18258706187"></a><a name="p18258706187"></a>（top_size与bottom_size必须不一致，且不为1；当axis=-1时，输入的dim必须等于4）</p>
<p id="p19258101186"><a name="p19258101186"></a><a name="p19258101186"></a>【参数】</p>
<a name="ul105341620102918"></a><a name="ul105341620102918"></a><ul id="ul105341620102918"><li>axis：可选，类型：int32，默认为1</li><li>end_axis：可选，类型：int32，默认为-1</li></ul>
<p id="p925814051813"><a name="p925814051813"></a><a name="p925814051813"></a>【约束】</p>
<p id="p225820121819"><a name="p225820121819"></a><a name="p225820121819"></a>axis必须小于end axis</p>
<p id="p5258306185"><a name="p5258306185"></a><a name="p5258306185"></a>【量化工具支持】</p>
<p id="p4258300188"><a name="p4258300188"></a><a name="p4258300188"></a>是</p>
</td>
</tr>
<tr id="row142581802183"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p62581902183"><a name="p62581902183"></a><a name="p62581902183"></a>14</p>
</td>
<td class="cellrowborder" valign="top" width="14.499999999999998%" headers="mcps1.2.5.1.2 "><p id="p162581206183"><a name="p162581206183"></a><a name="p162581206183"></a>FullConnection</p>
</td>
<td class="cellrowborder" valign="top" width="27.16%" headers="mcps1.2.5.1.3 "><p id="p20258150121813"><a name="p20258150121813"></a><a name="p20258150121813"></a>全连接</p>
</td>
<td class="cellrowborder" valign="top" width="48.339999999999996%" headers="mcps1.2.5.1.4 "><p id="p425818018185"><a name="p425818018185"></a><a name="p425818018185"></a>【输入】</p>
<p id="p132584018184"><a name="p132584018184"></a><a name="p132584018184"></a>1个输入</p>
<p id="p525817081813"><a name="p525817081813"></a><a name="p525817081813"></a>【参数】</p>
<a name="ul1670433032920"></a><a name="ul1670433032920"></a><ul id="ul1670433032920"><li>num_output：可选，类型：uint32</li><li>bias_term：可选，类型：bool，默认为true</li><li>weight_filler：可选，类型：FillerParameter，维度为2</li><li>bias_filler：可选，类型：FillerParameter，维度为1</li><li>axis：可选，类型：int32，默认为1</li><li>transpose：可选，类型：bool，默认为false</li></ul>
<p id="p625810131810"><a name="p625810131810"></a><a name="p625810131810"></a>【约束】</p>
<a name="ul1950934012296"></a><a name="ul1950934012296"></a><ul id="ul1950934012296"><li>仅支持transpose=false，axis=1</li><li>Bais_C &lt;= 56832</li><li>如果客户要量化模型时，需要满足下列维度：</li><li>−       当N = 1，2 * CEIL（C，16） * 16 * xH * xW&lt;= 1024 * 1024</li><li>−       当N&gt;1，2 * 16 * CEIL（C，16） * 16 * xH * xW &lt;= 1024 * 1024</li></ul>
<p id="p625890171813"><a name="p625890171813"></a><a name="p625890171813"></a>【量化工具支持】</p>
<p id="p125860111814"><a name="p125860111814"></a><a name="p125860111814"></a>是</p>
</td>
</tr>
<tr id="row19258110121819"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p525912012186"><a name="p525912012186"></a><a name="p525912012186"></a>15</p>
</td>
<td class="cellrowborder" valign="top" width="14.499999999999998%" headers="mcps1.2.5.1.2 "><p id="p1125912015187"><a name="p1125912015187"></a><a name="p1125912015187"></a>Interp</p>
</td>
<td class="cellrowborder" valign="top" width="27.16%" headers="mcps1.2.5.1.3 "><p id="p13259100141817"><a name="p13259100141817"></a><a name="p13259100141817"></a>插值层</p>
</td>
<td class="cellrowborder" valign="top" width="48.339999999999996%" headers="mcps1.2.5.1.4 "><p id="p52598011818"><a name="p52598011818"></a><a name="p52598011818"></a>【输入】</p>
<p id="p10260130201810"><a name="p10260130201810"></a><a name="p10260130201810"></a>1个输入</p>
<p id="p1226020191810"><a name="p1226020191810"></a><a name="p1226020191810"></a>【参数】</p>
<a name="ul17260100101819"></a><a name="ul17260100101819"></a><ul id="ul17260100101819"><li>height：可选，类型：int32，默认为0</li><li>width：可选，类型：int32，默认为0</li><li>zoom_factor：可选，类型：int32，默认为1</li><li>shrink_factor：可选，类型：int32，默认为1</li><li>pad_beg：可选，类型：int32，默认为0</li><li>pad_end：可选，类型：int32， 默认为0</li></ul>
<div class="note" id="note98588586178"><a name="note98588586178"></a><a name="note98588586178"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p2261102182"><a name="p2261102182"></a><a name="p2261102182"></a>l    zoom_factor与shrink_factor不能同时存在</p>
<p id="p426113015189"><a name="p426113015189"></a><a name="p426113015189"></a>l    height与zoom_factor不能同时存在</p>
<p id="p5261110141816"><a name="p5261110141816"></a><a name="p5261110141816"></a>l    height与shrink_factor不能同时存在</p>
</div></div>
<p id="p15261180131810"><a name="p15261180131810"></a><a name="p15261180131810"></a>【约束】</p>
<p id="p102618091818"><a name="p102618091818"></a><a name="p102618091818"></a>（outputH*outputW）/（inputH*inputW） &gt; 1/30</p>
<p id="p1426116011816"><a name="p1426116011816"></a><a name="p1426116011816"></a>【量化工具支持】</p>
<p id="p926117041820"><a name="p926117041820"></a><a name="p926117041820"></a>否</p>
</td>
</tr>
<tr id="row826110016185"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p1626150181815"><a name="p1626150181815"></a><a name="p1626150181815"></a>16</p>
</td>
<td class="cellrowborder" valign="top" width="14.499999999999998%" headers="mcps1.2.5.1.2 "><p id="p102611803185"><a name="p102611803185"></a><a name="p102611803185"></a>Log</p>
</td>
<td class="cellrowborder" valign="top" width="27.16%" headers="mcps1.2.5.1.3 "><p id="p6261180121819"><a name="p6261180121819"></a><a name="p6261180121819"></a>对输入进行log计算</p>
</td>
<td class="cellrowborder" valign="top" width="48.339999999999996%" headers="mcps1.2.5.1.4 "><p id="p102612081817"><a name="p102612081817"></a><a name="p102612081817"></a>【输入】</p>
<p id="p182614014185"><a name="p182614014185"></a><a name="p182614014185"></a>1个输入</p>
<p id="p132611021814"><a name="p132611021814"></a><a name="p132611021814"></a>【参数】</p>
<a name="ul964153172915"></a><a name="ul964153172915"></a><ul id="ul964153172915"><li>base：可选，类型：float，默认为-1.0</li><li>scale：可选，类型：float，默认为1.0</li><li>shift：可选，类型：float，默认为0.0</li></ul>
<p id="p426119051817"><a name="p426119051817"></a><a name="p426119051817"></a>【约束】</p>
<p id="p52613011813"><a name="p52613011813"></a><a name="p52613011813"></a>无限制</p>
<p id="p72622001818"><a name="p72622001818"></a><a name="p72622001818"></a>【量化工具支持】</p>
<p id="p126220131818"><a name="p126220131818"></a><a name="p126220131818"></a>否</p>
</td>
</tr>
<tr id="row1026270201813"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p172623091818"><a name="p172623091818"></a><a name="p172623091818"></a>17</p>
</td>
<td class="cellrowborder" valign="top" width="14.499999999999998%" headers="mcps1.2.5.1.2 "><p id="p62624031817"><a name="p62624031817"></a><a name="p62624031817"></a>LRN</p>
</td>
<td class="cellrowborder" valign="top" width="27.16%" headers="mcps1.2.5.1.3 "><p id="p182624061810"><a name="p182624061810"></a><a name="p182624061810"></a>局部响应归一化层</p>
</td>
<td class="cellrowborder" valign="top" width="48.339999999999996%" headers="mcps1.2.5.1.4 "><p id="p19262200121818"><a name="p19262200121818"></a><a name="p19262200121818"></a>【输入】</p>
<p id="p162629021818"><a name="p162629021818"></a><a name="p162629021818"></a>1个输入，不支持常量输入</p>
<p id="p52623061812"><a name="p52623061812"></a><a name="p52623061812"></a>【参数】</p>
<a name="ul1982119443012"></a><a name="ul1982119443012"></a><ul id="ul1982119443012"><li>local_size：可选，类型：uint32，默认为5</li><li>alpha：可选，类型：float，默认为1</li><li>beta：可选，类型：float，默认为0.75</li><li>norm_region：可选，类型：枚举型，默认为ACROSS_CHANNELS，（ACROSS_CHANNELS=0；WITHIN_CHANNEL = 1）</li><li>lrnk：可选，类型：float，默认为1</li><li>engine：可选，类型：枚举型（DEFAULT = 0；CAFFE = 1； CUDNN = 2）</li></ul>
<p id="p1826210020181"><a name="p1826210020181"></a><a name="p1826210020181"></a>【约束】</p>
<a name="ul55571233012"></a><a name="ul55571233012"></a><ul id="ul55571233012"><li>local_size &gt;0，且必须为奇数</li><li>通道间：当local_size∈[1，15]时，lrnK&gt;0.00001且beta&gt;0.01，否则lrnK和beta为任意值；LrnK和alpha不同时为0；当C维度大于1776时，local_size &lt;1728</li><li>通道内：LrnK=1，local_size∈[1，15]，beta&gt;0.01</li></ul>
<p id="p02621202188"><a name="p02621202188"></a><a name="p02621202188"></a>【量化工具支持】</p>
<p id="p15262308185"><a name="p15262308185"></a><a name="p15262308185"></a>是</p>
</td>
</tr>
<tr id="row32620012184"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p18262504185"><a name="p18262504185"></a><a name="p18262504185"></a>18</p>
</td>
<td class="cellrowborder" valign="top" width="14.499999999999998%" headers="mcps1.2.5.1.2 "><p id="p122620071819"><a name="p122620071819"></a><a name="p122620071819"></a>LSTM</p>
</td>
<td class="cellrowborder" valign="top" width="27.16%" headers="mcps1.2.5.1.3 "><p id="p20262908183"><a name="p20262908183"></a><a name="p20262908183"></a>长短期记忆网络</p>
</td>
<td class="cellrowborder" valign="top" width="48.339999999999996%" headers="mcps1.2.5.1.4 "><p id="p112621605182"><a name="p112621605182"></a><a name="p112621605182"></a>【输入】</p>
<p id="p526211001810"><a name="p526211001810"></a><a name="p526211001810"></a>2个或3个输入</p>
<a name="ul16302182373017"></a><a name="ul16302182373017"></a><ul id="ul16302182373017"><li>X：时间序列数据(T*B*Xt)，按4D的NCHW格式排布传入</li><li>需要保证：N对应时间序列长度T，C对应Batch数B，H对应t时刻的输入数据Xt，W取1</li><li>Cont：序列连续性标志（T*B）</li><li>Xs：静态数据（B*Xt），可选</li></ul>
<p id="p1526390131819"><a name="p1526390131819"></a><a name="p1526390131819"></a>【参数】</p>
<a name="ul13934192923011"></a><a name="ul13934192923011"></a><ul id="ul13934192923011"><li>num_output：可选，类型：uint32，默认为0</li><li>weight_filler：可选，类型：FillerParameter</li><li>bias_filler：可选，类型：FillerParameter</li><li>debug_info：可选，类型：bool，默认为false</li><li>expose_hidden：可选，类型：bool，默认为false</li></ul>
<p id="p12639051816"><a name="p12639051816"></a><a name="p12639051816"></a>【约束】</p>
<p id="p1926314051813"><a name="p1926314051813"></a><a name="p1926314051813"></a>此约束涉及中间变量计算，公式如列：</p>
<p id="p5263103185"><a name="p5263103185"></a><a name="p5263103185"></a>a = （ALIGN（xt，16） + ALIGN（output，16）） * 16 * 2 * 2</p>
<p id="p122633061811"><a name="p122633061811"></a><a name="p122633061811"></a>b = （ALIGN（xt，16） + ALIGN（output，16）） * 16 * 4 * 2 * 2</p>
<p id="p192639031814"><a name="p192639031814"></a><a name="p192639031814"></a>c = use_projection ? ALIGN（ht，16） * ALIGN（output，16） * 2）：0</p>
<p id="p32631602185"><a name="p32631602185"></a><a name="p32631602185"></a>d = 16 * ALIGN（ht，16） * 2</p>
<p id="p15263150191813"><a name="p15263150191813"></a><a name="p15263150191813"></a>e = batchNum* 4</p>
<p id="p192634014183"><a name="p192634014183"></a><a name="p192634014183"></a>则，约束为：</p>
<p id="p122631071818"><a name="p122631071818"></a><a name="p122631071818"></a>a + b + c &lt;= 1024 * 1024</p>
<p id="p42638081817"><a name="p42638081817"></a><a name="p42638081817"></a>d &lt;= 256*1024 / 8</p>
<p id="p1026310020180"><a name="p1026310020180"></a><a name="p1026310020180"></a>e &lt;= 256*1024 / 32</p>
<p id="p1926314015183"><a name="p1926314015183"></a><a name="p1926314015183"></a>【量化工具支持】</p>
<p id="p9263401183"><a name="p9263401183"></a><a name="p9263401183"></a>否</p>
</td>
</tr>
<tr id="row626380131818"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p182631709189"><a name="p182631709189"></a><a name="p182631709189"></a>19</p>
</td>
<td class="cellrowborder" valign="top" width="14.499999999999998%" headers="mcps1.2.5.1.2 "><p id="p15263809180"><a name="p15263809180"></a><a name="p15263809180"></a>Normalize</p>
</td>
<td class="cellrowborder" valign="top" width="27.16%" headers="mcps1.2.5.1.3 "><p id="p22630051816"><a name="p22630051816"></a><a name="p22630051816"></a>标准化层</p>
</td>
<td class="cellrowborder" valign="top" width="48.339999999999996%" headers="mcps1.2.5.1.4 "><p id="p182631701189"><a name="p182631701189"></a><a name="p182631701189"></a>【输入】</p>
<p id="p132630081815"><a name="p132630081815"></a><a name="p132630081815"></a>1个输入</p>
<p id="p102631000183"><a name="p102631000183"></a><a name="p102631000183"></a>【参数】</p>
<a name="ul1725911404302"></a><a name="ul1725911404302"></a><ul id="ul1725911404302"><li>across_spatial：可选，类型：bool，默认为true</li><li>scale_filler：可选，默认为1.0</li><li>channel_shared：可选，类型：bool，默认为true</li><li>eps：可选，类型：float，默认为1e-10</li></ul>
<p id="p13263160151813"><a name="p13263160151813"></a><a name="p13263160151813"></a>【约束】</p>
<a name="ul0491245143014"></a><a name="ul0491245143014"></a><ul id="ul0491245143014"><li>eps应大于1e-7，并且小于等于0.1+（1e-6）</li><li>Caffe框架中的参数across_spatial目前只支持true，按channel进行norm操作</li></ul>
<p id="p152641501185"><a name="p152641501185"></a><a name="p152641501185"></a>【量化工具支持】</p>
<p id="p112648051816"><a name="p112648051816"></a><a name="p112648051816"></a>是</p>
</td>
</tr>
<tr id="row142648012185"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p1426450171816"><a name="p1426450171816"></a><a name="p1426450171816"></a>20</p>
</td>
<td class="cellrowborder" valign="top" width="14.499999999999998%" headers="mcps1.2.5.1.2 "><p id="p1826410091812"><a name="p1826410091812"></a><a name="p1826410091812"></a>Permute</p>
</td>
<td class="cellrowborder" valign="top" width="27.16%" headers="mcps1.2.5.1.3 "><p id="p1626419019182"><a name="p1626419019182"></a><a name="p1626419019182"></a>将输入维度按照给定模式进行重排</p>
</td>
<td class="cellrowborder" valign="top" width="48.339999999999996%" headers="mcps1.2.5.1.4 "><p id="p126414013185"><a name="p126414013185"></a><a name="p126414013185"></a>【输入】</p>
<p id="p142641041817"><a name="p142641041817"></a><a name="p142641041817"></a>1个输入</p>
<p id="p1926417018189"><a name="p1926417018189"></a><a name="p1926417018189"></a>【参数】</p>
<p id="p82646019185"><a name="p82646019185"></a><a name="p82646019185"></a>order：uint32，数组</p>
<p id="p326410091816"><a name="p326410091816"></a><a name="p326410091816"></a>【约束】</p>
<p id="p1126417051810"><a name="p1126417051810"></a><a name="p1126417051810"></a>无约束</p>
<p id="p162648081819"><a name="p162648081819"></a><a name="p162648081819"></a>【量化工具支持】</p>
<p id="p18264200161819"><a name="p18264200161819"></a><a name="p18264200161819"></a>是</p>
</td>
</tr>
<tr id="row92646016189"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p1626416031819"><a name="p1626416031819"></a><a name="p1626416031819"></a>21</p>
</td>
<td class="cellrowborder" valign="top" width="14.499999999999998%" headers="mcps1.2.5.1.2 "><p id="p3264601187"><a name="p3264601187"></a><a name="p3264601187"></a>Pooling</p>
</td>
<td class="cellrowborder" valign="top" width="27.16%" headers="mcps1.2.5.1.3 "><p id="p1426413014181"><a name="p1426413014181"></a><a name="p1426413014181"></a>池化层</p>
</td>
<td class="cellrowborder" valign="top" width="48.339999999999996%" headers="mcps1.2.5.1.4 "><p id="p92645031813"><a name="p92645031813"></a><a name="p92645031813"></a>【输入】</p>
<p id="p626412031820"><a name="p626412031820"></a><a name="p626412031820"></a>1个输入</p>
<p id="p326419019183"><a name="p326419019183"></a><a name="p326419019183"></a>【参数】</p>
<a name="ul1710019073110"></a><a name="ul1710019073110"></a><ul id="ul1710019073110"><li>pool：池化方法，可选，类型：枚举，取值：MAX=0，AVE=1，STOCHASTIC = 2，默认为MAX</li><li>pad：可选，类型：uint32，默认为0</li><li>pad_h：可选，类型：uint32，默认为0</li><li>pad_w：可选，类型：uint32，默认为0</li><li>kernel_size：可选，类型：uint32，kernel_size和kernel_h/kernel_w不能同时出现</li><li>kernel_h：可选，类型：uint32</li><li>kernel_w：可选，类型：uint32，kernel_h/kernel_w必须同时存在</li><li>stride：可选，类型：uint32，默认为1</li><li>stride_h：可选，类型：uint32</li><li>stride_w：可选，类型：uint32</li><li>engine：可选，类型：枚举，取值：DEFAULT=0，CAFFE=1，CUDNN=2</li><li>global_pooling：可选，类型：bool，默认值为false</li><li>ceil_mode：可选，类型：bool，默认为true</li><li>round_mode：可选，类型：枚举，取值：CEIL=0，FLOOR=1；默认为CEIL</li></ul>
<p id="p2026516071818"><a name="p2026516071818"></a><a name="p2026516071818"></a>【约束】</p>
<a name="ul8815178133110"></a><a name="ul8815178133110"></a><ul id="ul8815178133110"><li>kernelH&lt;=inputH+padTop+padBottom</li><li>kernelW&lt;=inputW+padLeft+padRight</li><li>padTop&lt;windowH</li><li>padBottom&lt;windowH</li><li>padLeft&lt;windowW</li><li>padRight&lt;windowW</li></ul>
<p id="p15265206185"><a name="p15265206185"></a><a name="p15265206185"></a>除公共约束外，还需满足下列某一场景支持范围</p>
<p id="p82652081812"><a name="p82652081812"></a><a name="p82652081812"></a>global pool模式只支持以下范围：</p>
<a name="ol16493815183111"></a><a name="ol16493815183111"></a><ol id="ol16493815183111"><li>outputH==1 &amp;&amp; outputW==1 &amp;&amp; kernelH&gt;=inputH &amp;&amp; kernelW&gt;=inputW</li><li>inputH*inputW&lt;=10000</li></ol>
<p id="p3265180191818"><a name="p3265180191818"></a><a name="p3265180191818"></a>【量化工具支持】</p>
<p id="p5265409186"><a name="p5265409186"></a><a name="p5265409186"></a>是</p>
</td>
</tr>
<tr id="row122651403184"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p7265100131819"><a name="p7265100131819"></a><a name="p7265100131819"></a>22</p>
</td>
<td class="cellrowborder" valign="top" width="14.499999999999998%" headers="mcps1.2.5.1.2 "><p id="p20265706183"><a name="p20265706183"></a><a name="p20265706183"></a>Power</p>
</td>
<td class="cellrowborder" valign="top" width="27.16%" headers="mcps1.2.5.1.3 "><p id="p202655020185"><a name="p202655020185"></a><a name="p202655020185"></a>计算 y = （scale*x+shift）^ power</p>
</td>
<td class="cellrowborder" valign="top" width="48.339999999999996%" headers="mcps1.2.5.1.4 "><p id="p62653091810"><a name="p62653091810"></a><a name="p62653091810"></a>【输入】</p>
<p id="p132651002187"><a name="p132651002187"></a><a name="p132651002187"></a>1个输入</p>
<p id="p18265809186"><a name="p18265809186"></a><a name="p18265809186"></a>【参数】</p>
<a name="ul1333102153115"></a><a name="ul1333102153115"></a><ul id="ul1333102153115"><li>power：可选，类型：float，默认为1.0</li><li>scale：可选，类型：float，默认为1.0</li><li>shift：可选，类型：float，默认为0.0</li></ul>
<p id="p192656031812"><a name="p192656031812"></a><a name="p192656031812"></a>【约束】</p>
<a name="ul12970162583111"></a><a name="ul12970162583111"></a><ul id="ul12970162583111"><li>power!=1</li><li>scale*x+shift&gt;0</li></ul>
<p id="p152665001814"><a name="p152665001814"></a><a name="p152665001814"></a>【量化工具支持】</p>
<p id="p1326690161815"><a name="p1326690161815"></a><a name="p1326690161815"></a>是</p>
</td>
</tr>
<tr id="row17266190151817"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p22661071813"><a name="p22661071813"></a><a name="p22661071813"></a>23</p>
</td>
<td class="cellrowborder" valign="top" width="14.499999999999998%" headers="mcps1.2.5.1.2 "><p id="p326640131817"><a name="p326640131817"></a><a name="p326640131817"></a>Prelu</p>
</td>
<td class="cellrowborder" valign="top" width="27.16%" headers="mcps1.2.5.1.3 "><p id="p1626617016189"><a name="p1626617016189"></a><a name="p1626617016189"></a>激活函数</p>
</td>
<td class="cellrowborder" valign="top" width="48.339999999999996%" headers="mcps1.2.5.1.4 "><p id="p12266160131815"><a name="p12266160131815"></a><a name="p12266160131815"></a>【输入】</p>
<p id="p2026610191813"><a name="p2026610191813"></a><a name="p2026610191813"></a>1个输入</p>
<p id="p18266306180"><a name="p18266306180"></a><a name="p18266306180"></a>【参数】</p>
<a name="ul172901131173119"></a><a name="ul172901131173119"></a><ul id="ul172901131173119"><li>filler：可选</li><li>channel_shared：可选，类型：bool，默认为false，是否跨channel共享斜率参数</li></ul>
<p id="p0266505186"><a name="p0266505186"></a><a name="p0266505186"></a>【约束】</p>
<p id="p152666041811"><a name="p152666041811"></a><a name="p152666041811"></a>无限制</p>
<p id="p15266140181820"><a name="p15266140181820"></a><a name="p15266140181820"></a>【量化工具支持】</p>
<p id="p0266130171810"><a name="p0266130171810"></a><a name="p0266130171810"></a>是</p>
</td>
</tr>
<tr id="row1226618016181"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p226700101818"><a name="p226700101818"></a><a name="p226700101818"></a>24</p>
</td>
<td class="cellrowborder" valign="top" width="14.499999999999998%" headers="mcps1.2.5.1.2 "><p id="p5267200181813"><a name="p5267200181813"></a><a name="p5267200181813"></a>PriorBox</p>
</td>
<td class="cellrowborder" valign="top" width="27.16%" headers="mcps1.2.5.1.3 "><p id="p122671011184"><a name="p122671011184"></a><a name="p122671011184"></a>从目标预选框获取真实目标的位置</p>
</td>
<td class="cellrowborder" valign="top" width="48.339999999999996%" headers="mcps1.2.5.1.4 "><p id="p5267140101819"><a name="p5267140101819"></a><a name="p5267140101819"></a>【输入】</p>
<p id="p1826817071817"><a name="p1826817071817"></a><a name="p1826817071817"></a>1个输入</p>
<p id="p122692002181"><a name="p122692002181"></a><a name="p122692002181"></a>【参数】</p>
<a name="ul17346194318316"></a><a name="ul17346194318316"></a><ul id="ul17346194318316"><li>min_size：必须设置，最小框大小（以像素为单位）</li><li>max_size：必须设置，最大框大小（以像素为单位）</li><li>aspect_ratio：数组；类型：float；各种宽高比，重复的比率将被忽略，如果没有提供，使用默认比率1</li><li>flip：可选，类型：bool，默认为true；如果为true，将翻转每个宽高比，例如，如果有宽高比‘r’，也将生成宽高比‘1.0/r’</li><li>clip：可选，类型：bool，默认为false；如果为true，将剪切先前的值，使其在[0，1]范围内</li><li>variance：数组；调整先前bbox的方差</li><li>img_size：可选，类型：uint32，img_size与img_h/img_w不能同时存在</li><li>img_h：可选，类型：uint32</li><li>img_w：可选，类型：uint32</li><li>step：可选，类型：float，step与step_h/step_w不能同时存在</li><li>step_h：可选，类型：float</li><li>step_w：可选，类型：float</li><li>offset：类型：float，默认为0.5</li></ul>
<p id="p17272809186"><a name="p17272809186"></a><a name="p17272809186"></a>【约束】</p>
<p id="p112720013183"><a name="p112720013183"></a><a name="p112720013183"></a>只支持ssd网络</p>
<p id="p92726016184"><a name="p92726016184"></a><a name="p92726016184"></a>输出维度：[n，2，检测框*4，1]</p>
<p id="p1272905183"><a name="p1272905183"></a><a name="p1272905183"></a>【量化工具支持】</p>
<p id="p162721106185"><a name="p162721106185"></a><a name="p162721106185"></a>是</p>
</td>
</tr>
<tr id="row127210071812"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p162729017187"><a name="p162729017187"></a><a name="p162729017187"></a>25</p>
</td>
<td class="cellrowborder" valign="top" width="14.499999999999998%" headers="mcps1.2.5.1.2 "><p id="p132725013185"><a name="p132725013185"></a><a name="p132725013185"></a>Proposal</p>
</td>
<td class="cellrowborder" valign="top" width="27.16%" headers="mcps1.2.5.1.3 "><p id="p2272180171820"><a name="p2272180171820"></a><a name="p2272180171820"></a>将预选框通过（proposal， score）排序，通过nms获取topN proposal</p>
</td>
<td class="cellrowborder" valign="top" width="48.339999999999996%" headers="mcps1.2.5.1.4 "><p id="p1272307186"><a name="p1272307186"></a><a name="p1272307186"></a>【输入】</p>
<p id="p527216014187"><a name="p527216014187"></a><a name="p527216014187"></a>3个输入（scores，bbox_pred，im_info）</p>
<p id="p1027214081811"><a name="p1027214081811"></a><a name="p1027214081811"></a>【参数】</p>
<a name="ul076935213114"></a><a name="ul076935213114"></a><ul id="ul076935213114"><li>feat_stride：可选，类型：float</li><li>base_size：可选，类型：float</li><li>min_size：可选，类型：float</li><li>ratio：数组；类型：float</li><li>scale：数组；类型：float</li><li>pre_nms_topn：可选，类型：int32</li><li>post_nms_topn：可选，类型：int32</li><li>nms_thresh：可选，类型：float</li></ul>
<p id="p172724071815"><a name="p172724071815"></a><a name="p172724071815"></a>【约束】</p>
<a name="ul1397853323"></a><a name="ul1397853323"></a><ul id="ul1397853323"><li>只用于fastercnn</li><li>ProposalParameter、PythonParameter不能同时存在</li><li>preTopK范围为1~6144</li><li>postTopK范围为1~1024</li><li>scaleCnt*ratioCnt的最大值支持到64</li><li>nmsTresh：过滤框使用的阈值，0&lt;nmsTresh&lt;=1</li><li>minSize：框的边长的最小值，所有小于此最小值的框将会被过滤掉</li><li>featStride：在生成默认框时，指定两个相邻的框延H或W的步长</li><li>baseSize：用来生成默认框用到的参数，表示框的基本大小</li><li>ratio &amp; scale：生成默认框用到的参数</li><li>imgH&amp;imgW：输入到网络的图片高和宽，其值必须大于0</li><li>input维度约束：<p id="p1812214216320"><a name="p1812214216320"></a><a name="p1812214216320"></a>clsProb：C=2*scaleCnt*ratioCnt</p>
<p id="p012252119321"><a name="p012252119321"></a><a name="p012252119321"></a>bboxPred：C=4*scaleCnt*ratioCnt</p>
<p id="p1812272119326"><a name="p1812272119326"></a><a name="p1812272119326"></a>bboxPrior：N=clsProb.N，C=4*scaleCnt*ratioCnt</p>
<p id="p1812262112329"><a name="p1812262112329"></a><a name="p1812262112329"></a>imInfo：N=clsProb.N，C=3</p>
</li></ul>
<p id="p152733017184"><a name="p152733017184"></a><a name="p152733017184"></a>【量化工具支持】</p>
<p id="p82733051814"><a name="p82733051814"></a><a name="p82733051814"></a>是</p>
</td>
</tr>
<tr id="row5273110131812"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p142731904184"><a name="p142731904184"></a><a name="p142731904184"></a>26</p>
</td>
<td class="cellrowborder" valign="top" width="14.499999999999998%" headers="mcps1.2.5.1.2 "><p id="p22730013181"><a name="p22730013181"></a><a name="p22730013181"></a>PSROIPooling</p>
</td>
<td class="cellrowborder" valign="top" width="27.16%" headers="mcps1.2.5.1.3 "><p id="p627313001810"><a name="p627313001810"></a><a name="p627313001810"></a>位置敏感的区域池化</p>
</td>
<td class="cellrowborder" valign="top" width="48.339999999999996%" headers="mcps1.2.5.1.4 "><p id="p12732011181"><a name="p12732011181"></a><a name="p12732011181"></a>【输入】</p>
<p id="p172734016186"><a name="p172734016186"></a><a name="p172734016186"></a>2个输入</p>
<p id="p12273160191812"><a name="p12273160191812"></a><a name="p12273160191812"></a>【参数】</p>
<a name="ul1162563773217"></a><a name="ul1162563773217"></a><ul id="ul1162563773217"><li>spatial_scale：必须配置，类型：float</li><li>output_dim：必须配置，类型：int32，输出通道数</li><li>group_size：必须配置，类型：int32，编码位置敏感分数图的组数</li></ul>
<p id="p527311061814"><a name="p527311061814"></a><a name="p527311061814"></a>【约束】</p>
<p id="p1927317010187"><a name="p1927317010187"></a><a name="p1927317010187"></a>用于RFCN网络</p>
<a name="ul446655317323"></a><a name="ul446655317323"></a><ul id="ul446655317323"><li>输入Roi框的坐标信息为[roiN，roiC，roiH，roiW]，格式范围是：1&lt;= roiN &lt;=65535，roiC == 5，roiH == 1，roiW == 1</li><li>输入的featuremap维度为[xN，xC，xH，xW]<p id="p13631140133315"><a name="p13631140133315"></a><a name="p13631140133315"></a>pooledH==pooledW==groupSize &lt;= 128</p>
<p id="p1503164313312"><a name="p1503164313312"></a><a name="p1503164313312"></a>[pooledH pooledW ]表示pool框的长宽</p>
</li><li>输出的格式 y[yN， yC， yH， yW]</li><li>poolingMode == avg pooling， pooledH == pooledW == groupSize， pooledH &lt;= 128， spatialScale &gt; 0， groupSize &gt; 0， outputDim &gt; 0</li><li>1&lt;=xN&lt;=65535， roisN % xN == 0</li><li>HW_LIMIT是xh、xw的约束<p id="p530317323414"><a name="p530317323414"></a><a name="p530317323414"></a>xHW = xH * xW</p>
<p id="p964345133412"><a name="p964345133412"></a><a name="p964345133412"></a>pooledHW = pooledH * pooledW</p>
<p id="p20322114143411"><a name="p20322114143411"></a><a name="p20322114143411"></a>HW_LIMIT = （64*1024–8*1024） / 32</p>
<p id="p13221014143415"><a name="p13221014143415"></a><a name="p13221014143415"></a>xH &gt;= pooledH，xW &gt;= pooledW</p>
<p id="p9322714143410"><a name="p9322714143410"></a><a name="p9322714143410"></a>xHW &gt;= pooledHW</p>
<p id="p932281413349"><a name="p932281413349"></a><a name="p932281413349"></a>xHW/pooledHW&lt;=HW_LIMIT</p>
</li><li>多batch场景时，每个batch的roi框个数相同，且roi的batch排列顺序与feature相同</li></ul>
<p id="p327412010187"><a name="p327412010187"></a><a name="p327412010187"></a>【量化工具支持】</p>
<p id="p1727490161814"><a name="p1727490161814"></a><a name="p1727490161814"></a>是</p>
</td>
</tr>
<tr id="row1527415011185"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p172741206181"><a name="p172741206181"></a><a name="p172741206181"></a>27</p>
</td>
<td class="cellrowborder" valign="top" width="14.499999999999998%" headers="mcps1.2.5.1.2 "><p id="p11274908186"><a name="p11274908186"></a><a name="p11274908186"></a>Relu</p>
</td>
<td class="cellrowborder" valign="top" width="27.16%" headers="mcps1.2.5.1.3 "><p id="p15274190131820"><a name="p15274190131820"></a><a name="p15274190131820"></a>激活函数，同时包含普通的relu和leaky relu，可通过参数指定</p>
</td>
<td class="cellrowborder" valign="top" width="48.339999999999996%" headers="mcps1.2.5.1.4 "><p id="p1627410131817"><a name="p1627410131817"></a><a name="p1627410131817"></a>【输入】</p>
<p id="p42742014183"><a name="p42742014183"></a><a name="p42742014183"></a>1个输入</p>
<p id="p1327418018183"><a name="p1327418018183"></a><a name="p1327418018183"></a>【参数】</p>
<a name="ul199423233415"></a><a name="ul199423233415"></a><ul id="ul199423233415"><li>negative_slope：可选，类型：float，默认为0</li><li>engine：可选，类型：枚举，取值：DEFAULT=0，CAFFE=1，CUDNN=2</li></ul>
<p id="p1827420101817"><a name="p1827420101817"></a><a name="p1827420101817"></a>【约束】</p>
<p id="p18274807189"><a name="p18274807189"></a><a name="p18274807189"></a>无限制</p>
<p id="p6274100151812"><a name="p6274100151812"></a><a name="p6274100151812"></a>【量化工具支持】</p>
<p id="p12744012185"><a name="p12744012185"></a><a name="p12744012185"></a>是</p>
</td>
</tr>
<tr id="row18274180161815"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p8274301188"><a name="p8274301188"></a><a name="p8274301188"></a>28</p>
</td>
<td class="cellrowborder" valign="top" width="14.499999999999998%" headers="mcps1.2.5.1.2 "><p id="p2027418091813"><a name="p2027418091813"></a><a name="p2027418091813"></a>Reshape</p>
</td>
<td class="cellrowborder" valign="top" width="27.16%" headers="mcps1.2.5.1.3 "><p id="p142741204180"><a name="p142741204180"></a><a name="p142741204180"></a>改变输入维度</p>
</td>
<td class="cellrowborder" valign="top" width="48.339999999999996%" headers="mcps1.2.5.1.4 "><p id="p1727412001820"><a name="p1727412001820"></a><a name="p1727412001820"></a>【输入】</p>
<p id="p102746015182"><a name="p102746015182"></a><a name="p102746015182"></a>1个输入</p>
<p id="p122742021817"><a name="p122742021817"></a><a name="p122742021817"></a>【参数】</p>
<a name="ul4857154118346"></a><a name="ul4857154118346"></a><ul id="ul4857154118346"><li>shape：常量，类型：int64或int</li><li>axis：可选，类型：int32，默认为0</li><li>num_axes：可选，类型：int32，默认为-1</li></ul>
<p id="p1627414031818"><a name="p1627414031818"></a><a name="p1627414031818"></a>【约束】</p>
<p id="p1527460131815"><a name="p1527460131815"></a><a name="p1527460131815"></a>无限制</p>
<p id="p32751009187"><a name="p32751009187"></a><a name="p32751009187"></a>【量化工具支持】</p>
<p id="p827517016187"><a name="p827517016187"></a><a name="p827517016187"></a>是</p>
</td>
</tr>
<tr id="row427519010188"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p82751700185"><a name="p82751700185"></a><a name="p82751700185"></a>29</p>
</td>
<td class="cellrowborder" valign="top" width="14.499999999999998%" headers="mcps1.2.5.1.2 "><p id="p72756016186"><a name="p72756016186"></a><a name="p72756016186"></a>ROIAlign</p>
</td>
<td class="cellrowborder" valign="top" width="27.16%" headers="mcps1.2.5.1.3 "><p id="p1727512018189"><a name="p1727512018189"></a><a name="p1727512018189"></a>一种区域特征聚集的方式</p>
</td>
<td class="cellrowborder" valign="top" width="48.339999999999996%" headers="mcps1.2.5.1.4 "><p id="p427530201811"><a name="p427530201811"></a><a name="p427530201811"></a>【输入】</p>
<p id="p1727516091814"><a name="p1727516091814"></a><a name="p1727516091814"></a>至少有2个输入</p>
<p id="p027500181814"><a name="p027500181814"></a><a name="p027500181814"></a>【参数】</p>
<a name="ul840419493341"></a><a name="ul840419493341"></a><ul id="ul840419493341"><li>pooled_h：可选，类型：uint32，默认为0</li><li>pooled_w：可选，类型：uint32，默认为0</li><li>spatial_scale：可选，类型：float，默认为1</li><li>sampling_ratio：可选，类型：int32，默认为-1</li></ul>
<p id="p192753011814"><a name="p192753011814"></a><a name="p192753011814"></a>【约束】</p>
<p id="p1827514011814"><a name="p1827514011814"></a><a name="p1827514011814"></a>主要用于maskrcnn</p>
<a name="ul14225153113519"></a><a name="ul14225153113519"></a><ul id="ul14225153113519"><li>FeatureMap（特征图）约束：</li></ul>
<p id="p242761943516"><a name="p242761943516"></a><a name="p242761943516"></a>−       H * W &lt;= 5248（N&gt;1）或W * C &lt; 40960（N=1）</p>
<p id="p34279198356"><a name="p34279198356"></a><a name="p34279198356"></a>−       C &lt;= 1280</p>
<p id="p1242791903517"><a name="p1242791903517"></a><a name="p1242791903517"></a>−       （（C-1）/128+1）*pooledW &lt;= 216</p>
<a name="ul12445323193512"></a><a name="ul12445323193512"></a><ul id="ul12445323193512"><li>RoI（感兴区域）约束：</li></ul>
<p id="p184272019103515"><a name="p184272019103515"></a><a name="p184272019103515"></a>−       C=5（caffe），H=1，W=1</p>
<p id="p19427151913520"><a name="p19427151913520"></a><a name="p19427151913520"></a>−       samplingRatio*pooledW &lt;= 128且samplingRatio*pooledH &lt;= 128</p>
<p id="p5427161916353"><a name="p5427161916353"></a><a name="p5427161916353"></a>−       H &gt;= pooledH， W &gt;= pooledW</p>
<p id="p14275120201810"><a name="p14275120201810"></a><a name="p14275120201810"></a>【量化工具支持】</p>
<p id="p152752002182"><a name="p152752002182"></a><a name="p152752002182"></a>是</p>
</td>
</tr>
<tr id="row1727513011185"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p1227515091811"><a name="p1227515091811"></a><a name="p1227515091811"></a>30</p>
</td>
<td class="cellrowborder" valign="top" width="14.499999999999998%" headers="mcps1.2.5.1.2 "><p id="p20275200171816"><a name="p20275200171816"></a><a name="p20275200171816"></a>ROIPooling</p>
</td>
<td class="cellrowborder" valign="top" width="27.16%" headers="mcps1.2.5.1.3 "><p id="p1627510041811"><a name="p1627510041811"></a><a name="p1627510041811"></a>将“候选框”映射到特征图上</p>
</td>
<td class="cellrowborder" valign="top" width="48.339999999999996%" headers="mcps1.2.5.1.4 "><p id="p5275160181818"><a name="p5275160181818"></a><a name="p5275160181818"></a>【输入】</p>
<p id="p19275180191820"><a name="p19275180191820"></a><a name="p19275180191820"></a>至少有2个输入</p>
<p id="p1427513017181"><a name="p1427513017181"></a><a name="p1427513017181"></a>【参数】</p>
<a name="ul21216393359"></a><a name="ul21216393359"></a><ul id="ul21216393359"><li>pooled_h：必须设置，类型：uint32，默认为0</li><li>pooled_w：必须设置，类型：uint32，默认为0</li><li>spatial_scale：必须设置，类型：float；默认为1；乘法空间比例因子将ROI坐标从其输入比例转换为pool时使用的比例</li></ul>
<p id="p927640131818"><a name="p927640131818"></a><a name="p927640131818"></a>【约束】</p>
<p id="p227610181810"><a name="p227610181810"></a><a name="p227610181810"></a>主要用于fasterrcnn</p>
<a name="ul9237144573510"></a><a name="ul9237144573510"></a><ul id="ul9237144573510"><li>输入维度：H * W&lt;=8160；且H&lt;=120；且W&lt;=120</li><li>输出维度：pooledH &lt;=20，且pooledW &lt;=20</li></ul>
<p id="p5276120171820"><a name="p5276120171820"></a><a name="p5276120171820"></a>【量化工具支持】</p>
<p id="p14276140161811"><a name="p14276140161811"></a><a name="p14276140161811"></a>是</p>
</td>
</tr>
<tr id="row5276402180"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p8276130171815"><a name="p8276130171815"></a><a name="p8276130171815"></a>31</p>
</td>
<td class="cellrowborder" valign="top" width="14.499999999999998%" headers="mcps1.2.5.1.2 "><p id="p162761013182"><a name="p162761013182"></a><a name="p162761013182"></a>Scale</p>
</td>
<td class="cellrowborder" valign="top" width="27.16%" headers="mcps1.2.5.1.3 "><p id="p52762001816"><a name="p52762001816"></a><a name="p52762001816"></a>out=alpha*Input+beta</p>
</td>
<td class="cellrowborder" valign="top" width="48.339999999999996%" headers="mcps1.2.5.1.4 "><p id="p12276905189"><a name="p12276905189"></a><a name="p12276905189"></a>【输入】</p>
<p id="p827618081814"><a name="p827618081814"></a><a name="p827618081814"></a>2个输入，input的dim为4</p>
<p id="p32764081815"><a name="p32764081815"></a><a name="p32764081815"></a>【参数】</p>
<a name="ul641295663511"></a><a name="ul641295663511"></a><ul id="ul641295663511"><li>axis：可选，类型：int32，默认为1，仅支持axis为1或者-3</li><li>num_axes：可选，类型：int32，默认为1</li><li>filler：可选；filler被忽略，除非只给1个bottom且scale是学习参数</li><li>bias_term：可选，类型：bool，默认为false；是否也学习bias（相当于ScaleLayer + BiasLayer，但可能更有效率），使用bias_filler初始化</li><li>bias_filler：可选，默认为0</li></ul>
<p id="p132771402187"><a name="p132771402187"></a><a name="p132771402187"></a>【约束】</p>
<p id="p152776017188"><a name="p152776017188"></a><a name="p152776017188"></a>scale，bias的shape只支持（n，c，1，1），且c维度与input的c维度相等</p>
<p id="p82771001184"><a name="p82771001184"></a><a name="p82771001184"></a>【量化工具支持】</p>
<p id="p10277110111814"><a name="p10277110111814"></a><a name="p10277110111814"></a>是</p>
</td>
</tr>
<tr id="row627720010185"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p102773091810"><a name="p102773091810"></a><a name="p102773091810"></a>32</p>
</td>
<td class="cellrowborder" valign="top" width="14.499999999999998%" headers="mcps1.2.5.1.2 "><p id="p1627718010189"><a name="p1627718010189"></a><a name="p1627718010189"></a>ShuffleChannel</p>
</td>
<td class="cellrowborder" valign="top" width="27.16%" headers="mcps1.2.5.1.3 "><p id="p1427714081817"><a name="p1427714081817"></a><a name="p1427714081817"></a>帮助信息在特征通道交叉流动</p>
</td>
<td class="cellrowborder" valign="top" width="48.339999999999996%" headers="mcps1.2.5.1.4 "><p id="p152771005189"><a name="p152771005189"></a><a name="p152771005189"></a>【输入】</p>
<p id="p182778010184"><a name="p182778010184"></a><a name="p182778010184"></a>1个输入</p>
<p id="p827770151814"><a name="p827770151814"></a><a name="p827770151814"></a>【参数】</p>
<p id="p727710141818"><a name="p727710141818"></a><a name="p727710141818"></a>group：可选，类型：uint32，默认为1</p>
<p id="p12771106182"><a name="p12771106182"></a><a name="p12771106182"></a>【约束】</p>
<p id="p227750181817"><a name="p227750181817"></a><a name="p227750181817"></a>无限制</p>
<p id="p1327715011183"><a name="p1327715011183"></a><a name="p1327715011183"></a>【量化工具支持】</p>
<p id="p142771203188"><a name="p142771203188"></a><a name="p142771203188"></a>是</p>
</td>
</tr>
<tr id="row1827720020183"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p527715021818"><a name="p527715021818"></a><a name="p527715021818"></a>33</p>
</td>
<td class="cellrowborder" valign="top" width="14.499999999999998%" headers="mcps1.2.5.1.2 "><p id="p2027740171816"><a name="p2027740171816"></a><a name="p2027740171816"></a>Sigmoid</p>
</td>
<td class="cellrowborder" valign="top" width="27.16%" headers="mcps1.2.5.1.3 "><p id="p827740181811"><a name="p827740181811"></a><a name="p827740181811"></a>激活函数</p>
</td>
<td class="cellrowborder" valign="top" width="48.339999999999996%" headers="mcps1.2.5.1.4 "><p id="p527713019186"><a name="p527713019186"></a><a name="p527713019186"></a>【输入】</p>
<p id="p102777061818"><a name="p102777061818"></a><a name="p102777061818"></a>1个输入</p>
<p id="p12277170161818"><a name="p12277170161818"></a><a name="p12277170161818"></a>【参数】</p>
<p id="p92775012180"><a name="p92775012180"></a><a name="p92775012180"></a>engine：可选，类型：枚举，取值：DEFAULT=0，CAFFE=1，CUDNN=2</p>
<p id="p172775010185"><a name="p172775010185"></a><a name="p172775010185"></a>【约束】</p>
<p id="p027740131816"><a name="p027740131816"></a><a name="p027740131816"></a>无限制</p>
<p id="p13277190151813"><a name="p13277190151813"></a><a name="p13277190151813"></a>【量化工具支持】</p>
<p id="p92772013189"><a name="p92772013189"></a><a name="p92772013189"></a>是</p>
</td>
</tr>
<tr id="row42779021817"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p172774061812"><a name="p172774061812"></a><a name="p172774061812"></a>34</p>
</td>
<td class="cellrowborder" valign="top" width="14.499999999999998%" headers="mcps1.2.5.1.2 "><p id="p1327730161817"><a name="p1327730161817"></a><a name="p1327730161817"></a>Slice</p>
</td>
<td class="cellrowborder" valign="top" width="27.16%" headers="mcps1.2.5.1.3 "><p id="p2277201181"><a name="p2277201181"></a><a name="p2277201181"></a>将输入分解成多个输出</p>
</td>
<td class="cellrowborder" valign="top" width="48.339999999999996%" headers="mcps1.2.5.1.4 "><p id="p16277301183"><a name="p16277301183"></a><a name="p16277301183"></a>【输入】</p>
<p id="p132772015182"><a name="p132772015182"></a><a name="p132772015182"></a>1个输入</p>
<p id="p172771803189"><a name="p172771803189"></a><a name="p172771803189"></a>【参数】</p>
<a name="ul6189494368"></a><a name="ul6189494368"></a><ul id="ul6189494368"><li>slice_dim：可选，类型：uint32，默认为1；axis和slice_dim不能同时存在</li><li>slice_point：数组；类型：uint32</li><li>axis：可选，类型：int32，默认为1（表示沿channel拼接）</li></ul>
<p id="p7278504183"><a name="p7278504183"></a><a name="p7278504183"></a>【约束】</p>
<p id="p927814016188"><a name="p927814016188"></a><a name="p927814016188"></a>无限制</p>
<p id="p192781909188"><a name="p192781909188"></a><a name="p192781909188"></a>【输出】</p>
<p id="p122786017183"><a name="p122786017183"></a><a name="p122786017183"></a>无限制</p>
<p id="p192787015187"><a name="p192787015187"></a><a name="p192787015187"></a>【量化工具支持】</p>
<p id="p1327810141815"><a name="p1327810141815"></a><a name="p1327810141815"></a>是</p>
</td>
</tr>
<tr id="row8278160171814"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p22781205182"><a name="p22781205182"></a><a name="p22781205182"></a>35</p>
</td>
<td class="cellrowborder" valign="top" width="14.499999999999998%" headers="mcps1.2.5.1.2 "><p id="p92781041817"><a name="p92781041817"></a><a name="p92781041817"></a>Softmax</p>
</td>
<td class="cellrowborder" valign="top" width="27.16%" headers="mcps1.2.5.1.3 "><p id="p527812081816"><a name="p527812081816"></a><a name="p527812081816"></a>归一化逻辑函数</p>
</td>
<td class="cellrowborder" valign="top" width="48.339999999999996%" headers="mcps1.2.5.1.4 "><p id="p11278190131817"><a name="p11278190131817"></a><a name="p11278190131817"></a>【输入】</p>
<p id="p127815021817"><a name="p127815021817"></a><a name="p127815021817"></a>1个输入</p>
<p id="p192781805189"><a name="p192781805189"></a><a name="p192781805189"></a>【参数】</p>
<a name="ul15674153514364"></a><a name="ul15674153514364"></a><ul id="ul15674153514364"><li>engine：可选，取值：DEFAULT=0，CAFFE=1，CUDNN=2</li><li>axis：可选，类型：int32，默认为1；表示沿哪个axis作softmax</li></ul>
<p id="p73791333133614"><a name="p73791333133614"></a><a name="p73791333133614"></a>【约束】</p>
<p id="p3379163383618"><a name="p3379163383618"></a><a name="p3379163383618"></a>输入4维时可以针对每一维做softmax：</p>
<p id="p133792330363"><a name="p133792330363"></a><a name="p133792330363"></a>根据分类的轴不同，计算边界分别为：</p>
<a name="ul14915203719"></a><a name="ul14915203719"></a><ul id="ul14915203719"><li>axis=1时，c&lt;=（（256*1024/4）-8*1024-256）/2</li><li>axis=0时，n&lt;=（56*1024-256）/2</li><li>axis=2时，W=1， 0&lt;h&lt;（1024*1024/32）</li><li>axis=3时，0&lt;W&lt;（1024*1024/32）</li></ul>
<p id="p133808332361"><a name="p133808332361"></a><a name="p133808332361"></a>输入维度不足4维时，仅支持对最后一维做softmax计算，并且最后一维不超过46080</p>
<p id="p82784071816"><a name="p82784071816"></a><a name="p82784071816"></a>【量化工具支持】</p>
<p id="p122782091818"><a name="p122782091818"></a><a name="p122782091818"></a>是</p>
</td>
</tr>
<tr id="row18278160151817"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p1427850181813"><a name="p1427850181813"></a><a name="p1427850181813"></a>36</p>
</td>
<td class="cellrowborder" valign="top" width="14.499999999999998%" headers="mcps1.2.5.1.2 "><p id="p1427820141810"><a name="p1427820141810"></a><a name="p1427820141810"></a>Tanh</p>
</td>
<td class="cellrowborder" valign="top" width="27.16%" headers="mcps1.2.5.1.3 "><p id="p427810151812"><a name="p427810151812"></a><a name="p427810151812"></a>激活函数</p>
</td>
<td class="cellrowborder" valign="top" width="48.339999999999996%" headers="mcps1.2.5.1.4 "><p id="p4278305188"><a name="p4278305188"></a><a name="p4278305188"></a>【输入】</p>
<p id="p17278703188"><a name="p17278703188"></a><a name="p17278703188"></a>1个输入</p>
<p id="p1627813031820"><a name="p1627813031820"></a><a name="p1627813031820"></a>【参数】</p>
<p id="p182781403187"><a name="p182781403187"></a><a name="p182781403187"></a>engine：可选，类型：枚举，取值：DEFAULT=0，CAFFE=1，CUDNN=2</p>
<p id="p32781404180"><a name="p32781404180"></a><a name="p32781404180"></a>【约束】</p>
<p id="p112787091812"><a name="p112787091812"></a><a name="p112787091812"></a>输入tensor元素个数不超过INT32_MAX</p>
<p id="p7279190151814"><a name="p7279190151814"></a><a name="p7279190151814"></a>【量化工具支持】</p>
<p id="p1327916041818"><a name="p1327916041818"></a><a name="p1327916041818"></a>是</p>
</td>
</tr>
<tr id="row10279150101813"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p202791702186"><a name="p202791702186"></a><a name="p202791702186"></a>37</p>
</td>
<td class="cellrowborder" valign="top" width="14.499999999999998%" headers="mcps1.2.5.1.2 "><p id="p1027940181811"><a name="p1027940181811"></a><a name="p1027940181811"></a>Upsample</p>
</td>
<td class="cellrowborder" valign="top" width="27.16%" headers="mcps1.2.5.1.3 "><p id="p1527940171818"><a name="p1527940171818"></a><a name="p1527940171818"></a>maxpool的反向传播过程</p>
</td>
<td class="cellrowborder" valign="top" width="48.339999999999996%" headers="mcps1.2.5.1.4 "><p id="p162798071815"><a name="p162798071815"></a><a name="p162798071815"></a>【输入】</p>
<p id="p12791903187"><a name="p12791903187"></a><a name="p12791903187"></a>2个输入</p>
<p id="p127914071818"><a name="p127914071818"></a><a name="p127914071818"></a>【参数】</p>
<p id="p12279505185"><a name="p12279505185"></a><a name="p12279505185"></a>scale：可选，类型：int32，默认为1</p>
<p id="p1527911014181"><a name="p1527911014181"></a><a name="p1527911014181"></a>【约束】</p>
<p id="p1127911041812"><a name="p1127911041812"></a><a name="p1127911041812"></a>无限制</p>
<p id="p8279100131815"><a name="p8279100131815"></a><a name="p8279100131815"></a>【量化工具支持】</p>
<p id="p42799012186"><a name="p42799012186"></a><a name="p42799012186"></a>是</p>
</td>
</tr>
<tr id="row19279110131813"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p427911041819"><a name="p427911041819"></a><a name="p427911041819"></a>38</p>
</td>
<td class="cellrowborder" valign="top" width="14.499999999999998%" headers="mcps1.2.5.1.2 "><p id="p122798001812"><a name="p122798001812"></a><a name="p122798001812"></a>SSDDetectionOutput</p>
</td>
<td class="cellrowborder" valign="top" width="27.16%" headers="mcps1.2.5.1.3 "><p id="p8279109181"><a name="p8279109181"></a><a name="p8279109181"></a>SSD网络检测输出</p>
</td>
<td class="cellrowborder" valign="top" width="48.339999999999996%" headers="mcps1.2.5.1.4 "><p id="p112795081812"><a name="p112795081812"></a><a name="p112795081812"></a>【输入】</p>
<p id="p132791031813"><a name="p132791031813"></a><a name="p132791031813"></a>3个输入</p>
<p id="p11279190121819"><a name="p11279190121819"></a><a name="p11279190121819"></a>【参数】</p>
<a name="ul57133528374"></a><a name="ul57133528374"></a><ul id="ul57133528374"><li>num_classes：必选，类型：int32，要预测的类数</li><li>share_location：可选，类型：bool，默认为true（表示不同类间共享bounding box）</li><li>background_label_id：可选，类型：int32，默认为0</li><li>nms_param：可选，非最大抑制</li><li>save_output_param：可选，用于保存检测结果</li><li>code_type：可选，默认为CENTER_SIZE</li><li>variance_encoded_in_target：可选，类型：bool，默认为true；如果为true，方差编码在目标中，否则需要相应地调整预测偏移量</li><li>keep_top_k：可选，类型：int32，在nms步骤后每个图像要保留的总bbox数</li><li>confidence_threshold：可选，类型：float，仅考虑置信度大于阈值的检测；如果没有设置，考虑所有的box</li><li>nms_threshold：可选，类型：float</li><li>top_k：可选，类型：int32</li><li>boxes：可选，类型：int32，默认为1</li><li>relative：可选，类型：bool，默认为true</li><li>objectness_threshold，可选，类型：float，默认为0.5</li><li>class_threshold：可选，类型：float，默认为0.5</li><li>biases：数组</li><li>general_nms_param：可选</li></ul>
<p id="p182817031810"><a name="p182817031810"></a><a name="p182817031810"></a>【约束】</p>
<a name="ul1350416713389"></a><a name="ul1350416713389"></a><ul id="ul1350416713389"><li>只支持SSD网络</li><li>preTopK和postTopK的取值范围当前仅支持1~1024</li><li>shareLocation仅支持true</li><li>nmsEta仅支持1</li><li>numClasses支持的范围是1~2048</li><li>code_type仅支持CENTER_SIZE</li><li>nms_threshold和confidence_threshold的范围为0.0~1.0</li></ul>
<p id="p112819019185"><a name="p112819019185"></a><a name="p112819019185"></a>【量化工具支持】</p>
<p id="p4281503188"><a name="p4281503188"></a><a name="p4281503188"></a>是</p>
</td>
</tr>
<tr id="row82816021820"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p20281190151820"><a name="p20281190151820"></a><a name="p20281190151820"></a>39</p>
</td>
<td class="cellrowborder" valign="top" width="14.499999999999998%" headers="mcps1.2.5.1.2 "><p id="p1628110041820"><a name="p1628110041820"></a><a name="p1628110041820"></a>Reorg</p>
</td>
<td class="cellrowborder" valign="top" width="27.16%" headers="mcps1.2.5.1.3 "><p id="p1428113081810"><a name="p1428113081810"></a><a name="p1428113081810"></a>实时物体检测</p>
</td>
<td class="cellrowborder" valign="top" width="48.339999999999996%" headers="mcps1.2.5.1.4 "><p id="p16281110121814"><a name="p16281110121814"></a><a name="p16281110121814"></a>【输入】</p>
<p id="p628117011188"><a name="p628117011188"></a><a name="p628117011188"></a>1个输入</p>
<p id="p1928150121811"><a name="p1928150121811"></a><a name="p1928150121811"></a>【参数】</p>
<a name="ul8370714183810"></a><a name="ul8370714183810"></a><ul id="ul8370714183810"><li>stride：可选，类型：uint32，默认为2</li><li>reverse：可选，类型：bool，默认为false</li></ul>
<p id="p192834013189"><a name="p192834013189"></a><a name="p192834013189"></a>【约束】</p>
<p id="p152831901183"><a name="p152831901183"></a><a name="p152831901183"></a>只用于YOLOV2</p>
<p id="p162837021813"><a name="p162837021813"></a><a name="p162837021813"></a>【量化工具支持】</p>
<p id="p1328317091819"><a name="p1328317091819"></a><a name="p1328317091819"></a>否</p>
</td>
</tr>
<tr id="row128315041813"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p172836016188"><a name="p172836016188"></a><a name="p172836016188"></a>40</p>
</td>
<td class="cellrowborder" valign="top" width="14.499999999999998%" headers="mcps1.2.5.1.2 "><p id="p128313017184"><a name="p128313017184"></a><a name="p128313017184"></a>Reverse</p>
</td>
<td class="cellrowborder" valign="top" width="27.16%" headers="mcps1.2.5.1.3 "><p id="p4283120101819"><a name="p4283120101819"></a><a name="p4283120101819"></a>逆转</p>
</td>
<td class="cellrowborder" valign="top" width="48.339999999999996%" headers="mcps1.2.5.1.4 "><p id="p628319012186"><a name="p628319012186"></a><a name="p628319012186"></a>【输入】</p>
<p id="p14283100121813"><a name="p14283100121813"></a><a name="p14283100121813"></a>1个输入</p>
<p id="p228320017188"><a name="p228320017188"></a><a name="p228320017188"></a>【参数】</p>
<p id="p62836019180"><a name="p62836019180"></a><a name="p62836019180"></a>axis：可选，类型：int32，默认为1；控制需翻转的数据轴，内容的布局不会被颠倒</p>
<p id="p228310010186"><a name="p228310010186"></a><a name="p228310010186"></a>【约束】</p>
<p id="p328319041818"><a name="p328319041818"></a><a name="p328319041818"></a>无限制</p>
<p id="p14283104185"><a name="p14283104185"></a><a name="p14283104185"></a>【量化工具支持】</p>
<p id="p19283707188"><a name="p19283707188"></a><a name="p19283707188"></a>否</p>
</td>
</tr>
<tr id="row72835014182"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p428316041816"><a name="p428316041816"></a><a name="p428316041816"></a>41</p>
</td>
<td class="cellrowborder" valign="top" width="14.499999999999998%" headers="mcps1.2.5.1.2 "><p id="p828318041813"><a name="p828318041813"></a><a name="p828318041813"></a>LeakyRelu</p>
</td>
<td class="cellrowborder" valign="top" width="27.16%" headers="mcps1.2.5.1.3 "><p id="p1328313018187"><a name="p1328313018187"></a><a name="p1328313018187"></a>LeakyRelu激活函数</p>
</td>
<td class="cellrowborder" valign="top" width="48.339999999999996%" headers="mcps1.2.5.1.4 "><p id="p928319013184"><a name="p928319013184"></a><a name="p928319013184"></a>【输入】</p>
<p id="p182839071812"><a name="p182839071812"></a><a name="p182839071812"></a>1个输入</p>
<p id="p12283180121813"><a name="p12283180121813"></a><a name="p12283180121813"></a>【参数】</p>
<p id="p828316091814"><a name="p828316091814"></a><a name="p828316091814"></a>同Relu</p>
<p id="p328380121817"><a name="p328380121817"></a><a name="p328380121817"></a>【约束】</p>
<p id="p122831704180"><a name="p122831704180"></a><a name="p122831704180"></a>无限制</p>
<p id="p1828310161814"><a name="p1828310161814"></a><a name="p1828310161814"></a>【量化工具支持】</p>
<p id="p9283140141815"><a name="p9283140141815"></a><a name="p9283140141815"></a>是</p>
</td>
</tr>
<tr id="row11283120131820"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p182834010184"><a name="p182834010184"></a><a name="p182834010184"></a>42</p>
</td>
<td class="cellrowborder" valign="top" width="14.499999999999998%" headers="mcps1.2.5.1.2 "><p id="p528316071819"><a name="p528316071819"></a><a name="p528316071819"></a>YOLODetectionOutput</p>
</td>
<td class="cellrowborder" valign="top" width="27.16%" headers="mcps1.2.5.1.3 "><p id="p1628315019185"><a name="p1628315019185"></a><a name="p1628315019185"></a>YOLO网络检测输出</p>
</td>
<td class="cellrowborder" valign="top" width="48.339999999999996%" headers="mcps1.2.5.1.4 "><p id="p828417016186"><a name="p828417016186"></a><a name="p828417016186"></a>【输入】</p>
<p id="p228490131810"><a name="p228490131810"></a><a name="p228490131810"></a>4个输入</p>
<p id="p328412061815"><a name="p328412061815"></a><a name="p328412061815"></a>【参数】</p>
<a name="ul789053573819"></a><a name="ul789053573819"></a><ul id="ul789053573819"><li>num_classes：必选，类型：int32，要预测的类数</li><li>share_location：可选，类型：bool，默认为true（表示不同类间共享bounding box）</li><li>background_label_id：可选，类型：int32，默认为0</li><li>nms_param：可选，非最大抑制</li><li>save_output_param：可选，用于保存检测结果</li><li>code_type：可选，默认为CENTER_SIZE</li><li>variance_encoded_in_target：可选，类型：bool，默认为true；如果为true，方差编码在目标中，否则需要相应地调整预测偏移量</li><li>keep_top_k：可选，类型：int32，在nms步骤后每个图像要保留的总bbox数</li><li>confidence_threshold：可选，类型：float，仅考虑置信度大于阈值的检测；如果没有设置，考虑所有的box</li><li>nms_threshold：可选，类型：float</li><li>top_k：可选，类型：int32</li><li>boxes：可选，类型：int32，默认为1</li><li>relative：可选，类型：bool，默认为true</li><li>objectness_threshold，可选，类型：float，默认为0.5</li><li>class_threshold：可选，类型：float，默认为0.5</li><li>biases：数组</li><li>general_nms_param：可选</li></ul>
<p id="p2028430121811"><a name="p2028430121811"></a><a name="p2028430121811"></a>【约束】</p>
<a name="ul20761154203811"></a><a name="ul20761154203811"></a><ul id="ul20761154203811"><li>只用于YOLOV2</li><li>classNUm&lt;10240；anchorBox &lt;= 8</li><li>W &lt;= 1536</li><li>yolodetectionoutput的上层必须为yoloregion算子</li></ul>
<p id="p1128411021814"><a name="p1128411021814"></a><a name="p1128411021814"></a>【量化工具支持】</p>
<p id="p82844011819"><a name="p82844011819"></a><a name="p82844011819"></a>否</p>
</td>
</tr>
</tbody>
</table>

