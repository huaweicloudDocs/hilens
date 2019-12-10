# Tensorflow算子边界<a name="hilens_02_0060"></a>

“.om”模型支持的Tensorflow算子边界如[表1](#table8549141115462)所示。

**表 1**  TensorFlow算子边界

<a name="table8549141115462"></a>
<table><thead align="left"><tr id="row6157415174615"><th class="cellrowborder" valign="top" width="10%" id="mcps1.2.5.1.1"><p id="p315751518469"><a name="p315751518469"></a><a name="p315751518469"></a><strong id="b315791524611"><a name="b315791524611"></a><a name="b315791524611"></a>序号</strong></p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p7158315174619"><a name="p7158315174619"></a><a name="p7158315174619"></a><strong id="b1415891554616"><a name="b1415891554616"></a><a name="b1415891554616"></a>Python  API</strong></p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.3"><p id="p1215811554614"><a name="p1215811554614"></a><a name="p1215811554614"></a><strong id="b10158171584617"><a name="b10158171584617"></a><a name="b10158171584617"></a>C++  API</strong></p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.5.1.4"><p id="p81585155460"><a name="p81585155460"></a><a name="p81585155460"></a><strong id="b115891584615"><a name="b115891584615"></a><a name="b115891584615"></a>边界</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="row1315811153462"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p1815801574611"><a name="p1815801574611"></a><a name="p1815801574611"></a>1</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p121584151463"><a name="p121584151463"></a><a name="p121584151463"></a>tf.nn.avg_pool</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p715814154466"><a name="p715814154466"></a><a name="p715814154466"></a>AvgPool</p>
<p id="p131581156464"><a name="p131581156464"></a><a name="p131581156464"></a>Type：Mean</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p815891516466"><a name="p815891516466"></a><a name="p815891516466"></a>【参数】</p>
<a name="ul67243153489"></a><a name="ul67243153489"></a><ul id="ul67243153489"><li>value：4-D tensor，格式：[batch，height，width，channels]，数据类型：float32</li><li>ksize：包含四个int的列表或元组，其中每个值对应相应维度的窗口大小</li><li>strides：包含四个int的列表或元组，其中每个值对应相应维度的滑动步长</li><li>padding：类型：string，值必须为’VALID’或’SAME’</li><li>data_format：类型：string，值为'NHWC'（默认值）或'NCHW'</li><li>name：可选参数，类型：string</li></ul>
<p id="p121581815164613"><a name="p121581815164613"></a><a name="p121581815164613"></a>【约束】</p>
<a name="ul775132254815"></a><a name="ul775132254815"></a><ul id="ul775132254815"><li>kernelH&lt;=inputH+padTop+padBottom</li><li>kernelW&lt;=inputW+padLeft+padRight</li><li>padTop&lt;windowH</li><li>padBottom&lt;windowH</li><li>padLeft&lt;windowW</li><li>padRight&lt;windowW</li></ul>
<p id="p19158115174612"><a name="p19158115174612"></a><a name="p19158115174612"></a>除公共约束外，还需满足下列某一场景支持范围：</p>
<div class="p" id="p10158715144619"><a name="p10158715144619"></a><a name="p10158715144619"></a>global pool模式只支持下列场景：<a name="ul192542181514"></a><a name="ul192542181514"></a><ul id="ul192542181514"><li>outputH==1 &amp;&amp; outputW==1 &amp;&amp; kernelH&gt;=inputH &amp;&amp; kernelW&gt;=inputW</li><li>inputH*inputW&lt;=10000</li></ul>
</div>
<p id="p191581115134613"><a name="p191581115134613"></a><a name="p191581115134613"></a>【输出】</p>
<p id="p615811517468"><a name="p615811517468"></a><a name="p615811517468"></a>1个tensor，数据类型与value相同</p>
<p id="p101596153466"><a name="p101596153466"></a><a name="p101596153466"></a>【量化工具支持】</p>
<p id="p1715931534616"><a name="p1715931534616"></a><a name="p1715931534616"></a>是</p>
</td>
</tr>
<tr id="row215961504614"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p8159151518467"><a name="p8159151518467"></a><a name="p8159151518467"></a>2</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p81592152463"><a name="p81592152463"></a><a name="p81592152463"></a>tf.nn.max_pool</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p181591615104617"><a name="p181591615104617"></a><a name="p181591615104617"></a>MaxPool</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p215910152461"><a name="p215910152461"></a><a name="p215910152461"></a>同tf.nn.avg_pool</p>
</td>
</tr>
<tr id="row9159191517463"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p12159101594618"><a name="p12159101594618"></a><a name="p12159101594618"></a>3</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p415914158469"><a name="p415914158469"></a><a name="p415914158469"></a>tf.nn.conv2d</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p015991512461"><a name="p015991512461"></a><a name="p015991512461"></a>Conv2D</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p1159121518464"><a name="p1159121518464"></a><a name="p1159121518464"></a>【参数】</p>
<a name="ul9701195916486"></a><a name="ul9701195916486"></a><ul id="ul9701195916486"><li>value：4-D tensor，格式：[batch，height，width，channels]</li><li>数据类型：float32</li><li>filter：1个常量tensor，数据类型与维度与value相同，[filter_height，filter_width，in_channels，out_channels]</li><li>strides：非空，包含四个int的列表或元组，其中每个值对应相应维度的滑动步长</li><li>padding：非空，类型：string，值必须为’VALID’或’SAME’</li><li>use_cudnn_on_gpu：类型：bool，默认为‘True’</li><li>data_format：非空，类型：string，值为'NHWC'（默认值）或'NCHW'</li><li>dilations：可选参数，1个int列表（长度为4）；默认为[1，1，1，1]，对应输入的每一维；如果k&gt;1，相应维度做filter间跳过k-1个单元；维度顺序由data_format决定；dilations的batch与depth维度上的值必须是1</li><li>name：可选参数，类型：string</li></ul>
<p id="p115991534612"><a name="p115991534612"></a><a name="p115991534612"></a>【约束】</p>
<a name="ul43231910204912"></a><a name="ul43231910204912"></a><ul id="ul43231910204912"><li>（inputW + padWHead + padWTail） &gt;= （（（FilterW- 1） * dilationW） + 1）</li><li>（inputW + padWHead + padWTail） /StrideW + 1 &lt;= INT32_MAX</li><li>（inputH + padHHead + padHTail） &gt;= （（（FilterH- 1） * dilationH） + 1）</li><li>（inputH + padHHead + padHTail） /StrideH + 1 &lt;= INT32_MAX</li><li>0 &lt;= Pad &lt; 256， 0 &lt; FilterSize &lt; 256， 0 &lt; Stride &lt; 64， 1 &lt;= dilationsize &lt; 256</li></ul>
<p id="p12159111564610"><a name="p12159111564610"></a><a name="p12159111564610"></a>【输出】</p>
<p id="p01591715144620"><a name="p01591715144620"></a><a name="p01591715144620"></a>Tensor，数据类型与Value相同</p>
<p id="p71592015144619"><a name="p71592015144619"></a><a name="p71592015144619"></a>【量化工具支持】</p>
<p id="p7159171514613"><a name="p7159171514613"></a><a name="p7159171514613"></a>是</p>
</td>
</tr>
<tr id="row1615911544611"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p0159615144620"><a name="p0159615144620"></a><a name="p0159615144620"></a>4</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p81591815184610"><a name="p81591815184610"></a><a name="p81591815184610"></a>tf.concat</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p111597153461"><a name="p111597153461"></a><a name="p111597153461"></a>Concat</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p1616091574618"><a name="p1616091574618"></a><a name="p1616091574618"></a>【参数】</p>
<a name="ul111192111499"></a><a name="ul111192111499"></a><ul id="ul111192111499"><li>values：输入，包含tensor对象的列表或单个tensor，除要拼接的维度外，其他维度上的值要一致</li><li>axis：0-D tensor，类型：int32，指定要拼接的维度，范围在[-rank（values），rank（values）]；python中，索引以0开始，axis为正值时，表示对第axis维拼接；axis为负值时，对第axis+rank（values）维拼接</li></ul>
<p id="p15160815164613"><a name="p15160815164613"></a><a name="p15160815164613"></a>【约束】</p>
<p id="p0160161514462"><a name="p0160161514462"></a><a name="p0160161514462"></a>输入的tensor，除了进行concat的维度外，其他维度的size必须相等</p>
<p id="p11160515194615"><a name="p11160515194615"></a><a name="p11160515194615"></a>输入的的tensor个数范围属于[1，1000]</p>
<p id="p1516011514610"><a name="p1516011514610"></a><a name="p1516011514610"></a>【输出】</p>
<p id="p11160121584619"><a name="p11160121584619"></a><a name="p11160121584619"></a>1个tensor，为输入tensors拼接后的结果</p>
<p id="p151601215134615"><a name="p151601215134615"></a><a name="p151601215134615"></a>【量化工具支持】</p>
<p id="p10160815124617"><a name="p10160815124617"></a><a name="p10160815124617"></a>是</p>
</td>
</tr>
<tr id="row5160915204616"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p13160131510461"><a name="p13160131510461"></a><a name="p13160131510461"></a>5</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p18163131517464"><a name="p18163131517464"></a><a name="p18163131517464"></a>tf.matmul</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p121631415174620"><a name="p121631415174620"></a><a name="p121631415174620"></a>MatMul</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p3163161564617"><a name="p3163161564617"></a><a name="p3163161564617"></a>【参数】</p>
<a name="ul18348123512496"></a><a name="ul18348123512496"></a><ul id="ul18348123512496"><li>a：非常量tensor，rank&gt;=2，类型：float32</li><li>b：常量tensor，类型与rank同a</li><li>transpose_a：如果属性为True，a在乘法前做转置</li><li>transpose_b：如果属性为True，b在乘法前做转置；transpose_a属性为False，transpose_b属性也为False</li><li>adjoint_a：如果属性为True，a在乘法前被共轭和转置</li><li>adjoint_b：如果属性为True，b在乘法前被共轭和转置</li><li>a_is_sparse：如果属性为True，a被看做是稀疏矩阵</li><li>b_is_sparse：如果属性为True，b被看做是稀疏矩阵</li><li>name：可选参数</li></ul>
<p id="p13163121534612"><a name="p13163121534612"></a><a name="p13163121534612"></a>【约束】</p>
<a name="ul1765874144919"></a><a name="ul1765874144919"></a><ul id="ul1765874144919"><li>weight的转置属性为false</li><li>不能支持两个tensor相乘，只能支持1个tensor乘以1个常量</li></ul>
<p id="p1116317156463"><a name="p1116317156463"></a><a name="p1116317156463"></a>【输出】</p>
<p id="p16163915124613"><a name="p16163915124613"></a><a name="p16163915124613"></a>1个tensor，类型同a与b</p>
<p id="p616331584612"><a name="p616331584612"></a><a name="p616331584612"></a>【量化工具支持】</p>
<p id="p216371512466"><a name="p216371512466"></a><a name="p216371512466"></a>否</p>
</td>
</tr>
<tr id="row0163101514617"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p111631515184613"><a name="p111631515184613"></a><a name="p111631515184613"></a>6</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p51638152462"><a name="p51638152462"></a><a name="p51638152462"></a>tf.nn.fused_batch_norm</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p1816381515465"><a name="p1816381515465"></a><a name="p1816381515465"></a>FusedBatchNorm</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p15163615194611"><a name="p15163615194611"></a><a name="p15163615194611"></a>【参数】</p>
<a name="ul17382185154916"></a><a name="ul17382185154916"></a><ul id="ul17382185154916"><li>x：输入，4-D tensor，类型：float32</li><li>scale：1-D tensor，用于缩放</li><li>offset：1-D tensor，偏差</li><li>mean：1-D tensor，用于推理总体均值</li><li>variance：1-D tensor，用于推理总体方差</li><li>epsilon：在x的方差中添加的1个小的浮点数</li><li>data_format：x的数据格式，值为'NHWC'（默认）或'NCHW'</li><li>is_training：bool值，用于指定操作是用于训练还是推断</li><li>name：操作的名称，可选参数</li></ul>
<p id="p6164111513460"><a name="p6164111513460"></a><a name="p6164111513460"></a>【约束】</p>
<p id="p1316421514617"><a name="p1316421514617"></a><a name="p1316421514617"></a>scale，bias，mean，var的shape只支持（1，C，1，1），且c维度与input的c维度相等</p>
<p id="p81647152461"><a name="p81647152461"></a><a name="p81647152461"></a>【输出】</p>
<a name="ul13856205915496"></a><a name="ul13856205915496"></a><ul id="ul13856205915496"><li>y：标准化、缩放、偏移x的4-D tensor</li><li>batch_mean：1-D tensor，表示x的均值</li><li>batch_var：1-D tensor，表示x的方差</li></ul>
<p id="p31641115134618"><a name="p31641115134618"></a><a name="p31641115134618"></a>【量化工具支持】</p>
<p id="p1816413153469"><a name="p1816413153469"></a><a name="p1816413153469"></a>否</p>
</td>
</tr>
<tr id="row516441544617"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p11641515124618"><a name="p11641515124618"></a><a name="p11641515124618"></a>7</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p5164131584615"><a name="p5164131584615"></a><a name="p5164131584615"></a>tf.abs</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p11164171519467"><a name="p11164171519467"></a><a name="p11164171519467"></a>Abs</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p416461511464"><a name="p416461511464"></a><a name="p416461511464"></a>【参数】</p>
<a name="ul1735412545019"></a><a name="ul1735412545019"></a><ul id="ul1735412545019"><li>x：tensor或稀疏tensor，类型：float32</li><li>name：操作的名称，可选参数</li></ul>
<p id="p1216451512465"><a name="p1216451512465"></a><a name="p1216451512465"></a>【约束】</p>
<p id="p171641515104611"><a name="p171641515104611"></a><a name="p171641515104611"></a>无限制</p>
<p id="p916471517464"><a name="p916471517464"></a><a name="p916471517464"></a>【输出】</p>
<p id="p15164815164614"><a name="p15164815164614"></a><a name="p15164815164614"></a>返回x的绝对值，tensor或稀疏tensor，尺寸与类型同x</p>
<p id="p4164115104614"><a name="p4164115104614"></a><a name="p4164115104614"></a>【量化工具支持】</p>
<p id="p17164151512461"><a name="p17164151512461"></a><a name="p17164151512461"></a>是</p>
</td>
</tr>
<tr id="row1416441564615"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p121641215154614"><a name="p121641215154614"></a><a name="p121641215154614"></a>8</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p7164515104610"><a name="p7164515104610"></a><a name="p7164515104610"></a>tf.image.resize_nearest_neighbor</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p0164191512464"><a name="p0164191512464"></a><a name="p0164191512464"></a>ResizeNearestNeighbor</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p016491518461"><a name="p016491518461"></a><a name="p016491518461"></a>【参数】</p>
<a name="ul998951214508"></a><a name="ul998951214508"></a><ul id="ul998951214508"><li>images：4维tensor，[batch，height，width，channels]；3维tensor，[height，width，channels]；类型：float32</li><li>size：1维tensor，常量，2个元素（新的高宽）</li><li>method：ResizeMethod.NEARESTNEIGHBOR</li><li>align_corners：bool值，默认为False；如果为True，输入和输出的4个角像素的中心对齐，保留角像素处的值</li></ul>
<p id="p16165215174612"><a name="p16165215174612"></a><a name="p16165215174612"></a>【约束】</p>
<p id="p6165415124619"><a name="p6165415124619"></a><a name="p6165415124619"></a>无限制</p>
<p id="p13165115194610"><a name="p13165115194610"></a><a name="p13165115194610"></a>【输出】</p>
<p id="p116519154464"><a name="p116519154464"></a><a name="p116519154464"></a>shape同输入，类型：float</p>
<p id="p1516514156464"><a name="p1516514156464"></a><a name="p1516514156464"></a>【量化工具支持】</p>
<p id="p916514153463"><a name="p916514153463"></a><a name="p916514153463"></a>否</p>
</td>
</tr>
<tr id="row1165171584610"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p1116511584618"><a name="p1116511584618"></a><a name="p1116511584618"></a>9</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p3165151512463"><a name="p3165151512463"></a><a name="p3165151512463"></a>tf.image.resize_bilinear</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p416520151460"><a name="p416520151460"></a><a name="p416520151460"></a>ResizeBilinear</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p13165141554616"><a name="p13165141554616"></a><a name="p13165141554616"></a>【参数】</p>
<a name="ul48491319105019"></a><a name="ul48491319105019"></a><ul id="ul48491319105019"><li>images：4维非常量tensor，[batch，height，width，channels]；类型：float32</li><li>size：1维tensor，常量，2个元素（新的高宽）</li><li>method：ResizeMethod.BILINEAR</li><li>align_corners：bool值，默认为False；如果为True，输入和输出的4个角像素的中心对齐，保留角像素处的值</li></ul>
<p id="p2165111574616"><a name="p2165111574616"></a><a name="p2165111574616"></a>【约束】</p>
<p id="p9165161518464"><a name="p9165161518464"></a><a name="p9165161518464"></a>（outputH*outputW）/（inputH*inputW） &gt; 1/7</p>
<p id="p1516520157464"><a name="p1516520157464"></a><a name="p1516520157464"></a>【输出】</p>
<p id="p151656153462"><a name="p151656153462"></a><a name="p151656153462"></a>shape同输入，类型：float</p>
<p id="p416521510463"><a name="p416521510463"></a><a name="p416521510463"></a>【量化工具支持】</p>
<p id="p51651915144617"><a name="p51651915144617"></a><a name="p51651915144617"></a>否</p>
</td>
</tr>
<tr id="row6165131517468"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p19165115164613"><a name="p19165115164613"></a><a name="p19165115164613"></a>10</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p916531524613"><a name="p916531524613"></a><a name="p916531524613"></a>tf.cast</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p191658155466"><a name="p191658155466"></a><a name="p191658155466"></a>Cast</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p11165131519465"><a name="p11165131519465"></a><a name="p11165131519465"></a>【输入】</p>
<p id="p10625192914509"><a name="p10625192914509"></a><a name="p10625192914509"></a>类型：float32，int32，bool，int64，int16，int8，uint8，uint16，double</p>
<p id="p122382645015"><a name="p122382645015"></a><a name="p122382645015"></a>【参数】</p>
<a name="ul1551153685020"></a><a name="ul1551153685020"></a><ul id="ul1551153685020"><li>x：tensor或sparseTensor或indexedSlices</li><li>dtype：目标类型，同x支持的数据类型</li><li>name：名称（可选）</li></ul>
<p id="p1165141534619"><a name="p1165141534619"></a><a name="p1165141534619"></a>【约束】</p>
<p id="p181669154466"><a name="p181669154466"></a><a name="p181669154466"></a>无限制</p>
<p id="p141661150468"><a name="p141661150468"></a><a name="p141661150468"></a>【输出】</p>
<p id="p18166131534614"><a name="p18166131534614"></a><a name="p18166131534614"></a>tensor或sparseTensor或indexedSlices，同输入的dtype、shape</p>
<p id="p1016661514460"><a name="p1016661514460"></a><a name="p1016661514460"></a>【量化工具支持】</p>
<p id="p11166215114614"><a name="p11166215114614"></a><a name="p11166215114614"></a>无需支持</p>
</td>
</tr>
<tr id="row116671594613"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p11166215104610"><a name="p11166215104610"></a><a name="p11166215104610"></a>11</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p716601515468"><a name="p716601515468"></a><a name="p716601515468"></a>tf.nn.depthwise_conv2d</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p1416601554615"><a name="p1416601554615"></a><a name="p1416601554615"></a>DepthwiseConv2dNative</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p11166715144610"><a name="p11166715144610"></a><a name="p11166715144610"></a>【参数】</p>
<a name="ul7290114713502"></a><a name="ul7290114713502"></a><ul id="ul7290114713502"><li>input：4维</li><li>filter：4维，常量，数据格式：[filter_height，filter_width，in_channels，channel_multiplier]</li><li>strides：输入的每个维度的滑动窗口的步长，属性必须是list（int），且大小为4</li><li>padding：类型：string，值为’VALID’或’SAME’</li><li>rate：1维，大小为2；等值卷积中在height和width维度上对输入值进行采样的扩张率；如果值大于1，则步长的所有值必须为1</li><li>data_format：输入的数据格式，可以是NHWC（默认）或NCHW</li><li>name：名称（可选）</li></ul>
<p id="p016631510460"><a name="p016631510460"></a><a name="p016631510460"></a>【约束】</p>
<p id="p171661150463"><a name="p171661150463"></a><a name="p171661150463"></a>filterN=inputC=group</p>
<p id="p6166111594611"><a name="p6166111594611"></a><a name="p6166111594611"></a>【输出】</p>
<p id="p161661015144611"><a name="p161661015144611"></a><a name="p161661015144611"></a>4维tensor，形状与data_format一致，例如，对于NHWC格式，形状是[batch，out_height，out_width，in_channels * channel_multiplier]</p>
<p id="p10166101514466"><a name="p10166101514466"></a><a name="p10166101514466"></a>【量化工具支持】</p>
<p id="p21661015174616"><a name="p21661015174616"></a><a name="p21661015174616"></a>是</p>
</td>
</tr>
<tr id="row1516617159466"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p61660153466"><a name="p61660153466"></a><a name="p61660153466"></a>12</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p12166141524616"><a name="p12166141524616"></a><a name="p12166141524616"></a>tf.reshape</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p31662015164614"><a name="p31662015164614"></a><a name="p31662015164614"></a>Reshape</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p121667152462"><a name="p121667152462"></a><a name="p121667152462"></a>【参数】</p>
<a name="ul77745655015"></a><a name="ul77745655015"></a><ul id="ul77745655015"><li>tensor：输入，1个tensor</li><li>shape：定义输出的shape，常量tensor，数据类型：int64，int</li><li>name：此操作的名称（可选）</li></ul>
<p id="p3167615124620"><a name="p3167615124620"></a><a name="p3167615124620"></a>【约束】</p>
<p id="p161671515124619"><a name="p161671515124619"></a><a name="p161671515124619"></a>无限制</p>
<p id="p19167161574616"><a name="p19167161574616"></a><a name="p19167161574616"></a>【输出】</p>
<p id="p16167715184617"><a name="p16167715184617"></a><a name="p16167715184617"></a>1个tensor，类型同输入</p>
<p id="p31678155465"><a name="p31678155465"></a><a name="p31678155465"></a>【量化工具支持】</p>
<p id="p3167141514611"><a name="p3167141514611"></a><a name="p3167141514611"></a>是</p>
</td>
</tr>
<tr id="row1167151519463"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p1716701544616"><a name="p1716701544616"></a><a name="p1716701544616"></a>13</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1916711515468"><a name="p1916711515468"></a><a name="p1916711515468"></a>tf.squeeze</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p121671152461"><a name="p121671152461"></a><a name="p121671152461"></a>Squeeze</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p101676158463"><a name="p101676158463"></a><a name="p101676158463"></a>【参数】</p>
<a name="ul1364720325118"></a><a name="ul1364720325118"></a><ul id="ul1364720325118"><li>input：1个tensor，非常量输入</li><li>axis：1个int型列表，指定要移除的维度，默认为[]；不能指定非1的维度</li><li>name：此操作的名称（可选）</li><li>squeeze_dims：不推荐使用的参数，axis和dim不能同时存在</li></ul>
<p id="p9167515174613"><a name="p9167515174613"></a><a name="p9167515174613"></a>【约束】</p>
<p id="p131671215144612"><a name="p131671215144612"></a><a name="p131671215144612"></a>无限制</p>
<p id="p131682015164616"><a name="p131682015164616"></a><a name="p131682015164616"></a>【输出】</p>
<p id="p81687155461"><a name="p81687155461"></a><a name="p81687155461"></a>1个tensor，与input的类型、数据相同，但删除了1个或多个值为1的维度</p>
<p id="p916820155466"><a name="p916820155466"></a><a name="p916820155466"></a>【量化工具支持】</p>
<p id="p41681915124619"><a name="p41681915124619"></a><a name="p41681915124619"></a>是</p>
</td>
</tr>
<tr id="row016861504620"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p416812158465"><a name="p416812158465"></a><a name="p416812158465"></a>14</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p11168715104616"><a name="p11168715104616"></a><a name="p11168715104616"></a>tf.expand_dims</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p181681315144619"><a name="p181681315144619"></a><a name="p181681315144619"></a>ExpandDims</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p17168141513460"><a name="p17168141513460"></a><a name="p17168141513460"></a>【参数】</p>
<a name="ul731621317512"></a><a name="ul731621317512"></a><ul id="ul731621317512"><li>inuput：输入，1个tensor</li><li>axis：0-D（标量），指定扩展input形状的维度索引</li><li>name：输出tensor的名称</li><li>dim：0-D（标量），相当于axis，被弃用</li></ul>
<p id="p11691915144614"><a name="p11691915144614"></a><a name="p11691915144614"></a>【约束】</p>
<p id="p716911150466"><a name="p716911150466"></a><a name="p716911150466"></a>无限制</p>
<p id="p141695156461"><a name="p141695156461"></a><a name="p141695156461"></a>【输出】</p>
<p id="p216981584616"><a name="p216981584616"></a><a name="p216981584616"></a>1个tensor，与input数据相同，shape增加了一维（值为1）</p>
<p id="p8169515104616"><a name="p8169515104616"></a><a name="p8169515104616"></a>【量化工具支持】</p>
<p id="p816931515467"><a name="p816931515467"></a><a name="p816931515467"></a>是</p>
</td>
</tr>
<tr id="row141691615114616"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p1316911564617"><a name="p1316911564617"></a><a name="p1316911564617"></a>15</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p416981554618"><a name="p416981554618"></a><a name="p416981554618"></a>tf.greater</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p151691715104615"><a name="p151691715104615"></a><a name="p151691715104615"></a>Greater</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p81697151466"><a name="p81697151466"></a><a name="p81697151466"></a>【参数】</p>
<a name="ul1095313200516"></a><a name="ul1095313200516"></a><ul id="ul1095313200516"><li>x：输入，1个tensor</li><li>y：标量</li><li>name：此操作的名称（可选）</li></ul>
<p id="p151691515174617"><a name="p151691515174617"></a><a name="p151691515174617"></a>【约束】</p>
<p id="p1917012156468"><a name="p1917012156468"></a><a name="p1917012156468"></a>支持广播broadcast，对比x和y的shape，在同一纬度上，dim[x]只能相同或者一方为1或者一方缺失</p>
<p id="p20170515144612"><a name="p20170515144612"></a><a name="p20170515144612"></a>【输出】</p>
<p id="p191701115104617"><a name="p191701115104617"></a><a name="p191701115104617"></a>1个tensor，类型：bool</p>
<p id="p121701315194618"><a name="p121701315194618"></a><a name="p121701315194618"></a>【量化工具支持】</p>
<p id="p1317081584617"><a name="p1317081584617"></a><a name="p1317081584617"></a>无需支持</p>
</td>
</tr>
<tr id="row617061517463"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p1017018153467"><a name="p1017018153467"></a><a name="p1017018153467"></a>16</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p61701115184613"><a name="p61701115184613"></a><a name="p61701115184613"></a>tf.nn.relu</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p201705153466"><a name="p201705153466"></a><a name="p201705153466"></a>Relu</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p17170201519462"><a name="p17170201519462"></a><a name="p17170201519462"></a>【参数】</p>
<a name="ul4779182712517"></a><a name="ul4779182712517"></a><ul id="ul4779182712517"><li>features：非常量输入，tensor</li><li>name：此操作的名称（可选）</li></ul>
<p id="p717071584615"><a name="p717071584615"></a><a name="p717071584615"></a>【约束】</p>
<p id="p1017016157462"><a name="p1017016157462"></a><a name="p1017016157462"></a>无限制</p>
<p id="p1170181518468"><a name="p1170181518468"></a><a name="p1170181518468"></a>【输出】</p>
<p id="p1117018158462"><a name="p1117018158462"></a><a name="p1117018158462"></a>1个tensor，类型同features</p>
<p id="p717021574618"><a name="p717021574618"></a><a name="p717021574618"></a>【量化工具支持】</p>
<p id="p21700155467"><a name="p21700155467"></a><a name="p21700155467"></a>是</p>
</td>
</tr>
<tr id="row12170141554610"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p11706155466"><a name="p11706155466"></a><a name="p11706155466"></a>17</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p51704157464"><a name="p51704157464"></a><a name="p51704157464"></a>tf.nn.relu6</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p19170111534617"><a name="p19170111534617"></a><a name="p19170111534617"></a>Relu6</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p81717151468"><a name="p81717151468"></a><a name="p81717151468"></a>【参数】</p>
<a name="ul14134633185115"></a><a name="ul14134633185115"></a><ul id="ul14134633185115"><li>features：非常量输入，tensor</li><li>name：此操作的名称（可选）</li></ul>
<p id="p6171101512466"><a name="p6171101512466"></a><a name="p6171101512466"></a>【约束】</p>
<p id="p51711015124614"><a name="p51711015124614"></a><a name="p51711015124614"></a>无限制</p>
<p id="p617113150460"><a name="p617113150460"></a><a name="p617113150460"></a>【输出】</p>
<p id="p15171715174620"><a name="p15171715174620"></a><a name="p15171715174620"></a>1个tensor，类型同features</p>
<p id="p20171171514465"><a name="p20171171514465"></a><a name="p20171171514465"></a>【量化工具支持】</p>
<p id="p117151524610"><a name="p117151524610"></a><a name="p117151524610"></a>是</p>
</td>
</tr>
<tr id="row121711815124615"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p2171111519464"><a name="p2171111519464"></a><a name="p2171111519464"></a>18</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1817181584612"><a name="p1817181584612"></a><a name="p1817181584612"></a>tf.nn.leaky_relu</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p3171161514465"><a name="p3171161514465"></a><a name="p3171161514465"></a>/</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p61711115164615"><a name="p61711115164615"></a><a name="p61711115164615"></a>【参数】</p>
<a name="ul26472041165112"></a><a name="ul26472041165112"></a><ul id="ul26472041165112"><li>features：非常量输入，tensor，表示预激活的值</li><li>alpha：x&lt;0时激活函数的斜率</li><li>name：此操作的名称（可选）</li></ul>
<p id="p14171201554615"><a name="p14171201554615"></a><a name="p14171201554615"></a>【约束】</p>
<p id="p11718152469"><a name="p11718152469"></a><a name="p11718152469"></a>无限制</p>
<p id="p13171141513468"><a name="p13171141513468"></a><a name="p13171141513468"></a>【输出】</p>
<p id="p1817241518468"><a name="p1817241518468"></a><a name="p1817241518468"></a>激活值</p>
<p id="p2172141564618"><a name="p2172141564618"></a><a name="p2172141564618"></a>【量化工具支持】</p>
<p id="p2172181524614"><a name="p2172181524614"></a><a name="p2172181524614"></a>是</p>
</td>
</tr>
<tr id="row15172215144618"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p81722015174616"><a name="p81722015174616"></a><a name="p81722015174616"></a>19</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p7172111504619"><a name="p7172111504619"></a><a name="p7172111504619"></a>tf.exp</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p41721715124614"><a name="p41721715124614"></a><a name="p41721715124614"></a>exp</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p1617216151464"><a name="p1617216151464"></a><a name="p1617216151464"></a>【参数】</p>
<a name="ul14782848185111"></a><a name="ul14782848185111"></a><ul id="ul14782848185111"><li>x：1个输入tensor，类型float32，double</li><li>name：此操作的名称（可选）</li></ul>
<p id="p131729159467"><a name="p131729159467"></a><a name="p131729159467"></a>【约束】</p>
<p id="p1417211514463"><a name="p1417211514463"></a><a name="p1417211514463"></a>无限制</p>
<p id="p917291544614"><a name="p917291544614"></a><a name="p917291544614"></a>【输出】</p>
<p id="p11172151511466"><a name="p11172151511466"></a><a name="p11172151511466"></a>1个tensor，类型同x</p>
<p id="p2172715184612"><a name="p2172715184612"></a><a name="p2172715184612"></a>【量化工具支持】</p>
<p id="p11172191544611"><a name="p11172191544611"></a><a name="p11172191544611"></a>否</p>
</td>
</tr>
<tr id="row517261574619"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p1417281516465"><a name="p1417281516465"></a><a name="p1417281516465"></a>20</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1617241510466"><a name="p1617241510466"></a><a name="p1617241510466"></a>tf.nn.conv2d_transpose</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p8172191564616"><a name="p8172191564616"></a><a name="p8172191564616"></a>Conv2DBackpropInput</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p1017271511461"><a name="p1017271511461"></a><a name="p1017271511461"></a>【参数】</p>
<a name="ul557985713511"></a><a name="ul557985713511"></a><ul id="ul557985713511"><li>value：输入，4-D tensor，数据格式：NHWC（[batch，height，width，in_channels]）或NCHW（[batch，in_channel，height，width]）</li><li>filter：4-D tensor，常量，shape：[height，width，output_channels，in_channels]</li><li>output_shape：1-D tensor，表示输出的shape</li><li>strides：int型列表，非空，输入的每个维度的滑动窗口的步长</li><li>padding：类型：string，值为’VALID’或’SAME’，非空</li><li>data_format：类型：string，’NHWC’或’NCHW’，非空</li><li>name：输出名（可选）</li></ul>
<p id="p11731815114617"><a name="p11731815114617"></a><a name="p11731815114617"></a>【约束】</p>
<a name="ul1578011414526"></a><a name="ul1578011414526"></a><ul id="ul1578011414526"><li>group = 1</li><li>dilation = 1</li><li>filterH - padHHead - 1 &gt;= 0</li><li>filterW - padWHead - 1 &gt;= 0</li></ul>
<p id="p17173181534616"><a name="p17173181534616"></a><a name="p17173181534616"></a>还有一条约束涉及中间变量，公式如下：</p>
<a name="ol12584812165210"></a><a name="ol12584812165210"></a><ol id="ol12584812165210"><li>a = ALIGN（filter_num，16） * ALIGN（filter_c，16） * filter_h * filter_w * 2；</li><li>如果ALIGN（filter_c，16）%32 = 0，a = a/2</li><li>conv_input_width=（反卷积输入w - 1） * strideW + 1</li><li>b = （conv_input_width） * filter_h * ALIGN（filter_num，16） * 2 * 2</li><li>a + b &lt;= 1024*1024</li></ol>
<p id="p0173915194613"><a name="p0173915194613"></a><a name="p0173915194613"></a>【输出】</p>
<p id="p117351511469"><a name="p117351511469"></a><a name="p117351511469"></a>1个tensor，类型同value</p>
<p id="p4173111524615"><a name="p4173111524615"></a><a name="p4173111524615"></a>【量化工具支持】</p>
<p id="p1717381511465"><a name="p1717381511465"></a><a name="p1717381511465"></a>是</p>
</td>
</tr>
<tr id="row14173815164614"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p13173131512465"><a name="p13173131512465"></a><a name="p13173131512465"></a>21</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p81735153465"><a name="p81735153465"></a><a name="p81735153465"></a>tf.sigmoid</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p81731015154618"><a name="p81731015154618"></a><a name="p81731015154618"></a>Sigmoid</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p4173715134618"><a name="p4173715134618"></a><a name="p4173715134618"></a>【参数】</p>
<a name="ul16777112155218"></a><a name="ul16777112155218"></a><ul id="ul16777112155218"><li>x：1个tensor，输入</li><li>name：此操作的名称（可选）</li></ul>
<p id="p817321544612"><a name="p817321544612"></a><a name="p817321544612"></a>【约束】</p>
<p id="p3173515174614"><a name="p3173515174614"></a><a name="p3173515174614"></a>无限制</p>
<p id="p717361518464"><a name="p717361518464"></a><a name="p717361518464"></a>【输出】</p>
<p id="p121731715194614"><a name="p121731715194614"></a><a name="p121731715194614"></a>1个tensor，类型同value</p>
<p id="p15173111519468"><a name="p15173111519468"></a><a name="p15173111519468"></a>【量化工具支持】</p>
<p id="p617391511463"><a name="p617391511463"></a><a name="p617391511463"></a>是</p>
</td>
</tr>
<tr id="row18173161514467"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p1017401544619"><a name="p1017401544619"></a><a name="p1017401544619"></a>22</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p0174515174612"><a name="p0174515174612"></a><a name="p0174515174612"></a>tf.add</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p917414158462"><a name="p917414158462"></a><a name="p917414158462"></a>Add</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p3174215144616"><a name="p3174215144616"></a><a name="p3174215144616"></a>【参数】</p>
<a name="ul18452427185212"></a><a name="ul18452427185212"></a><ul id="ul18452427185212"><li>x：输入，1个tensor，类型：float32、int32</li><li>y：输入，1个tensor，类型同x；两个输入为常量时，1个输入为标量</li><li>name：此操作的名称（可选）</li></ul>
<p id="p41741715144615"><a name="p41741715144615"></a><a name="p41741715144615"></a>【约束】</p>
<p id="p19174615134619"><a name="p19174615134619"></a><a name="p19174615134619"></a>支持两组输入的维度不一致，进行广播操作（广播即维度补齐）</p>
<p id="p1817471554618"><a name="p1817471554618"></a><a name="p1817471554618"></a>目前支持以下几种广播场景：</p>
<a name="ul9174181544620"></a><a name="ul9174181544620"></a><ul id="ul9174181544620"><li>NHWC+NHWC，NHWC+scalar</li><li>NHWC +1 1 1 1</li><li>NHWC+W和HWC+W和HW+W（备注，W维度做广播）</li><li>NCHW + NH1C和HWC + H1C和HW + H1</li><li>HWC + 1 WC（备注，H维度做广播）</li></ul>
<div class="note" id="note1714111214610"><a name="note1714111214610"></a><a name="note1714111214610"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p7174191519468"><a name="p7174191519468"></a><a name="p7174191519468"></a>两个tensor的输入顺序可以互换。</p>
</div></div>
<p id="p817416157464"><a name="p817416157464"></a><a name="p817416157464"></a>【输出】</p>
<p id="p121741715194615"><a name="p121741715194615"></a><a name="p121741715194615"></a>1个tensor，类型同y</p>
<p id="p161746155461"><a name="p161746155461"></a><a name="p161746155461"></a>【量化工具支持】</p>
<p id="p18174191584617"><a name="p18174191584617"></a><a name="p18174191584617"></a>是</p>
</td>
</tr>
<tr id="row181741815194617"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p171742152467"><a name="p171742152467"></a><a name="p171742152467"></a>23</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p12174141515467"><a name="p12174141515467"></a><a name="p12174141515467"></a>tf.multiply</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p16174121516466"><a name="p16174121516466"></a><a name="p16174121516466"></a>Multiply</p>
<p id="p417491564615"><a name="p417491564615"></a><a name="p417491564615"></a>Type：Mul</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p217501518463"><a name="p217501518463"></a><a name="p217501518463"></a>【参数】</p>
<a name="ul832194019527"></a><a name="ul832194019527"></a><ul id="ul832194019527"><li>x：输入，1个tensor，类型：float32、int32</li><li>y：输入，1个tensor，类型同x；两个输入为常量时，维度必须一致，为标量或者1-D tensor</li><li>name：此操作的名称（可选）</li></ul>
<p id="p51754158461"><a name="p51754158461"></a><a name="p51754158461"></a>【约束】</p>
<p id="p6175215164612"><a name="p6175215164612"></a><a name="p6175215164612"></a>支持两组输入的维度不一致，进行广播操作（广播即维度补齐），</p>
<p id="p101759157466"><a name="p101759157466"></a><a name="p101759157466"></a>目前支持以下几种广播场景：</p>
<a name="ul101751715134620"></a><a name="ul101751715134620"></a><ul id="ul101751715134620"><li>NHWC+NHWC，NHWC+scalar</li><li>NHWC +1 1 1 1，</li><li>NHWC+W和HWC+W和HW+W（备注，W维度做广播）</li><li>NCHW + NH1C和HWC + H1C和HW + H1</li><li>HWC + 1 WC（备注，H维度做广播）</li></ul>
<div class="note" id="note113514126469"><a name="note113514126469"></a><a name="note113514126469"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p1917541511468"><a name="p1917541511468"></a><a name="p1917541511468"></a>两个tensor的输入顺序可以互换。</p>
</div></div>
<p id="p1017561554618"><a name="p1017561554618"></a><a name="p1017561554618"></a>【输出】</p>
<p id="p151754156466"><a name="p151754156466"></a><a name="p151754156466"></a>1个tensor</p>
<p id="p0175121520468"><a name="p0175121520468"></a><a name="p0175121520468"></a>【量化工具支持】</p>
<p id="p16175115184613"><a name="p16175115184613"></a><a name="p16175115184613"></a>是</p>
</td>
</tr>
<tr id="row13175161517464"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p41758157465"><a name="p41758157465"></a><a name="p41758157465"></a>24</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p141754153462"><a name="p141754153462"></a><a name="p141754153462"></a>tf.subtract</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p151754154464"><a name="p151754154464"></a><a name="p151754154464"></a>Subtract</p>
<p id="p11175715194614"><a name="p11175715194614"></a><a name="p11175715194614"></a>Type：Sub</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p1917514151466"><a name="p1917514151466"></a><a name="p1917514151466"></a>【参数】</p>
<a name="ul1415415515215"></a><a name="ul1415415515215"></a><ul id="ul1415415515215"><li>x：输入，1个tensor</li><li>y：输入，1个tensor，类型同x；两个输入，可支持常量或非常量</li><li>name：此操作的名称（可选）</li></ul>
<p id="p131761715124611"><a name="p131761715124611"></a><a name="p131761715124611"></a>【约束】</p>
<p id="p817651512467"><a name="p817651512467"></a><a name="p817651512467"></a>支持两组输入的维度不一致，进行广播操作（广播即维度补齐），</p>
<p id="p91766156463"><a name="p91766156463"></a><a name="p91766156463"></a>目前支持以下几种广播场景：</p>
<a name="ul1217591516465"></a><a name="ul1217591516465"></a><ul id="ul1217591516465"><li>NHWC+NHWC，NHWC+scalar</li><li>NHWC +1 1 1 1</li><li>NHWC+W和HWC+W 和HW+W（备注，W维度做广播）</li><li>NCHW + NH1C和HWC + H1C和HW + H1</li><li>HWC + 1 WC（备注，H维度做广播）</li></ul>
<div class="note" id="note1670191213465"><a name="note1670191213465"></a><a name="note1670191213465"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p1717671584610"><a name="p1717671584610"></a><a name="p1717671584610"></a>两个tensor的输入顺序可以互换。</p>
</div></div>
<p id="p1317651574611"><a name="p1317651574611"></a><a name="p1317651574611"></a>【输出】</p>
<p id="p31761915194616"><a name="p31761915194616"></a><a name="p31761915194616"></a>1个tensor</p>
<p id="p15176115174615"><a name="p15176115174615"></a><a name="p15176115174615"></a>【量化工具支持】</p>
<p id="p1017661524614"><a name="p1017661524614"></a><a name="p1017661524614"></a>是</p>
</td>
</tr>
<tr id="row11176015184617"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p121761415144620"><a name="p121761415144620"></a><a name="p121761415144620"></a>25</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p8176151594619"><a name="p8176151594619"></a><a name="p8176151594619"></a>tf.nn.bias_add</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p191765159460"><a name="p191765159460"></a><a name="p191765159460"></a>BiasAdd</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p171763159469"><a name="p171763159469"></a><a name="p171763159469"></a>【参数】</p>
<a name="ul2657162125311"></a><a name="ul2657162125311"></a><ul id="ul2657162125311"><li>value：输入，1个tensor，非常量</li><li>bias：1-D tensor，常量，尺寸与value的最后一维一致；除非value为量化类型，否则类型需同value</li><li>data_format：类型：string，‘NHWC’或‘NCHW’</li><li>name：此操作的名称（可选）</li></ul>
<p id="p7176151513462"><a name="p7176151513462"></a><a name="p7176151513462"></a>【约束】</p>
<a name="ul916798155314"></a><a name="ul916798155314"></a><ul id="ul916798155314"><li>C &lt; 10000</li><li>input和bias的数据排布要一致</li><li>当在c通道上加bias时，input和bias的C维度大小要一致</li></ul>
<p id="p4176115174616"><a name="p4176115174616"></a><a name="p4176115174616"></a>【输出】</p>
<p id="p1117621519468"><a name="p1117621519468"></a><a name="p1117621519468"></a>1个tensor，类型同value</p>
<p id="p1617615152462"><a name="p1617615152462"></a><a name="p1617615152462"></a>【量化工具支持】</p>
<p id="p14176191518461"><a name="p14176191518461"></a><a name="p14176191518461"></a>是</p>
</td>
</tr>
<tr id="row1317711517464"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p1517715156467"><a name="p1517715156467"></a><a name="p1517715156467"></a>26</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1517781594612"><a name="p1517781594612"></a><a name="p1517781594612"></a>tf.nn.lrn</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p161771158461"><a name="p161771158461"></a><a name="p161771158461"></a>LRN</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p117717151469"><a name="p117717151469"></a><a name="p117717151469"></a>【参数】</p>
<a name="ul18419186531"></a><a name="ul18419186531"></a><ul id="ul18419186531"><li>input：输入，4-D tensor，类型：float32</li><li>depth_radius：0-D int型，默认值为5，1-D标准化窗口的半宽</li><li>bias：可选参数，float型，默认为1；偏移（通常为正值，以避免除以0）</li><li>alpha：可选参数，float型，默认为1；比例因子，通常为正值</li><li>beta：可选参数，float型，默认为0.5；1个指数</li><li>name：此操作的名称（可选）</li></ul>
<p id="p417711534618"><a name="p417711534618"></a><a name="p417711534618"></a>【约束】</p>
<a name="ul4281202420538"></a><a name="ul4281202420538"></a><ul id="ul4281202420538"><li>depth_radius &gt;0，且必须为奇数</li><li>通道间：<p id="p6177815114616"><a name="p6177815114616"></a><a name="p6177815114616"></a>当depth_radius∈[1，15]时，alpha &gt;0.00001且beta&gt;0.01，否则alpha和beta为任意值；当C维度大于1776时，depth_radius &lt;1728</p>
</li></ul>
<p id="p1917771564618"><a name="p1917771564618"></a><a name="p1917771564618"></a>【输出】</p>
<p id="p9177415174618"><a name="p9177415174618"></a><a name="p9177415174618"></a>1个tensor，类型同input</p>
<p id="p171771415134612"><a name="p171771415134612"></a><a name="p171771415134612"></a>【量化工具支持】</p>
<p id="p18177815104619"><a name="p18177815104619"></a><a name="p18177815104619"></a>是</p>
</td>
</tr>
<tr id="row1317771510462"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p5177171515463"><a name="p5177171515463"></a><a name="p5177171515463"></a>27</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p417710159464"><a name="p417710159464"></a><a name="p417710159464"></a>tf.nn.elu</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p111771415144615"><a name="p111771415144615"></a><a name="p111771415144615"></a>Elu</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p7177715144616"><a name="p7177715144616"></a><a name="p7177715144616"></a>【参数】</p>
<a name="ul0747193925316"></a><a name="ul0747193925316"></a><ul id="ul0747193925316"><li>features：输入tensor，非常量</li><li>name：名称（可选）</li></ul>
<p id="p131772151465"><a name="p131772151465"></a><a name="p131772151465"></a>【约束】</p>
<p id="p717731512463"><a name="p717731512463"></a><a name="p717731512463"></a>无限制</p>
<p id="p1417731514613"><a name="p1417731514613"></a><a name="p1417731514613"></a>【输出】</p>
<p id="p17177141514611"><a name="p17177141514611"></a><a name="p17177141514611"></a>输出tensor，类型同features</p>
<p id="p8177121511469"><a name="p8177121511469"></a><a name="p8177121511469"></a>【量化工具支持】</p>
<p id="p017851554618"><a name="p017851554618"></a><a name="p017851554618"></a>否</p>
</td>
</tr>
<tr id="row4178171520465"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p0178171514610"><a name="p0178171514610"></a><a name="p0178171514610"></a>28</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p11781415194616"><a name="p11781415194616"></a><a name="p11781415194616"></a>tf.rsqrt</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p7178615204614"><a name="p7178615204614"></a><a name="p7178615204614"></a>Rsqrt</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p417851510464"><a name="p417851510464"></a><a name="p417851510464"></a>【参数】</p>
<a name="ul16489115112534"></a><a name="ul16489115112534"></a><ul id="ul16489115112534"><li>x：输入tensor</li><li>name：名称（可选）</li></ul>
<p id="p617811157468"><a name="p617811157468"></a><a name="p617811157468"></a>【约束】</p>
<p id="p1217881511468"><a name="p1217881511468"></a><a name="p1217881511468"></a>无限制</p>
<p id="p417812153463"><a name="p417812153463"></a><a name="p417812153463"></a>【输出】</p>
<p id="p171781152469"><a name="p171781152469"></a><a name="p171781152469"></a>输出tensor，类型同x</p>
<p id="p7178415154611"><a name="p7178415154611"></a><a name="p7178415154611"></a>【量化工具支持】</p>
<p id="p1717820152461"><a name="p1717820152461"></a><a name="p1717820152461"></a>是</p>
</td>
</tr>
<tr id="row19178715194611"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p1217891514616"><a name="p1217891514616"></a><a name="p1217891514616"></a>29</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p41784155464"><a name="p41784155464"></a><a name="p41784155464"></a>tf.log</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p91781315144617"><a name="p91781315144617"></a><a name="p91781315144617"></a>Log</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p517821594613"><a name="p517821594613"></a><a name="p517821594613"></a>【参数】</p>
<a name="ul5600105612538"></a><a name="ul5600105612538"></a><ul id="ul5600105612538"><li>x：输入tensor，类型：float32</li><li>name：名称（可选）</li></ul>
<p id="p7178131524611"><a name="p7178131524611"></a><a name="p7178131524611"></a>【约束】</p>
<p id="p317871524619"><a name="p317871524619"></a><a name="p317871524619"></a>无限制</p>
<p id="p11178131512466"><a name="p11178131512466"></a><a name="p11178131512466"></a>【输出】</p>
<p id="p2178121513465"><a name="p2178121513465"></a><a name="p2178121513465"></a>输出tensor，类型同x</p>
<p id="p18178515104620"><a name="p18178515104620"></a><a name="p18178515104620"></a>【量化工具支持】</p>
<p id="p171781915194612"><a name="p171781915194612"></a><a name="p171781915194612"></a>否</p>
</td>
</tr>
<tr id="row1517881554618"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p1717810155466"><a name="p1717810155466"></a><a name="p1717810155466"></a>30</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p19178161564616"><a name="p19178161564616"></a><a name="p19178161564616"></a>tf.tanh</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p15178141515463"><a name="p15178141515463"></a><a name="p15178141515463"></a>Tanh</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p1617941519469"><a name="p1617941519469"></a><a name="p1617941519469"></a>【参数】</p>
<a name="ul105253185413"></a><a name="ul105253185413"></a><ul id="ul105253185413"><li>x：输入tensor，非常量</li><li>name：名称（可选）</li></ul>
<p id="p317991534610"><a name="p317991534610"></a><a name="p317991534610"></a>【约束】</p>
<p id="p16179615104614"><a name="p16179615104614"></a><a name="p16179615104614"></a>无限制</p>
<p id="p0179161584619"><a name="p0179161584619"></a><a name="p0179161584619"></a>【输出】</p>
<p id="p61792015154620"><a name="p61792015154620"></a><a name="p61792015154620"></a>输出tensor，类型同x</p>
<p id="p317931534617"><a name="p317931534617"></a><a name="p317931534617"></a>【量化工具支持】</p>
<p id="p1917919159463"><a name="p1917919159463"></a><a name="p1917919159463"></a>是</p>
</td>
</tr>
<tr id="row1417991514618"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p6179815104612"><a name="p6179815104612"></a><a name="p6179815104612"></a>31</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p117951510464"><a name="p117951510464"></a><a name="p117951510464"></a>tf.slice</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p71791715124616"><a name="p71791715124616"></a><a name="p71791715124616"></a>Slice</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p41792153467"><a name="p41792153467"></a><a name="p41792153467"></a>【参数】</p>
<a name="ul205685685410"></a><a name="ul205685685410"></a><ul id="ul205685685410"><li>input_：输入tensor</li><li>begin：tensor，类型：int32或int64</li><li>size：tensor，类型：int32或int64</li><li>name：名称（可选）</li></ul>
<p id="p1817991519468"><a name="p1817991519468"></a><a name="p1817991519468"></a>【约束】</p>
<p id="p16179151517464"><a name="p16179151517464"></a><a name="p16179151517464"></a>输入tensor元素个数不超过INT32_MAX</p>
<p id="p5179141512465"><a name="p5179141512465"></a><a name="p5179141512465"></a>【输出】</p>
<p id="p18179191516466"><a name="p18179191516466"></a><a name="p18179191516466"></a>输出tensor，类型同input_</p>
<p id="p16179915144612"><a name="p16179915144612"></a><a name="p16179915144612"></a>【量化工具支持】</p>
<p id="p11179151513465"><a name="p11179151513465"></a><a name="p11179151513465"></a>是</p>
</td>
</tr>
<tr id="row19179131514612"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p1317916156467"><a name="p1317916156467"></a><a name="p1317916156467"></a>32</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p61791315184619"><a name="p61791315184619"></a><a name="p61791315184619"></a>tf.split</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p2017941564612"><a name="p2017941564612"></a><a name="p2017941564612"></a>Split</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p81791715204618"><a name="p81791715204618"></a><a name="p81791715204618"></a>【参数】</p>
<a name="ul688201315417"></a><a name="ul688201315417"></a><ul id="ul688201315417"><li>value：输入Tensor</li><li>num_or_size_splits：不支持这个参数</li><li>axis：标准，整型，指定输出维度</li><li>name：string；名称（可选）</li></ul>
<p id="p121801150464"><a name="p121801150464"></a><a name="p121801150464"></a>【约束】</p>
<p id="p181801815194616"><a name="p181801815194616"></a><a name="p181801815194616"></a>无限制</p>
<p id="p1018061574613"><a name="p1018061574613"></a><a name="p1018061574613"></a>【输出】</p>
<p id="p14180215184618"><a name="p14180215184618"></a><a name="p14180215184618"></a>List，包含split后的各Tensor</p>
<p id="p71801615124617"><a name="p71801615124617"></a><a name="p71801615124617"></a>【量化工具支持】</p>
<p id="p918001534616"><a name="p918001534616"></a><a name="p918001534616"></a>是</p>
</td>
</tr>
<tr id="row13180141544612"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p4180111512465"><a name="p4180111512465"></a><a name="p4180111512465"></a>33</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p5180111520460"><a name="p5180111520460"></a><a name="p5180111520460"></a>tf.nn.softplus</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p16180101516461"><a name="p16180101516461"></a><a name="p16180101516461"></a>Softplus</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p6180191514613"><a name="p6180191514613"></a><a name="p6180191514613"></a>【参数】</p>
<a name="ul7458131911544"></a><a name="ul7458131911544"></a><ul id="ul7458131911544"><li>features：输入Tensor；数据类型：`float32`</li><li>name：string；名称（可选）</li></ul>
<p id="p6180915134620"><a name="p6180915134620"></a><a name="p6180915134620"></a>【约束】</p>
<p id="p7180715134613"><a name="p7180715134613"></a><a name="p7180715134613"></a>无限制</p>
<p id="p1818018156465"><a name="p1818018156465"></a><a name="p1818018156465"></a>【输出】</p>
<p id="p181802015194616"><a name="p181802015194616"></a><a name="p181802015194616"></a>输出Tensor，数据类型与features相同</p>
<p id="p818016156466"><a name="p818016156466"></a><a name="p818016156466"></a>【量化工具支持】</p>
<p id="p151801315164611"><a name="p151801315164611"></a><a name="p151801315164611"></a>否</p>
</td>
</tr>
<tr id="row121804154464"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p0180115194612"><a name="p0180115194612"></a><a name="p0180115194612"></a>34</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p7180715164619"><a name="p7180715164619"></a><a name="p7180715164619"></a>tf.nn.softsign</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p16180615104610"><a name="p16180615104610"></a><a name="p16180615104610"></a>Softsign</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p218091584613"><a name="p218091584613"></a><a name="p218091584613"></a>【参数】</p>
<a name="ul105271528165412"></a><a name="ul105271528165412"></a><ul id="ul105271528165412"><li>features：输入Tensor；数据类型：`float32`</li><li>name：string；名称（可选）</li></ul>
<p id="p51801915174612"><a name="p51801915174612"></a><a name="p51801915174612"></a>【约束】</p>
<p id="p171801015124617"><a name="p171801015124617"></a><a name="p171801015124617"></a>无限制</p>
<p id="p71801715204616"><a name="p71801715204616"></a><a name="p71801715204616"></a>【输出】</p>
<p id="p13180615154615"><a name="p13180615154615"></a><a name="p13180615154615"></a>输出Tensor，数据类型与features相同</p>
<p id="p818020156461"><a name="p818020156461"></a><a name="p818020156461"></a>【量化工具支持】</p>
<p id="p13180415104618"><a name="p13180415104618"></a><a name="p13180415104618"></a>否</p>
</td>
</tr>
<tr id="row718091584617"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p9181111511464"><a name="p9181111511464"></a><a name="p9181111511464"></a>35</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1518151514464"><a name="p1518151514464"></a><a name="p1518151514464"></a>tf.pad</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p1518110155460"><a name="p1518110155460"></a><a name="p1518110155460"></a>Pad/MirrorPad/ PadV2</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p1118151574614"><a name="p1118151574614"></a><a name="p1118151574614"></a>【参数】</p>
<a name="ul113281335105414"></a><a name="ul113281335105414"></a><ul id="ul113281335105414"><li>tensor：4-D Tensor；数据类型：`float32`，`int32`</li><li>paddings：Tensor，常量，数据类型：`int32`</li><li>mode：string，值为"CONSTANT"，或"REFLECT"，或"SYMMETRIC"</li><li>name：string；名称（可选）</li><li>constant_values：Pad默认填充的值，标量，数据类型与tensor相同</li></ul>
<p id="p3181131594611"><a name="p3181131594611"></a><a name="p3181131594611"></a>【约束】</p>
<p id="p16181161554616"><a name="p16181161554616"></a><a name="p16181161554616"></a>CONSTANT模式时，0=&lt;PAD&lt;=128，0&lt;W&lt;=3000</p>
<p id="p15181151584617"><a name="p15181151584617"></a><a name="p15181151584617"></a>【输出】</p>
<p id="p10181015184615"><a name="p10181015184615"></a><a name="p10181015184615"></a>输出Tensor，数据类型与tensor相同</p>
<p id="p1418110155467"><a name="p1418110155467"></a><a name="p1418110155467"></a>【量化工具支持】</p>
<p id="p11181215154613"><a name="p11181215154613"></a><a name="p11181215154613"></a>是</p>
</td>
</tr>
<tr id="row618141511465"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p0181141518463"><a name="p0181141518463"></a><a name="p0181141518463"></a>36</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p718112158468"><a name="p718112158468"></a><a name="p718112158468"></a>tf.fake_quant_with_min_max_vars</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p21817152462"><a name="p21817152462"></a><a name="p21817152462"></a>FakeQuantWithMinMaxVars</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p81818154465"><a name="p81818154465"></a><a name="p81818154465"></a>【参数】</p>
<a name="ul17625944125411"></a><a name="ul17625944125411"></a><ul id="ul17625944125411"><li>inputs ：输入Tensor；数据类型：`float32`</li><li>min：Tensor，数据类型：`float32`</li><li>max：Tensor，数据类型：`float32`</li><li>num_bits：标量，整型，默认值`8`</li><li>narrow_range：bool（可选），默认值`False`</li><li>name：string；名称（可选）</li></ul>
<p id="p3181181544610"><a name="p3181181544610"></a><a name="p3181181544610"></a>【约束】</p>
<p id="p1818151544612"><a name="p1818151544612"></a><a name="p1818151544612"></a>-65504&lt;=min&lt;=65504，-65504&lt;=max&lt;=65504</p>
<p id="p91815152462"><a name="p91815152462"></a><a name="p91815152462"></a>【输出】</p>
<p id="p181811715184613"><a name="p181811715184613"></a><a name="p181811715184613"></a>输出Tensor，数据类型：`float32`</p>
<p id="p1618211519468"><a name="p1618211519468"></a><a name="p1618211519468"></a>【量化工具支持】</p>
<p id="p1182515134612"><a name="p1182515134612"></a><a name="p1182515134612"></a>否</p>
</td>
</tr>
<tr id="row3182131512469"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p141821015134619"><a name="p141821015134619"></a><a name="p141821015134619"></a>37</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p618214152460"><a name="p618214152460"></a><a name="p618214152460"></a>tf.reduce_max</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p151824154464"><a name="p151824154464"></a><a name="p151824154464"></a>Max</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p21821215194618"><a name="p21821215194618"></a><a name="p21821215194618"></a>【参数】</p>
<a name="ul19578111355518"></a><a name="ul19578111355518"></a><ul id="ul19578111355518"><li>input_tensor：输入tensor；数据类型：`float32`，`int64`，`int32`，`uint8`，`uint16`，`int16`，`int8`</li><li>axis：1-D list或标量，数据类型整型</li><li>keepdims：bool，是否保留维度为1</li><li>name：string；名称（可选）</li><li>reduction_indices：axis旧的别名（不推荐）</li><li>keep_dims：keepdims别名（不推荐）</li></ul>
<p id="p24624716550"><a name="p24624716550"></a><a name="p24624716550"></a>【约束】</p>
<a name="ul197491154155415"></a><a name="ul197491154155415"></a><ul id="ul197491154155415"><li>当输入的tensor维数等于4时：输入axis={3，{1，2，3}}，keepDims=true，H*W*16*2 &lt;= 16*1024</li><li>当输入的tensor维数等于2时，输入axis={1，{1}}，keepDims=true，H*W*CEIL（C，16）*16*2 &lt;= 16*1024</li></ul>
<p id="p111821015194611"><a name="p111821015194611"></a><a name="p111821015194611"></a>【输出】</p>
<p id="p1018212155462"><a name="p1018212155462"></a><a name="p1018212155462"></a>输出reduce后的Tensor，数据类型同input_tensor</p>
<p id="p91826151464"><a name="p91826151464"></a><a name="p91826151464"></a>【量化工具支持】</p>
<p id="p4182415154610"><a name="p4182415154610"></a><a name="p4182415154610"></a>否</p>
</td>
</tr>
<tr id="row1118291513462"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p618221574620"><a name="p618221574620"></a><a name="p618221574620"></a>38</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1018214154465"><a name="p1018214154465"></a><a name="p1018214154465"></a>tf.strided_slice</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p0182101524615"><a name="p0182101524615"></a><a name="p0182101524615"></a>StridedSlice</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p18182191513468"><a name="p18182191513468"></a><a name="p18182191513468"></a>【参数】</p>
<a name="ul194781227195512"></a><a name="ul194781227195512"></a><ul id="ul194781227195512"><li>input_：1个Tensor</li><li>begin：1-D Tensor，数据类型：`int32`</li><li>end：1-D Tensor，数据类型：`int32`</li><li>strides：1-D Tensor，数据类型：`int32`</li><li>begin_mask：标量，数据类型：`int32`</li><li>end_mask：标量，数据类型：`int32`</li><li>ellipsis_mask：标量，数据类型：`int32`</li><li>new_axis_mask：：标量，数据类型：`int32`</li><li>shrink_axis_mask：标量，数据类型：`int32`</li><li>var：与input_或None对应的变量</li><li>name：string；名称（可选）</li></ul>
<p id="p4184141512468"><a name="p4184141512468"></a><a name="p4184141512468"></a>【约束】</p>
<p id="p121841615194615"><a name="p121841615194615"></a><a name="p121841615194615"></a>strides不允许为0</p>
<p id="p161844154464"><a name="p161844154464"></a><a name="p161844154464"></a>【输出】</p>
<p id="p818421514611"><a name="p818421514611"></a><a name="p818421514611"></a>输出Tensor，数据类型同input_</p>
<p id="p6184141519463"><a name="p6184141519463"></a><a name="p6184141519463"></a>【量化工具支持】</p>
<p id="p7184315174611"><a name="p7184315174611"></a><a name="p7184315174611"></a>否</p>
</td>
</tr>
<tr id="row1618461564620"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p1618431544612"><a name="p1618431544612"></a><a name="p1618431544612"></a>39</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p41841515174615"><a name="p41841515174615"></a><a name="p41841515174615"></a>tf.reverse</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p12184121564610"><a name="p12184121564610"></a><a name="p12184121564610"></a>Reverse</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p101847159464"><a name="p101847159464"></a><a name="p101847159464"></a>【参数】</p>
<a name="ul047718357551"></a><a name="ul047718357551"></a><ul id="ul047718357551"><li>tensor：1个包含Tensor的列表，</li><li>axis：Tensor reverse轴向，数据类型：`int32`，`int64`</li><li>name：string；名称（可选）</li></ul>
<p id="p2184121514466"><a name="p2184121514466"></a><a name="p2184121514466"></a>【约束】</p>
<p id="p818411514469"><a name="p818411514469"></a><a name="p818411514469"></a>无限制</p>
<p id="p141841515184617"><a name="p141841515184617"></a><a name="p141841515184617"></a>【输出】</p>
<p id="p16184111520468"><a name="p16184111520468"></a><a name="p16184111520468"></a>1个Tensor，数据类型同tensor</p>
<p id="p101841158468"><a name="p101841158468"></a><a name="p101841158468"></a>【量化工具支持】</p>
<p id="p1018441534612"><a name="p1018441534612"></a><a name="p1018441534612"></a>否</p>
</td>
</tr>
<tr id="row101841915184612"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p161855157462"><a name="p161855157462"></a><a name="p161855157462"></a>40</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p19185121544617"><a name="p19185121544617"></a><a name="p19185121544617"></a>tf.realdiv</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p1418510157468"><a name="p1418510157468"></a><a name="p1418510157468"></a>RealDiv</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p318517150468"><a name="p318517150468"></a><a name="p318517150468"></a>【参数】</p>
<a name="ul14372114125514"></a><a name="ul14372114125514"></a><ul id="ul14372114125514"><li>x：输入Tensor；数据类型：float32`</li><li>y：输入Tensor；数据类型：float32`</li><li>name：string；名称（可选）</li></ul>
<p id="p15185141574617"><a name="p15185141574617"></a><a name="p15185141574617"></a>【约束】</p>
<p id="p718561544618"><a name="p718561544618"></a><a name="p718561544618"></a>无限制</p>
<p id="p1318571512461"><a name="p1318571512461"></a><a name="p1318571512461"></a>【输出】</p>
<p id="p19185615134617"><a name="p19185615134617"></a><a name="p19185615134617"></a>输出Tensor，数据类型同x</p>
<p id="p1018541513464"><a name="p1018541513464"></a><a name="p1018541513464"></a>【量化工具支持】</p>
<p id="p918516154468"><a name="p918516154468"></a><a name="p918516154468"></a>是</p>
</td>
</tr>
<tr id="row1618521517462"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p18185131519460"><a name="p18185131519460"></a><a name="p18185131519460"></a>41</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p01861015194616"><a name="p01861015194616"></a><a name="p01861015194616"></a>tf.stack</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p191861315134611"><a name="p191861315134611"></a><a name="p191861315134611"></a>Stack</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p12186131584614"><a name="p12186131584614"></a><a name="p12186131584614"></a>【参数】</p>
<a name="ul17140448155516"></a><a name="ul17140448155516"></a><ul id="ul17140448155516"><li>values：包含tensor对象（形状与类型相同，类型：float32，int32）的列表</li><li>axis：整数，沿axis维度堆叠，默认是第一维，必须设置</li><li>name：名称（可选）</li></ul>
<p id="p61863153466"><a name="p61863153466"></a><a name="p61863153466"></a>【约束】</p>
<p id="p151866153467"><a name="p151866153467"></a><a name="p151866153467"></a>无限制</p>
<p id="p9186131574618"><a name="p9186131574618"></a><a name="p9186131574618"></a>【输出】</p>
<p id="p9186141511462"><a name="p9186141511462"></a><a name="p9186141511462"></a>堆叠后的tensor，类型同values</p>
<p id="p18186131512467"><a name="p18186131512467"></a><a name="p18186131512467"></a>属性T、N和axis必须存在</p>
<p id="p1618681519461"><a name="p1618681519461"></a><a name="p1618681519461"></a>【量化工具支持】</p>
<p id="p818641524614"><a name="p818641524614"></a><a name="p818641524614"></a>否</p>
</td>
</tr>
<tr id="row9186101524611"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p8186415174614"><a name="p8186415174614"></a><a name="p8186415174614"></a>42</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p14186101554616"><a name="p14186101554616"></a><a name="p14186101554616"></a>tf.unstack</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p10186141511461"><a name="p10186141511461"></a><a name="p10186141511461"></a>Unpack</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p618611514611"><a name="p618611514611"></a><a name="p618611514611"></a>【参数】</p>
<a name="ul118591945563"></a><a name="ul118591945563"></a><ul id="ul118591945563"><li>value：输入tensor，秩&gt;0，类型：float32、int32</li><li>num：整数，表示axis维度的长度，默认为None</li><li>axis：整数，沿axis拆分，默认是第一维</li><li>name：名称（可选）</li></ul>
<p id="p1518791516469"><a name="p1518791516469"></a><a name="p1518791516469"></a>【约束】</p>
<p id="p13187111514613"><a name="p13187111514613"></a><a name="p13187111514613"></a>无限制</p>
<p id="p17187415134614"><a name="p17187415134614"></a><a name="p17187415134614"></a>【输出】</p>
<p id="p16187101524616"><a name="p16187101524616"></a><a name="p16187101524616"></a>从value中拆分出的包含tensor对象的列表</p>
<p id="p1318751514464"><a name="p1318751514464"></a><a name="p1318751514464"></a>【量化工具支持】</p>
<p id="p1118771544616"><a name="p1118771544616"></a><a name="p1118771544616"></a>否</p>
</td>
</tr>
<tr id="row1818714153468"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p18187171544612"><a name="p18187171544612"></a><a name="p18187171544612"></a>43</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p018701554611"><a name="p018701554611"></a><a name="p018701554611"></a>tf.transpose</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p31878153463"><a name="p31878153463"></a><a name="p31878153463"></a>Transpose</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p16187191594617"><a name="p16187191594617"></a><a name="p16187191594617"></a>【参数】</p>
<a name="ul132451427115611"></a><a name="ul132451427115611"></a><ul id="ul132451427115611"><li>a：输入tensor</li><li>perm：a的维数的排列</li><li>name：名称（可选）</li><li>conjugate：可选，类型：bool，默认为False；设置为True时，等同于tf.conj（tf.transpose（input））</li></ul>
<p id="p14187121514460"><a name="p14187121514460"></a><a name="p14187121514460"></a>【约束】</p>
<p id="p1718751514611"><a name="p1718751514611"></a><a name="p1718751514611"></a>无限制</p>
<p id="p1818721511465"><a name="p1818721511465"></a><a name="p1818721511465"></a>【输出】</p>
<p id="p15187215114614"><a name="p15187215114614"></a><a name="p15187215114614"></a>被转置后的tensor</p>
<p id="p4187101564620"><a name="p4187101564620"></a><a name="p4187101564620"></a>【量化工具支持】</p>
<p id="p191874159461"><a name="p191874159461"></a><a name="p191874159461"></a>是</p>
</td>
</tr>
<tr id="row13187171584611"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p418751517465"><a name="p418751517465"></a><a name="p418751517465"></a>44</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1818711150463"><a name="p1818711150463"></a><a name="p1818711150463"></a>tf.space_to_batch_nd</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p5187131574618"><a name="p5187131574618"></a><a name="p5187131574618"></a>SpaceToBatchND</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p618716154461"><a name="p618716154461"></a><a name="p618716154461"></a>【参数】</p>
<a name="ul238313885616"></a><a name="ul238313885616"></a><ul id="ul238313885616"><li>input：1个Tensor，是N维的并且具有形状input_shape = [batch] + spatial_shape + remaining_shape，其中spatial_shape有M维度；支持数据类型为：uint8，int8，int16，uint16，int32，int64，float32</li><li>block_shape：1个Tensor，必须是以下类型之一：int32，int64；1-D，shape为[M]，所有值必须&gt;=1</li><li>paddings：1个Tensor，必须是以下类型之一：int32，int64；二维，shape为[M，2]，所有值必须&gt;=0</li></ul>
<p id="p1218811515464"><a name="p1218811515464"></a><a name="p1218811515464"></a>【约束】</p>
<p id="p141886157465"><a name="p141886157465"></a><a name="p141886157465"></a>当tensor维数为4时：</p>
<p id="p818891516460"><a name="p818891516460"></a><a name="p818891516460"></a>blockShape的长度必须等于2，paddings的长度必须等于4</p>
<a name="ul3609151105616"></a><a name="ul3609151105616"></a><ul id="ul3609151105616"><li>blockShape元素的大小必须要大于等于1，paddings元素值的大小必须大于等于0</li><li>padding后的h维度要能够被blockShape[0]整除，padding后的w维度要能够被blockShape[1]整除</li></ul>
<p id="p9188201512464"><a name="p9188201512464"></a><a name="p9188201512464"></a>【输出】</p>
<p id="p131881915174614"><a name="p131881915174614"></a><a name="p131881915174614"></a>1个Tensor，与input具有相同的类型</p>
<p id="p10188715184611"><a name="p10188715184611"></a><a name="p10188715184611"></a>【量化工具支持】</p>
<p id="p131881615154617"><a name="p131881615154617"></a><a name="p131881615154617"></a>否</p>
</td>
</tr>
<tr id="row5188115134619"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p1118811155465"><a name="p1118811155465"></a><a name="p1118811155465"></a>45</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1818813151467"><a name="p1818813151467"></a><a name="p1818813151467"></a>tf.batch_to_space_nd</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p17188191574617"><a name="p17188191574617"></a><a name="p17188191574617"></a>BatchToSpaceND</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p151881515154619"><a name="p151881515154619"></a><a name="p151881515154619"></a>【参数】</p>
<a name="ul14107012572"></a><a name="ul14107012572"></a><ul id="ul14107012572"><li>input：1个Tensor，是N维的并且具有形状input_shape = [batch] + spatial_shape + remaining_shape，其中spatial_shape有M维度；支持数据类型为：uint8，int8，int16，uint16，int32，int64，float32</li><li>block_shape：1个Tensor；必须是以下类型之一：int32，int64；1-D，shape为[M]，所有值必须&gt;=1</li><li>crops：1个Tensor；必须是以下类型之一：int32，int64；二维，shape为[M，2]，所有值必须&gt;=0</li></ul>
<p id="p20188515194614"><a name="p20188515194614"></a><a name="p20188515194614"></a>【约束】</p>
<a name="ul217911103574"></a><a name="ul217911103574"></a><ul id="ul217911103574"><li>blockShape和crops的元素值数据类型必须是int32，当tensor维数为4时：blockShape的长度必须等于2，crops的长度必须等于4</li><li>blockShape元素的大小必须要大于等于1，crops元素值的大小必须大于等于0，crops数组的大小必须满足crop_start[i] + crop_end[i] &lt; block_shape[i] * input_shape[i+1]</li></ul>
<p id="p418816155462"><a name="p418816155462"></a><a name="p418816155462"></a>【输出】</p>
<p id="p218818152462"><a name="p218818152462"></a><a name="p218818152462"></a>1个Tensor，与images具有相同的类型</p>
<p id="p318811515467"><a name="p318811515467"></a><a name="p318811515467"></a>【量化工具支持】</p>
<p id="p15188515144616"><a name="p15188515144616"></a><a name="p15188515144616"></a>否</p>
</td>
</tr>
<tr id="row1618871510467"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p61881115194618"><a name="p61881115194618"></a><a name="p61881115194618"></a>46</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1188171517464"><a name="p1188171517464"></a><a name="p1188171517464"></a>tf.extract_image_patches</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p1218819156460"><a name="p1218819156460"></a><a name="p1218819156460"></a>ExtractImagePatches</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p41882153462"><a name="p41882153462"></a><a name="p41882153462"></a>【参数】</p>
<a name="ul744921115713"></a><a name="ul744921115713"></a><ul id="ul744921115713"><li>images：1个Tensor，支持数据类型：float32，int32，int64，uint8，int8，uint16，int16；4-D Tensor shape：[batch，in_rows，in_cols，depth]</li><li>ksizes：1个整形list，长度&gt;=4</li><li>strides：1个整形list，必须是：[1，stride_rows，stride_cols，1]</li><li>rate：1个整形list，必须是：[1，rate_rows，rate_cols，1]</li><li>padding：string，取值：“VALID”或者“SAME”，“VALID”表示所取的patch区域必须完全包含在原始图中"SAME"表示取超出原始图像的部分，以0填充该部分</li><li>name：名称（可选）</li></ul>
<p id="p18189315194618"><a name="p18189315194618"></a><a name="p18189315194618"></a>【约束】</p>
<p id="p718951514610"><a name="p718951514610"></a><a name="p718951514610"></a>无约束</p>
<p id="p1818971513465"><a name="p1818971513465"></a><a name="p1818971513465"></a>【输出】</p>
<p id="p1518911516467"><a name="p1518911516467"></a><a name="p1518911516467"></a>1个Tensor，与images具有相同的类型</p>
<p id="p11189215104611"><a name="p11189215104611"></a><a name="p11189215104611"></a>【量化工具支持】</p>
<p id="p141891015184611"><a name="p141891015184611"></a><a name="p141891015184611"></a>否</p>
</td>
</tr>
<tr id="row51891215154610"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p16189181511467"><a name="p16189181511467"></a><a name="p16189181511467"></a>47</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p171891715204615"><a name="p171891715204615"></a><a name="p171891715204615"></a>tf.floormod</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p171899151461"><a name="p171899151461"></a><a name="p171899151461"></a>FloorMod</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p131894157467"><a name="p131894157467"></a><a name="p131894157467"></a>【参数】</p>
<a name="ul966153213570"></a><a name="ul966153213570"></a><ul id="ul966153213570"><li>x：1个Tensor，支持数据类型：float32，int32</li><li>y：1个Tensor，与x具有相同类型</li><li>name：名称（可选）</li></ul>
<p id="p118991524618"><a name="p118991524618"></a><a name="p118991524618"></a>【约束】</p>
<p id="p1618961574610"><a name="p1618961574610"></a><a name="p1618961574610"></a>由于支持广播broadcast，对比x和y的shape，在同一纬度上，dim[x]只能相同或者一方为1或者一方缺失</p>
<p id="p19189515104619"><a name="p19189515104619"></a><a name="p19189515104619"></a>【输出】</p>
<p id="p7189215174617"><a name="p7189215174617"></a><a name="p7189215174617"></a>1个Tensor，与x具有相同的类型</p>
<p id="p10189191584618"><a name="p10189191584618"></a><a name="p10189191584618"></a>【量化工具支持】</p>
<p id="p16189121512461"><a name="p16189121512461"></a><a name="p16189121512461"></a>否</p>
</td>
</tr>
<tr id="row15189181512465"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p6189111584618"><a name="p6189111584618"></a><a name="p6189111584618"></a>48</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p618971518467"><a name="p618971518467"></a><a name="p618971518467"></a>tf.nn.softmax</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p141891115204617"><a name="p141891115204617"></a><a name="p141891115204617"></a>Softmax</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p6189115124615"><a name="p6189115124615"></a><a name="p6189115124615"></a>【参数】</p>
<a name="ul1861014397570"></a><a name="ul1861014397570"></a><ul id="ul1861014397570"><li>logits：1个非空的Tensor，支持数据类型：float32</li><li>axis：在其上执行维度softmax。默认值为-1，表示最后1个维度，不超过logits维度</li><li>name：名称（可选）</li><li>dim：axis的已弃用的别名</li></ul>
<p id="p9190131574611"><a name="p9190131574611"></a><a name="p9190131574611"></a>【约束】</p>
<a name="ul61311248135713"></a><a name="ul61311248135713"></a><ul id="ul61311248135713"><li>输入4维时可以针对每一维做softmax：<p id="p1695161105812"><a name="p1695161105812"></a><a name="p1695161105812"></a>根据分类的轴不同，计算边界分别为：</p>
<p id="p1337720118586"><a name="p1337720118586"></a><a name="p1337720118586"></a>axis=1时，c&lt;=（（256*1024/4）-8*1024-256）/2</p>
<p id="p737741145815"><a name="p737741145815"></a><a name="p737741145815"></a>axis=0时，n&lt;=（56*1024-256）/2</p>
<p id="p637771115815"><a name="p637771115815"></a><a name="p637771115815"></a>axis=2时，W=1，0&lt;h&lt;（1024*1024/32）</p>
<p id="p037719116587"><a name="p037719116587"></a><a name="p037719116587"></a>axis=3时，0&lt;W&lt;（1024*1024/32）</p>
</li><li>输入维度不足4维时，仅支持对最后一维做softmax计算，并且最后一维不超过46080</li></ul>
<p id="p1119010155467"><a name="p1119010155467"></a><a name="p1119010155467"></a>【输出】</p>
<p id="p17190161524614"><a name="p17190161524614"></a><a name="p17190161524614"></a>1个Tensor，与logits具有相同的类型和shape</p>
<p id="p1119010158461"><a name="p1119010158461"></a><a name="p1119010158461"></a>【量化工具支持】</p>
<p id="p1519015159462"><a name="p1519015159462"></a><a name="p1519015159462"></a>是</p>
</td>
</tr>
<tr id="row8190141504620"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p619091514469"><a name="p619091514469"></a><a name="p619091514469"></a>49</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p10190115174611"><a name="p10190115174611"></a><a name="p10190115174611"></a>tf.math.pow</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p1319015150464"><a name="p1319015150464"></a><a name="p1319015150464"></a>Power</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p101903153469"><a name="p101903153469"></a><a name="p101903153469"></a>【参数】</p>
<a name="ul930692119586"></a><a name="ul930692119586"></a><ul id="ul930692119586"><li>x：1个Tensor，支持数据类型：float32</li><li>y：1个Tensor，支持数据类型：float32</li><li>name：名称（可选）</li></ul>
<p id="p7190141584615"><a name="p7190141584615"></a><a name="p7190141584615"></a>【约束】</p>
<p id="p719011514613"><a name="p719011514613"></a><a name="p719011514613"></a>power!=1</p>
<p id="p719011513463"><a name="p719011513463"></a><a name="p719011513463"></a>scale*x+shift&gt;0</p>
<p id="p121909159469"><a name="p121909159469"></a><a name="p121909159469"></a>【输出】</p>
<p id="p1190151519469"><a name="p1190151519469"></a><a name="p1190151519469"></a>1个Tensor</p>
<p id="p319015154462"><a name="p319015154462"></a><a name="p319015154462"></a>【量化工具支持】</p>
<p id="p1319001510463"><a name="p1319001510463"></a><a name="p1319001510463"></a>是</p>
</td>
</tr>
<tr id="row1519031564615"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p2190915154616"><a name="p2190915154616"></a><a name="p2190915154616"></a>50</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1919041534618"><a name="p1919041534618"></a><a name="p1919041534618"></a>tf.nn.leaky_relu</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p119101515469"><a name="p119101515469"></a><a name="p119101515469"></a>LeakyRelu</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p171911515174620"><a name="p171911515174620"></a><a name="p171911515174620"></a>【参数】</p>
<a name="ul8167427175814"></a><a name="ul8167427175814"></a><ul id="ul8167427175814"><li>features：1个Tensor，支持数据类型：float32</li><li>alpha：x &lt;0时激活函数的斜率</li><li>name：名称（可选）</li></ul>
<p id="p01917158467"><a name="p01917158467"></a><a name="p01917158467"></a>【约束】</p>
<p id="p3191181517463"><a name="p3191181517463"></a><a name="p3191181517463"></a>无限制</p>
<p id="p19191615154613"><a name="p19191615154613"></a><a name="p19191615154613"></a>【输出】</p>
<p id="p9191915174615"><a name="p9191915174615"></a><a name="p9191915174615"></a>激活值</p>
<p id="p14191615114612"><a name="p14191615114612"></a><a name="p14191615114612"></a>【量化工具支持】</p>
<p id="p4191171574619"><a name="p4191171574619"></a><a name="p4191171574619"></a>是</p>
</td>
</tr>
<tr id="row7191615154618"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p1819151584613"><a name="p1819151584613"></a><a name="p1819151584613"></a>51</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p191911515194613"><a name="p191911515194613"></a><a name="p191911515194613"></a>tf.placeholder</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p11191191564619"><a name="p11191191564619"></a><a name="p11191191564619"></a>-</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p141911415114612"><a name="p141911415114612"></a><a name="p141911415114612"></a>【参数】</p>
<a name="ul16195032195811"></a><a name="ul16195032195811"></a><ul id="ul16195032195811"><li>dype：数据类型（必须）</li><li>shape：Tensor的维度和大小（必须）</li></ul>
<p id="p1119181514610"><a name="p1119181514610"></a><a name="p1119181514610"></a>【约束】</p>
<p id="p1619191564613"><a name="p1619191564613"></a><a name="p1619191564613"></a>无限制</p>
<p id="p11191151534612"><a name="p11191151534612"></a><a name="p11191151534612"></a>【输出】</p>
<p id="p13191201554611"><a name="p13191201554611"></a><a name="p13191201554611"></a>1个Tensor</p>
<p id="p719121574618"><a name="p719121574618"></a><a name="p719121574618"></a>【量化工具支持】</p>
<p id="p5191171564617"><a name="p5191171564617"></a><a name="p5191171564617"></a>否</p>
</td>
</tr>
<tr id="row1619171510461"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p1719115154464"><a name="p1719115154464"></a><a name="p1719115154464"></a>52</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p719111151468"><a name="p719111151468"></a><a name="p719111151468"></a>tf.shape</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p19191815144613"><a name="p19191815144613"></a><a name="p19191815144613"></a>Shape</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p171916153468"><a name="p171916153468"></a><a name="p171916153468"></a>【参数】</p>
<a name="ul139551247145817"></a><a name="ul139551247145817"></a><ul id="ul139551247145817"><li>input：1个Tensor或`SparseTensor`</li><li>name：string；名称（可选）</li><li>out_type输出Tensor数据类型，`int32`或`int64`（可选，默认为`int32`）</li></ul>
<p id="p44973434586"><a name="p44973434586"></a><a name="p44973434586"></a>【约束】</p>
<p id="p204976435582"><a name="p204976435582"></a><a name="p204976435582"></a>无限制</p>
<p id="p154974435588"><a name="p154974435588"></a><a name="p154974435588"></a>【输出】</p>
<p id="p11497134395814"><a name="p11497134395814"></a><a name="p11497134395814"></a>1个Tensor，输出数据类型为out_type</p>
<p id="p84972043175810"><a name="p84972043175810"></a><a name="p84972043175810"></a>【量化工具支持】</p>
<p id="p8497134335813"><a name="p8497134335813"></a><a name="p8497134335813"></a>无需支持</p>
</td>
</tr>
<tr id="row141921215114620"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p819291513465"><a name="p819291513465"></a><a name="p819291513465"></a>53</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p71921015154614"><a name="p71921015154614"></a><a name="p71921015154614"></a>tf.math.argmax</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p71925152467"><a name="p71925152467"></a><a name="p71925152467"></a>ArgMax</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p1019281514611"><a name="p1019281514611"></a><a name="p1019281514611"></a>【参数】</p>
<a name="ul122476544580"></a><a name="ul122476544580"></a><ul id="ul122476544580"><li>input：1个Tensor，支持数据类型：`int8`，`uint8`，`int16`，`uint16`，`int32`，`int64`，`float32`</li><li>axis：1个Tensor，数据类型`int32`，`int64`</li><li>out_type输出Tensor数据类型，`int32`或`int64`（可选，默认为`int64`）</li><li>name：string；名称（可选）</li></ul>
<p id="p2192111516469"><a name="p2192111516469"></a><a name="p2192111516469"></a>【约束】</p>
<p id="p1419211153462"><a name="p1419211153462"></a><a name="p1419211153462"></a>无限制</p>
<p id="p1719291519462"><a name="p1719291519462"></a><a name="p1719291519462"></a>【输出】</p>
<p id="p19192215104618"><a name="p19192215104618"></a><a name="p19192215104618"></a>1个Tensor，输出数据类型为out_type</p>
<p id="p9192615144610"><a name="p9192615144610"></a><a name="p9192615144610"></a>【量化工具支持】</p>
<p id="p71921415154613"><a name="p71921415154613"></a><a name="p71921415154613"></a>否</p>
</td>
</tr>
<tr id="row1194131518460"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p2194141564614"><a name="p2194141564614"></a><a name="p2194141564614"></a>54</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p16194161534613"><a name="p16194161534613"></a><a name="p16194161534613"></a>tf.gather</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p191941515194614"><a name="p191941515194614"></a><a name="p191941515194614"></a>Gather</p>
<p id="p1619410150466"><a name="p1619410150466"></a><a name="p1619410150466"></a>GatherV2</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p1019417151465"><a name="p1019417151465"></a><a name="p1019417151465"></a>【参数】</p>
<a name="ul6158628597"></a><a name="ul6158628597"></a><ul id="ul6158628597"><li>params：1个Tensor，维度必须大于`axis + 1`</li><li>indices：1个Tensor，数据类型`int32`，`int64`，范围[0，params.shape[axis]）</li><li>axis：输出Tensor数据类型，`int32`或`int64`，指定indices选取的维度，rank=0</li><li>name：string，名称（可选）</li></ul>
<p id="p1019571510462"><a name="p1019571510462"></a><a name="p1019571510462"></a>【约束】</p>
<p id="p1119511519463"><a name="p1119511519463"></a><a name="p1119511519463"></a>无限制</p>
<p id="p51956159460"><a name="p51956159460"></a><a name="p51956159460"></a>【输出】</p>
<p id="p619541510461"><a name="p619541510461"></a><a name="p619541510461"></a>1个Tensor，输出数据类型于params相同</p>
<p id="p6195161504620"><a name="p6195161504620"></a><a name="p6195161504620"></a>【量化工具支持】</p>
<p id="p11952015114620"><a name="p11952015114620"></a><a name="p11952015114620"></a>否</p>
</td>
</tr>
<tr id="row219571524617"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p1919521574613"><a name="p1919521574613"></a><a name="p1919521574613"></a>55</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p191951615124618"><a name="p191951615124618"></a><a name="p191951615124618"></a>tf.gather_nd</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p161951115104613"><a name="p161951115104613"></a><a name="p161951115104613"></a>GatherNd</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p81951115134613"><a name="p81951115134613"></a><a name="p81951115134613"></a>【参数】</p>
<a name="ul321219135916"></a><a name="ul321219135916"></a><ul id="ul321219135916"><li>params：1个Tensor，维度必须大于`axis + 1`</li><li>indices：1个Tensor，数据类型`int32`，`int64`</li><li>name：string；名称（可选）</li></ul>
<p id="p2070510145591"><a name="p2070510145591"></a><a name="p2070510145591"></a>【约束】</p>
<a name="ul649713107596"></a><a name="ul649713107596"></a><ul id="ul649713107596"><li>indices最后一维的大小不能超过params的维数</li><li>indices最后一维中的元素对应着params中的1个维度上的坐标，必须满足坐标规则</li><li>indices中对应维度上的坐标不能超过维度的大小</li></ul>
<p id="p141952154462"><a name="p141952154462"></a><a name="p141952154462"></a>【输出】</p>
<p id="p141951115154617"><a name="p141951115154617"></a><a name="p141951115154617"></a>1个Tensor，输出数据类型于params相同</p>
<p id="p1019514156466"><a name="p1019514156466"></a><a name="p1019514156466"></a>【量化工具支持】</p>
<p id="p14195181554618"><a name="p14195181554618"></a><a name="p14195181554618"></a>是</p>
</td>
</tr>
<tr id="row15195615124618"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p8195131564616"><a name="p8195131564616"></a><a name="p8195131564616"></a>56</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1419511516460"><a name="p1419511516460"></a><a name="p1419511516460"></a>tf.math.floordiv</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p1119531514462"><a name="p1119531514462"></a><a name="p1119531514462"></a>FloorDiv</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p15195115104611"><a name="p15195115104611"></a><a name="p15195115104611"></a>【参数】</p>
<a name="ul92661927165914"></a><a name="ul92661927165914"></a><ul id="ul92661927165914"><li>x：1个Tensor，数据类型：`float32`，`int32`，</li><li>y：1个Tensor，分母，数据类型：`float32`，`int32`</li><li>name：string；名称（可选）</li></ul>
<p id="p15196615124611"><a name="p15196615124611"></a><a name="p15196615124611"></a>【约束】</p>
<p id="p171969159468"><a name="p171969159468"></a><a name="p171969159468"></a>由于支持广播broadcast，对比x和y的shape，在同一纬度上，dim[x]只能相同或者一方为1或者一方缺失</p>
<p id="p1419671519466"><a name="p1419671519466"></a><a name="p1419671519466"></a>【输出】</p>
<p id="p2196141524615"><a name="p2196141524615"></a><a name="p2196141524615"></a>1个Tensor，floor（x/y）</p>
<p id="p1619651517460"><a name="p1619651517460"></a><a name="p1619651517460"></a>【量化工具支持】</p>
<p id="p181969158464"><a name="p181969158464"></a><a name="p181969158464"></a>否</p>
</td>
</tr>
<tr id="row2019621554613"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p171978151466"><a name="p171978151466"></a><a name="p171978151466"></a>57</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p41976158465"><a name="p41976158465"></a><a name="p41976158465"></a>tf.range</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p8197515194615"><a name="p8197515194615"></a><a name="p8197515194615"></a>Range</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p21971515164611"><a name="p21971515164611"></a><a name="p21971515164611"></a>【参数】</p>
<a name="ul364173316592"></a><a name="ul364173316592"></a><ul id="ul364173316592"><li>start：开始标量，数据类型`float32`，`int32`，必须为常量</li><li>limit：结束标量，数据类型`float32`，`int32`，必须为常量</li><li>delta：步长标量，数据类型`float32`，`int32`，必须为常量</li><li>dtype：返回Tensor的数据类型</li><li>name：string；名称（可选）</li></ul>
<p id="p519813151464"><a name="p519813151464"></a><a name="p519813151464"></a>【约束】</p>
<p id="p0198141584610"><a name="p0198141584610"></a><a name="p0198141584610"></a>无限制</p>
<p id="p419812158460"><a name="p419812158460"></a><a name="p419812158460"></a>【输出】</p>
<p id="p1419821544612"><a name="p1419821544612"></a><a name="p1419821544612"></a>1个1-D Tensor</p>
<p id="p1019871584615"><a name="p1019871584615"></a><a name="p1019871584615"></a>【量化工具支持】</p>
<p id="p10198115114610"><a name="p10198115114610"></a><a name="p10198115114610"></a>否</p>
</td>
</tr>
<tr id="row1198111518463"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p1919881513465"><a name="p1919881513465"></a><a name="p1919881513465"></a>58</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p161981615144620"><a name="p161981615144620"></a><a name="p161981615144620"></a>tf.tile</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p131981015144616"><a name="p131981015144616"></a><a name="p131981015144616"></a>Tile</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p9198131554619"><a name="p9198131554619"></a><a name="p9198131554619"></a>【参数】</p>
<a name="ul939713895916"></a><a name="ul939713895916"></a><ul id="ul939713895916"><li>input：输入Tensor，数据类型：<p id="p1875817455599"><a name="p1875817455599"></a><a name="p1875817455599"></a>`int8`，`uint8`，`int16`，`uint16`，`int32`，`int64`，`float32`</p>
</li><li>multiples：1-D Tensor，长度须和input的秩相同，数据类型：`int32`，必须为常量</li><li>name：string；名称（可选）</li></ul>
<p id="p1219861512464"><a name="p1219861512464"></a><a name="p1219861512464"></a>【约束】</p>
<p id="p1719816152461"><a name="p1719816152461"></a><a name="p1719816152461"></a>无限制</p>
<p id="p3198515194616"><a name="p3198515194616"></a><a name="p3198515194616"></a>【输出】</p>
<p id="p319881564612"><a name="p319881564612"></a><a name="p319881564612"></a>1个Tensor</p>
<p id="p2198215104611"><a name="p2198215104611"></a><a name="p2198215104611"></a>【量化工具支持】</p>
<p id="p519813153460"><a name="p519813153460"></a><a name="p519813153460"></a>是</p>
</td>
</tr>
<tr id="row619851510468"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p519891517465"><a name="p519891517465"></a><a name="p519891517465"></a>59</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p319811510465"><a name="p319811510465"></a><a name="p319811510465"></a>tf.size</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p16198015194617"><a name="p16198015194617"></a><a name="p16198015194617"></a>Size</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p6199215174615"><a name="p6199215174615"></a><a name="p6199215174615"></a>【参数】</p>
<a name="ul17917192616015"></a><a name="ul17917192616015"></a><ul id="ul17917192616015"><li>input：输入Tensor，数据类型：float32`</li><li>name：string；名称（可选）</li><li>out_type：输出Tensor数据类型，默认`int32`</li></ul>
<p id="p121997159466"><a name="p121997159466"></a><a name="p121997159466"></a>【约束】</p>
<p id="p161991156463"><a name="p161991156463"></a><a name="p161991156463"></a>无限制</p>
<p id="p319911515469"><a name="p319911515469"></a><a name="p319911515469"></a>【输出】</p>
<p id="p9199151515464"><a name="p9199151515464"></a><a name="p9199151515464"></a>1个Tensor，类型由out_type指定</p>
<p id="p719911159466"><a name="p719911159466"></a><a name="p719911159466"></a>【量化工具支持】</p>
<p id="p31995151461"><a name="p31995151461"></a><a name="p31995151461"></a>否</p>
</td>
</tr>
<tr id="row16199111513462"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p119971514464"><a name="p119971514464"></a><a name="p119971514464"></a>60</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p9199615134614"><a name="p9199615134614"></a><a name="p9199615134614"></a>tf.fill</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p5199215164618"><a name="p5199215164618"></a><a name="p5199215164618"></a>Fill</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p919951534619"><a name="p919951534619"></a><a name="p919951534619"></a>【参数】</p>
<a name="ul9371133314017"></a><a name="ul9371133314017"></a><ul id="ul9371133314017"><li>dims：1-D Tensor，数据类型：`int32`，</li><li>value：变量，数据类型：`int32`，`float32`</li><li>name：string；名称（可选）</li></ul>
<p id="p19200121515466"><a name="p19200121515466"></a><a name="p19200121515466"></a>【约束】</p>
<p id="p1420018152460"><a name="p1420018152460"></a><a name="p1420018152460"></a>支持Constant、GivenTensor、Range、Diagonal、Gaussian、MSRA、Uniform、UniformInt、UniqueUniform、XavierFill这些填充模式，在Uniform填充、UniformInt填充、UniqueUniform填充、xavier填充时，生成的数值区间最大范围介于[min，max）之间</p>
<p id="p112001715204612"><a name="p112001715204612"></a><a name="p112001715204612"></a>【输出】</p>
<p id="p720017157465"><a name="p720017157465"></a><a name="p720017157465"></a>1个Tensor，类型同value数据类型</p>
<p id="p22007153466"><a name="p22007153466"></a><a name="p22007153466"></a>【量化工具支持】</p>
<p id="p1120010151467"><a name="p1120010151467"></a><a name="p1120010151467"></a>否</p>
</td>
</tr>
<tr id="row19200131564612"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p5200161574614"><a name="p5200161574614"></a><a name="p5200161574614"></a>61</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1820031510465"><a name="p1820031510465"></a><a name="p1820031510465"></a>tf.concat</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p1320001564613"><a name="p1320001564613"></a><a name="p1320001564613"></a>Concat</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p1220051574612"><a name="p1220051574612"></a><a name="p1220051574612"></a>【参数】</p>
<a name="ul2048112401209"></a><a name="ul2048112401209"></a><ul id="ul2048112401209"><li>value：1个包含Tensor的列表，数据类型：`int32`，`float32`</li><li>axis：Tensor拼接轴向，数据类型：`int32`</li><li>name：string；名称（可选）</li></ul>
<p id="p720091584611"><a name="p720091584611"></a><a name="p720091584611"></a>【约束】</p>
<p id="p520041518462"><a name="p520041518462"></a><a name="p520041518462"></a>输入的tensor，除了进行concat的维度外，其他维度的size必须相等</p>
<p id="p32008156467"><a name="p32008156467"></a><a name="p32008156467"></a>输入的的tensor个数范围属于[1，1000]</p>
<p id="p142003154464"><a name="p142003154464"></a><a name="p142003154464"></a>【输出】</p>
<p id="p132008157464"><a name="p132008157464"></a><a name="p132008157464"></a>1个Tensor</p>
<p id="p17200191512469"><a name="p17200191512469"></a><a name="p17200191512469"></a>【量化工具支持】</p>
<p id="p1120020159463"><a name="p1120020159463"></a><a name="p1120020159463"></a>是</p>
</td>
</tr>
<tr id="row14200715204613"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p10200121524610"><a name="p10200121524610"></a><a name="p10200121524610"></a>62</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p7200151519464"><a name="p7200151519464"></a><a name="p7200151519464"></a>tf.reverse</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p132001415134610"><a name="p132001415134610"></a><a name="p132001415134610"></a>Reverse</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p2020012156467"><a name="p2020012156467"></a><a name="p2020012156467"></a>【参数】</p>
<a name="ul12932646607"></a><a name="ul12932646607"></a><ul id="ul12932646607"><li>tensor：1个包含Tensor的列表，</li><li>axis：Tensor reverse轴向，数据类型：`int32`</li><li>name：string；名称（可选）</li></ul>
<p id="p1820020159467"><a name="p1820020159467"></a><a name="p1820020159467"></a>【约束】</p>
<p id="p162002015164618"><a name="p162002015164618"></a><a name="p162002015164618"></a>无限制</p>
<p id="p19201101564615"><a name="p19201101564615"></a><a name="p19201101564615"></a>【输出】</p>
<p id="p72011115154616"><a name="p72011115154616"></a><a name="p72011115154616"></a>1个Tensor，数据类型同tensor</p>
<p id="p10201101515465"><a name="p10201101515465"></a><a name="p10201101515465"></a>【量化工具支持】</p>
<p id="p1320181584615"><a name="p1320181584615"></a><a name="p1320181584615"></a>否</p>
</td>
</tr>
<tr id="row82011915114615"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p4201915194619"><a name="p4201915194619"></a><a name="p4201915194619"></a>63</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1620112157460"><a name="p1620112157460"></a><a name="p1620112157460"></a>tf. reduce_sum</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p1720116152465"><a name="p1720116152465"></a><a name="p1720116152465"></a>sum</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p2020117152469"><a name="p2020117152469"></a><a name="p2020117152469"></a>【参数】</p>
<a name="ul121985413017"></a><a name="ul121985413017"></a><ul id="ul121985413017"><li>input_tensor：输入Tensor，</li><li>axis：Tensor sum轴向，数据类型：`int32`</li><li>keepdims：bool值，是否保留维度</li><li>name：string；名称（可选）</li><li>reduction_indices：axis旧的string；名称</li><li>keep_dims：不推荐使用，参数keepdims别名</li></ul>
<p id="p14201315184618"><a name="p14201315184618"></a><a name="p14201315184618"></a>【约束】</p>
<p id="p1920131515464"><a name="p1920131515464"></a><a name="p1920131515464"></a>无约束</p>
<p id="p620113156460"><a name="p620113156460"></a><a name="p620113156460"></a>【输出】</p>
<p id="p920121518462"><a name="p920121518462"></a><a name="p920121518462"></a>输出Tensor，数据类型同tensor</p>
<p id="p1220181594610"><a name="p1220181594610"></a><a name="p1220181594610"></a>【量化工具支持】</p>
<p id="p15201181519467"><a name="p15201181519467"></a><a name="p15201181519467"></a>否</p>
</td>
</tr>
<tr id="row6201715204614"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p0201141564620"><a name="p0201141564620"></a><a name="p0201141564620"></a>64</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p4201181564612"><a name="p4201181564612"></a><a name="p4201181564612"></a>tf. math.maximum</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p1820171512468"><a name="p1820171512468"></a><a name="p1820171512468"></a>Maximum</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p16201615124612"><a name="p16201615124612"></a><a name="p16201615124612"></a>【参数】</p>
<a name="ul39631701116"></a><a name="ul39631701116"></a><ul id="ul39631701116"><li>x：Tensor数据类型：`int32`，`int64`，`float32`</li><li>y：Tensor数据类型同x</li><li>name：string；名称（可选）</li></ul>
<p id="p17201131594611"><a name="p17201131594611"></a><a name="p17201131594611"></a>【约束】</p>
<p id="p19201915134612"><a name="p19201915134612"></a><a name="p19201915134612"></a>由于支持广播broadcast，对比x和y的shape，在同一纬度上，dim[x]只能相同或者一方为1或者一方缺失</p>
<p id="p220111519465"><a name="p220111519465"></a><a name="p220111519465"></a>【输出】</p>
<p id="p15202015154612"><a name="p15202015154612"></a><a name="p15202015154612"></a>输出Tensor，返回值（x &gt; y ? x ：y）</p>
<p id="p120211511462"><a name="p120211511462"></a><a name="p120211511462"></a>数据类型同x</p>
<p id="p6202111513466"><a name="p6202111513466"></a><a name="p6202111513466"></a>【量化工具支持】</p>
<p id="p520201519466"><a name="p520201519466"></a><a name="p520201519466"></a>否</p>
</td>
</tr>
<tr id="row14202191514615"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p820211564614"><a name="p820211564614"></a><a name="p820211564614"></a>65</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p202021515144617"><a name="p202021515144617"></a><a name="p202021515144617"></a>tf. math.minimum</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p16202141594616"><a name="p16202141594616"></a><a name="p16202141594616"></a>Minimum</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p020261512466"><a name="p020261512466"></a><a name="p020261512466"></a>【参数】</p>
<a name="ul17393469115"></a><a name="ul17393469115"></a><ul id="ul17393469115"><li>x：Tensor数据类型：`int32`，`int64`，`float32`</li><li>y：Tensor数据类型同x</li><li>name：名称（可选）</li></ul>
<p id="p162021615104613"><a name="p162021615104613"></a><a name="p162021615104613"></a>【约束】</p>
<p id="p1220218158466"><a name="p1220218158466"></a><a name="p1220218158466"></a>广播场景只支持下面两种：</p>
<p id="p5202171524614"><a name="p5202171524614"></a><a name="p5202171524614"></a>NHWC+scaler，NHWC+NHWC</p>
<p id="p182021152465"><a name="p182021152465"></a><a name="p182021152465"></a>【输出】</p>
<p id="p1620216154465"><a name="p1620216154465"></a><a name="p1620216154465"></a>输出Tensor，返回值（x &lt; y ? x ：y）</p>
<p id="p3202515204616"><a name="p3202515204616"></a><a name="p3202515204616"></a>数据类型同x</p>
<p id="p10202111574610"><a name="p10202111574610"></a><a name="p10202111574610"></a>【量化工具支持】</p>
<p id="p17202715144614"><a name="p17202715144614"></a><a name="p17202715144614"></a>否</p>
</td>
</tr>
<tr id="row14202131534618"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p82025158461"><a name="p82025158461"></a><a name="p82025158461"></a>66</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p102021415144612"><a name="p102021415144612"></a><a name="p102021415144612"></a>tf.clip_by_value</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p320214152466"><a name="p320214152466"></a><a name="p320214152466"></a>ClipByValue</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p520210153461"><a name="p520210153461"></a><a name="p520210153461"></a>【参数】</p>
<a name="ul1541714121819"></a><a name="ul1541714121819"></a><ul id="ul1541714121819"><li>t：Tensor</li><li>clip_value_min：clip最小值</li><li>clip_value_max：clip最大值</li><li>name：string；名称（可选）</li></ul>
<p id="p172021115104614"><a name="p172021115104614"></a><a name="p172021115104614"></a>【约束】</p>
<p id="p62021715184618"><a name="p62021715184618"></a><a name="p62021715184618"></a>min值要小于或者等于max值</p>
<p id="p920291512462"><a name="p920291512462"></a><a name="p920291512462"></a>【输出】</p>
<p id="p22025158467"><a name="p22025158467"></a><a name="p22025158467"></a>输出Tensor，返回值范围【clip_value_min，clip_value_max】</p>
<p id="p5203151514465"><a name="p5203151514465"></a><a name="p5203151514465"></a>【量化工具支持】</p>
<p id="p17203161524616"><a name="p17203161524616"></a><a name="p17203161524616"></a>否</p>
</td>
</tr>
<tr id="row3203161519469"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p1203181594614"><a name="p1203181594614"></a><a name="p1203181594614"></a>67</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p220311154468"><a name="p220311154468"></a><a name="p220311154468"></a>tf.math.logical_not</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p112031015164613"><a name="p112031015164613"></a><a name="p112031015164613"></a>LogicalNot</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p11203815164615"><a name="p11203815164615"></a><a name="p11203815164615"></a>【参数】</p>
<a name="ul682341818111"></a><a name="ul682341818111"></a><ul id="ul682341818111"><li>x：Tensor数据类型bool</li><li>name：string；名称（可选）</li></ul>
<p id="p82039155464"><a name="p82039155464"></a><a name="p82039155464"></a>【约束】</p>
<p id="p182031915184612"><a name="p182031915184612"></a><a name="p182031915184612"></a>无限制</p>
<p id="p1120331512461"><a name="p1120331512461"></a><a name="p1120331512461"></a>【输出】</p>
<p id="p5203515134616"><a name="p5203515134616"></a><a name="p5203515134616"></a>输出Tensor，数据类型bool</p>
<p id="p220311524611"><a name="p220311524611"></a><a name="p220311524611"></a>【量化工具支持】</p>
<p id="p620381515469"><a name="p620381515469"></a><a name="p620381515469"></a>否</p>
</td>
</tr>
<tr id="row112032015174619"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p92033154466"><a name="p92033154466"></a><a name="p92033154466"></a>68</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p720351554610"><a name="p720351554610"></a><a name="p720351554610"></a>tf.math.logical_and</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p15203161514461"><a name="p15203161514461"></a><a name="p15203161514461"></a>LogicalAnd</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p0203101534614"><a name="p0203101534614"></a><a name="p0203101534614"></a>【参数】</p>
<a name="ul14193124919"></a><a name="ul14193124919"></a><ul id="ul14193124919"><li>x：Tensor数据类型bool</li><li>y：Tensor数据类型bool</li><li>name：string；名称（可选）</li></ul>
<p id="p1620461519462"><a name="p1620461519462"></a><a name="p1620461519462"></a>【约束】</p>
<p id="p8204615124614"><a name="p8204615124614"></a><a name="p8204615124614"></a>BroadCast只支持如下几种维度的广播，NHWC和[1，1，1，1]，[N，H，W，C]，[N，H，W，1]，[1，H，W，C]，[N，1，1，C]</p>
<p id="p132041156463"><a name="p132041156463"></a><a name="p132041156463"></a>【输出】</p>
<p id="p2204101574619"><a name="p2204101574619"></a><a name="p2204101574619"></a>输出Tensor，数据类型bool</p>
<p id="p02041156465"><a name="p02041156465"></a><a name="p02041156465"></a>【量化工具支持】</p>
<p id="p1820491513469"><a name="p1820491513469"></a><a name="p1820491513469"></a>否</p>
</td>
</tr>
<tr id="row172041153462"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p142044157468"><a name="p142044157468"></a><a name="p142044157468"></a>69</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p8204515124619"><a name="p8204515124619"></a><a name="p8204515124619"></a>tf.equal</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p4204101544611"><a name="p4204101544611"></a><a name="p4204101544611"></a>Equal</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p1820415153463"><a name="p1820415153463"></a><a name="p1820415153463"></a>【参数】</p>
<a name="ul10282173215110"></a><a name="ul10282173215110"></a><ul id="ul10282173215110"><li>x：Tensor</li><li>y：Tensor，数据类型同x</li><li>name：string，名称（可选）</li></ul>
<p id="p20204101544614"><a name="p20204101544614"></a><a name="p20204101544614"></a>【约束】</p>
<p id="p1020491514612"><a name="p1020491514612"></a><a name="p1020491514612"></a>由于支持广播broadcast，对比x和y的shape，在同一纬度上右对齐的情况下，xdim[i]和ydim[i]只能相同或者一方为1或者一方缺失</p>
<p id="p2204111512463"><a name="p2204111512463"></a><a name="p2204111512463"></a>【输出】</p>
<p id="p162048157467"><a name="p162048157467"></a><a name="p162048157467"></a>输出Tensor，数据类型bool</p>
<p id="p620421511465"><a name="p620421511465"></a><a name="p620421511465"></a>【量化工具支持】</p>
<p id="p17204131513466"><a name="p17204131513466"></a><a name="p17204131513466"></a>否</p>
</td>
</tr>
<tr id="row3204015184614"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p1320451515469"><a name="p1320451515469"></a><a name="p1320451515469"></a>70</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1020414151464"><a name="p1020414151464"></a><a name="p1020414151464"></a>tf.square</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p62041815134614"><a name="p62041815134614"></a><a name="p62041815134614"></a>Square</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p14204191513468"><a name="p14204191513468"></a><a name="p14204191513468"></a>【参数】</p>
<a name="ul1083716382111"></a><a name="ul1083716382111"></a><ul id="ul1083716382111"><li>x：Tensor</li><li>name：string，名称（可选）</li></ul>
<p id="p1820481564612"><a name="p1820481564612"></a><a name="p1820481564612"></a>【约束】</p>
<p id="p32041315104610"><a name="p32041315104610"></a><a name="p32041315104610"></a>无限制</p>
<p id="p162041515104618"><a name="p162041515104618"></a><a name="p162041515104618"></a>【输出】</p>
<p id="p52041315154617"><a name="p52041315154617"></a><a name="p52041315154617"></a>输出Tensor，数据类型同x</p>
<p id="p920441544618"><a name="p920441544618"></a><a name="p920441544618"></a>【量化工具支持】</p>
<p id="p13204111534618"><a name="p13204111534618"></a><a name="p13204111534618"></a>否</p>
</td>
</tr>
<tr id="row920431554610"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p0205111513464"><a name="p0205111513464"></a><a name="p0205111513464"></a>71</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p3205161514611"><a name="p3205161514611"></a><a name="p3205161514611"></a>tf.image.crop_and_resize</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p10205191514616"><a name="p10205191514616"></a><a name="p10205191514616"></a>CropAndResize</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p7205101594615"><a name="p7205101594615"></a><a name="p7205101594615"></a>【参数】</p>
<a name="ul143411471018"></a><a name="ul143411471018"></a><ul id="ul143411471018"><li>image：4-D Tensor；数据类型：`float32`，`int8`，`int32`，`int64`，shape：`[num_boxes，4]`</li><li>boxes：2-D Tensor；数据类型：`float32`，shape：`[num_boxes]`</li><li>box_ind：1-D Tensor，数据类型：`int32`</li><li>crop_size：1-D Tensor，包含2个元素，数据类型：`int32`</li><li>method：string，表示插值方法，值为"bilinear"（默认），"nearest"</li><li>name：string；名称（可选）</li></ul>
<p id="p420581513463"><a name="p420581513463"></a><a name="p420581513463"></a>【约束】</p>
<p id="p4205015184614"><a name="p4205015184614"></a><a name="p4205015184614"></a>无限制</p>
<p id="p720511564610"><a name="p720511564610"></a><a name="p720511564610"></a>【输出】</p>
<p id="p52056153461"><a name="p52056153461"></a><a name="p52056153461"></a>Tensor，数据类型：`float32`</p>
<p id="p122050151465"><a name="p122050151465"></a><a name="p122050151465"></a>【量化工具支持】</p>
<p id="p520591511469"><a name="p520591511469"></a><a name="p520591511469"></a>否</p>
</td>
</tr>
<tr id="row1820517158466"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p1205161504611"><a name="p1205161504611"></a><a name="p1205161504611"></a>72</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p11205115154612"><a name="p11205115154612"></a><a name="p11205115154612"></a>tf.math.top_k</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p9217215114616"><a name="p9217215114616"></a><a name="p9217215114616"></a>TopKV2</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p1521751513465"><a name="p1521751513465"></a><a name="p1521751513465"></a>【参数】</p>
<a name="ul165514531719"></a><a name="ul165514531719"></a><ul id="ul165514531719"><li>input：Tensor，&gt;=1-D，最后1个维度大小必须大于k，数据类型：`float32`k：标量，&gt;=1；数据类型：`int32`</li><li>sorted：bool</li><li>name：string；名称（可选）</li></ul>
<p id="p521771524610"><a name="p521771524610"></a><a name="p521771524610"></a>【约束】</p>
<p id="p162171615174612"><a name="p162171615174612"></a><a name="p162171615174612"></a>K一定要以常量传入</p>
<p id="p221771513463"><a name="p221771513463"></a><a name="p221771513463"></a>【输出】</p>
<a name="ul121717151462"></a><a name="ul121717151462"></a><ul id="ul121717151462"><li>values：Tensor返回最后维度上的K个最大向量</li><li>indices：Tensor，values在input中的索引位置<p id="p1021881564613"><a name="p1021881564613"></a><a name="p1021881564613"></a>【量化工具支持】</p>
<p id="p521861524615"><a name="p521861524615"></a><a name="p521861524615"></a>否</p>
</li></ul>
</td>
</tr>
<tr id="row13218131518467"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p14218171524613"><a name="p14218171524613"></a><a name="p14218171524613"></a>73</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p821881554616"><a name="p821881554616"></a><a name="p821881554616"></a>tf.invert_permutation</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p5218415144619"><a name="p5218415144619"></a><a name="p5218415144619"></a>InvertPermutation</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p321821515464"><a name="p321821515464"></a><a name="p321821515464"></a>【参数】</p>
<a name="ul07071811923"></a><a name="ul07071811923"></a><ul id="ul07071811923"><li>x：1-D Tensor，数据类型：`int32`，`int64`，</li><li>name：string；名称（可选）</li></ul>
<p id="p2021815157462"><a name="p2021815157462"></a><a name="p2021815157462"></a>【约束】</p>
<p id="p14218181515461"><a name="p14218181515461"></a><a name="p14218181515461"></a>无限制</p>
<p id="p12218111512460"><a name="p12218111512460"></a><a name="p12218111512460"></a>【输出】</p>
<p id="p72181515134612"><a name="p72181515134612"></a><a name="p72181515134612"></a>Tensor，数据类型同x</p>
<p id="p17218191524612"><a name="p17218191524612"></a><a name="p17218191524612"></a>【量化工具支持】</p>
<p id="p82181115174618"><a name="p82181115174618"></a><a name="p82181115174618"></a>否</p>
</td>
</tr>
<tr id="row1521812151466"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p18218161534619"><a name="p18218161534619"></a><a name="p18218161534619"></a>74</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p152181115184620"><a name="p152181115184620"></a><a name="p152181115184620"></a>tf.multinomial</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p421861516467"><a name="p421861516467"></a><a name="p421861516467"></a>Multinomial</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p321810159469"><a name="p321810159469"></a><a name="p321810159469"></a>【参数】</p>
<a name="ul591928827"></a><a name="ul591928827"></a><ul id="ul591928827"><li>logits：2-D Tensor，shape `[batch_size，num_classes]`</li><li>num_samples：标量，抽样个数</li><li>seed：随机数种子，数据类型：`int32`，`int64`，</li><li>name：string；名称（可选）</li><li>output_dtype：输出Tensor数据类型：整型默认`int64`</li></ul>
<p id="p7218131584616"><a name="p7218131584616"></a><a name="p7218131584616"></a>【约束】</p>
<p id="p17218515154610"><a name="p17218515154610"></a><a name="p17218515154610"></a>seed为0时产生随机数是动态的</p>
<p id="p14218101524619"><a name="p14218101524619"></a><a name="p14218101524619"></a>输出数据行数等于输出数据的行，输出数据的列数等num_samples</p>
<p id="p112191215164610"><a name="p112191215164610"></a><a name="p112191215164610"></a>【输出】</p>
<p id="p11219141594610"><a name="p11219141594610"></a><a name="p11219141594610"></a>Tensor，数据类型同output_dtype</p>
<p id="p921918151469"><a name="p921918151469"></a><a name="p921918151469"></a>【量化工具支持】</p>
<p id="p1421915158466"><a name="p1421915158466"></a><a name="p1421915158466"></a>否</p>
</td>
</tr>
<tr id="row9219191524618"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p10219915114613"><a name="p10219915114613"></a><a name="p10219915114613"></a>75</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p82191815184616"><a name="p82191815184616"></a><a name="p82191815184616"></a>tf.reverse_sequence</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p122195155466"><a name="p122195155466"></a><a name="p122195155466"></a>ReverseSequence</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p521991514464"><a name="p521991514464"></a><a name="p521991514464"></a>【参数】</p>
<a name="ul563717156211"></a><a name="ul563717156211"></a><ul id="ul563717156211"><li>input：输入Tensor</li><li>seq_lengths：1-D Tensor；数据类型：`int32`，`int64`</li><li>seq_axis：标量，，数据类型：整型</li><li>batch_axis：标量（可选），数据类型：整型</li><li>name：string；名称（可选）</li></ul>
<p id="p62191515144613"><a name="p62191515144613"></a><a name="p62191515144613"></a>【约束】</p>
<a name="ul088092414216"></a><a name="ul088092414216"></a><ul id="ul088092414216"><li>seq_lengths的长度必须等于input在batchAxis的元素数</li><li>seq_lengths的最大元素必须要小于等于seq_dim的元素数</li><li>seqAxis、batchAxis、seqDim、batchDim必须是int64类型</li><li>seqAxis与seqDim不可同时指定，batchAxis与batchDim不可同时指定</li><li>batchAxis和batchDim是可选参数，缺省值为0，权值个数需要为1</li></ul>
<p id="p1322071584615"><a name="p1322071584615"></a><a name="p1322071584615"></a>【输出】</p>
<p id="p10220201519469"><a name="p10220201519469"></a><a name="p10220201519469"></a>Tensor，数据类型同input</p>
<p id="p10220115184617"><a name="p10220115184617"></a><a name="p10220115184617"></a>【量化工具支持】</p>
<p id="p722071514463"><a name="p722071514463"></a><a name="p722071514463"></a>否</p>
</td>
</tr>
<tr id="row8220151518468"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p1922019154467"><a name="p1922019154467"></a><a name="p1922019154467"></a>76</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p622021511468"><a name="p622021511468"></a><a name="p622021511468"></a>tf.math.reciprocal</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p1822061544615"><a name="p1822061544615"></a><a name="p1822061544615"></a>Reciprocal</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p1522011517464"><a name="p1522011517464"></a><a name="p1522011517464"></a>【参数】</p>
<a name="ul144873322022"></a><a name="ul144873322022"></a><ul id="ul144873322022"><li>x：输入Tensor数据类型`float32`</li><li>name：string；名称（可选）</li></ul>
<p id="p1922031511463"><a name="p1922031511463"></a><a name="p1922031511463"></a>【约束】</p>
<p id="p172208157464"><a name="p172208157464"></a><a name="p172208157464"></a>不支持输入数据中包含0</p>
<p id="p162207153465"><a name="p162207153465"></a><a name="p162207153465"></a>【输出】</p>
<p id="p1822071514468"><a name="p1822071514468"></a><a name="p1822071514468"></a>Tensor，数据类型同x</p>
<p id="p5220015184620"><a name="p5220015184620"></a><a name="p5220015184620"></a>【量化工具支持】</p>
<p id="p6220111510468"><a name="p6220111510468"></a><a name="p6220111510468"></a>否</p>
</td>
</tr>
<tr id="row1220171554615"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p3220181514462"><a name="p3220181514462"></a><a name="p3220181514462"></a>77</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p722021519468"><a name="p722021519468"></a><a name="p722021519468"></a>tf.nn.selu</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p2220151574612"><a name="p2220151574612"></a><a name="p2220151574612"></a>Selu</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p82201815154610"><a name="p82201815154610"></a><a name="p82201815154610"></a>【参数】</p>
<a name="ul496163919215"></a><a name="ul496163919215"></a><ul id="ul496163919215"><li>features：输入Tensor数据类型`float32`，</li><li>name：string；名称（可选）</li></ul>
<p id="p1322031512462"><a name="p1322031512462"></a><a name="p1322031512462"></a>【约束】</p>
<p id="p9220111516468"><a name="p9220111516468"></a><a name="p9220111516468"></a>无约束</p>
<p id="p12220111515468"><a name="p12220111515468"></a><a name="p12220111515468"></a>【输出】</p>
<p id="p72209155461"><a name="p72209155461"></a><a name="p72209155461"></a>Tensor，数据类型同features</p>
<p id="p722031512461"><a name="p722031512461"></a><a name="p722031512461"></a>【量化工具支持】</p>
<p id="p522061574617"><a name="p522061574617"></a><a name="p522061574617"></a>否</p>
</td>
</tr>
<tr id="row3220515184620"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p9220131544612"><a name="p9220131544612"></a><a name="p9220131544612"></a>78</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p52211215124610"><a name="p52211215124610"></a><a name="p52211215124610"></a>tf.math.acosh</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p622151564610"><a name="p622151564610"></a><a name="p622151564610"></a>Acosh</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p5221111584611"><a name="p5221111584611"></a><a name="p5221111584611"></a>【参数】</p>
<a name="ul10341545421"></a><a name="ul10341545421"></a><ul id="ul10341545421"><li>x：输入Tensor数据类型`float32`</li><li>name：string；名称（可选）</li></ul>
<p id="p922111594618"><a name="p922111594618"></a><a name="p922111594618"></a>【约束】</p>
<p id="p9221161544618"><a name="p9221161544618"></a><a name="p9221161544618"></a>无约束</p>
<p id="p16221111564619"><a name="p16221111564619"></a><a name="p16221111564619"></a>【输出】</p>
<p id="p1221515194612"><a name="p1221515194612"></a><a name="p1221515194612"></a>Tensor，数据类型同x</p>
<p id="p222114153462"><a name="p222114153462"></a><a name="p222114153462"></a>【量化工具支持】</p>
<p id="p20221151534619"><a name="p20221151534619"></a><a name="p20221151534619"></a>否</p>
</td>
</tr>
<tr id="row18221201512465"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p1422111515464"><a name="p1422111515464"></a><a name="p1422111515464"></a>79</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p19221101554618"><a name="p19221101554618"></a><a name="p19221101554618"></a>tf.math.asinh</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p12221161524611"><a name="p12221161524611"></a><a name="p12221161524611"></a>Asinh</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p8221101574615"><a name="p8221101574615"></a><a name="p8221101574615"></a>【参数】</p>
<a name="ul101921350628"></a><a name="ul101921350628"></a><ul id="ul101921350628"><li>x：输入Tensor数据类型`float32`</li><li>name：string；名称（可选）</li></ul>
<p id="p1522111158465"><a name="p1522111158465"></a><a name="p1522111158465"></a>【约束】</p>
<p id="p22215159467"><a name="p22215159467"></a><a name="p22215159467"></a>无约束</p>
<p id="p7221151524619"><a name="p7221151524619"></a><a name="p7221151524619"></a>【输出】</p>
<p id="p2221111514467"><a name="p2221111514467"></a><a name="p2221111514467"></a>Tensor，数据类型同x</p>
<p id="p1322161524611"><a name="p1322161524611"></a><a name="p1322161524611"></a>【量化工具支持】</p>
<p id="p202211315144612"><a name="p202211315144612"></a><a name="p202211315144612"></a>否</p>
</td>
</tr>
<tr id="row16221111519469"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p1622110150468"><a name="p1622110150468"></a><a name="p1622110150468"></a>80</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p62212155466"><a name="p62212155466"></a><a name="p62212155466"></a>tf.math.reduce_prod</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p722151511460"><a name="p722151511460"></a><a name="p722151511460"></a>Prod</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p6221151544616"><a name="p6221151544616"></a><a name="p6221151544616"></a>【参数】</p>
<a name="ul69659561927"></a><a name="ul69659561927"></a><ul id="ul69659561927"><li>input_tensor：输入Tensor</li><li>axis：reduce维度</li><li>keepdims：bool是否需要保存reduce维度</li><li>name：string；名称（可选）</li><li>reduction_indices：参数axis旧的别名（不推荐）</li><li>keep_dims：参数keepdims别名（不推荐）</li></ul>
<p id="p1222315184612"><a name="p1222315184612"></a><a name="p1222315184612"></a>【约束】</p>
<p id="p2222121514617"><a name="p2222121514617"></a><a name="p2222121514617"></a>无约束</p>
<p id="p1222615114614"><a name="p1222615114614"></a><a name="p1222615114614"></a>【输出】</p>
<p id="p1122291516467"><a name="p1122291516467"></a><a name="p1122291516467"></a>Tensor，raduce后的Tensor</p>
<p id="p122210154468"><a name="p122210154468"></a><a name="p122210154468"></a>【量化工具支持】</p>
<p id="p1022212156466"><a name="p1022212156466"></a><a name="p1022212156466"></a>否</p>
</td>
</tr>
<tr id="row18222171514466"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p1022216154463"><a name="p1022216154463"></a><a name="p1022216154463"></a>81</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p122214158465"><a name="p122214158465"></a><a name="p122214158465"></a>tf.math.sqrt</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p12222515194611"><a name="p12222515194611"></a><a name="p12222515194611"></a>Sqrt</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p132220152463"><a name="p132220152463"></a><a name="p132220152463"></a>【参数】</p>
<a name="ul114836417311"></a><a name="ul114836417311"></a><ul id="ul114836417311"><li>x：输入Tensor；数据类型：`float32`</li><li>name：string；名称（可选）</li></ul>
<p id="p10222151510468"><a name="p10222151510468"></a><a name="p10222151510468"></a>【约束】</p>
<p id="p122215150465"><a name="p122215150465"></a><a name="p122215150465"></a>无约束</p>
<p id="p8222191584616"><a name="p8222191584616"></a><a name="p8222191584616"></a>【输出】</p>
<p id="p1522215152464"><a name="p1522215152464"></a><a name="p1522215152464"></a>Tensor，数据类型同x</p>
<p id="p4222915114613"><a name="p4222915114613"></a><a name="p4222915114613"></a>【量化工具支持】</p>
<p id="p15222171515469"><a name="p15222171515469"></a><a name="p15222171515469"></a>否</p>
</td>
</tr>
<tr id="row152229159461"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p2022251511466"><a name="p2022251511466"></a><a name="p2022251511466"></a>82</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p172221155463"><a name="p172221155463"></a><a name="p172221155463"></a>tf.math.reduce_all</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p9222171518463"><a name="p9222171518463"></a><a name="p9222171518463"></a>All</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p18222201517465"><a name="p18222201517465"></a><a name="p18222201517465"></a>【参数】</p>
<a name="ul13824692315"></a><a name="ul13824692315"></a><ul id="ul13824692315"><li>input_tensor：输入Tensor；数据类型：bool</li><li>axis：指定reduce的维度</li><li>keepdims：bool值</li><li>name：string；名称（可选）</li><li>reduction_indices：axis旧的别名（不推荐）</li><li>keep_dims：keepdims别名（不推荐）</li></ul>
<p id="p822221515462"><a name="p822221515462"></a><a name="p822221515462"></a>【约束】</p>
<p id="p2022271564619"><a name="p2022271564619"></a><a name="p2022271564619"></a>无约束</p>
<p id="p1522291544611"><a name="p1522291544611"></a><a name="p1522291544611"></a>【输出】</p>
<p id="p15222191504617"><a name="p15222191504617"></a><a name="p15222191504617"></a>Tensor，数据类型同input_tensor</p>
<p id="p18222141515464"><a name="p18222141515464"></a><a name="p18222141515464"></a>【量化工具支持】</p>
<p id="p182221015114618"><a name="p182221015114618"></a><a name="p182221015114618"></a>否</p>
</td>
</tr>
<tr id="row112221715134610"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p7222121516468"><a name="p7222121516468"></a><a name="p7222121516468"></a>83</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1822213154463"><a name="p1822213154463"></a><a name="p1822213154463"></a>tf.nn.l2_normalize</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p1722371512466"><a name="p1722371512466"></a><a name="p1722371512466"></a>L2Normalize</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p6223181516464"><a name="p6223181516464"></a><a name="p6223181516464"></a>【参数】</p>
<a name="ul14991020933"></a><a name="ul14991020933"></a><ul id="ul14991020933"><li>x：输入Tensor；数据类型：boolean</li><li>axis：指定normalize的维度轴向<a name="ul430943935"></a><a name="ul430943935"></a><ul id="ul430943935"><li>如果format为NCHW，则axis必须为1</li><li>如果format为NHWC，则axis必须为3</li></ul>
</li><li>epsilon：规范化的下限值.如果norm&lt;sqrt（epsilon），将使用sqrt（epsilon）作为除数</li><li>name：string；名称（可选）</li><li>dim：axis旧的别名（不推荐）</li></ul>
<p id="p14223131514467"><a name="p14223131514467"></a><a name="p14223131514467"></a>【约束】</p>
<p id="p10223215124613"><a name="p10223215124613"></a><a name="p10223215124613"></a>H*W*2 &lt; 256*1024/4</p>
<p id="p52230151463"><a name="p52230151463"></a><a name="p52230151463"></a>【输出】</p>
<p id="p8223815184620"><a name="p8223815184620"></a><a name="p8223815184620"></a>Tensor，数据类型同x</p>
<p id="p15223171544618"><a name="p15223171544618"></a><a name="p15223171544618"></a>【量化工具支持】</p>
<p id="p82238157467"><a name="p82238157467"></a><a name="p82238157467"></a>否</p>
</td>
</tr>
<tr id="row8223515164618"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p2223111524614"><a name="p2223111524614"></a><a name="p2223111524614"></a>84</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p19223171517465"><a name="p19223171517465"></a><a name="p19223171517465"></a>tf.keras.backend.hard_sigmoid</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p122314153462"><a name="p122314153462"></a><a name="p122314153462"></a>Hardsigmoid</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p11223111534613"><a name="p11223111534613"></a><a name="p11223111534613"></a>【参数】</p>
<p id="p57872494310"><a name="p57872494310"></a><a name="p57872494310"></a>x：输入Tensor</p>
<p id="p6223151554616"><a name="p6223151554616"></a><a name="p6223151554616"></a>【约束】</p>
<p id="p12231415124610"><a name="p12231415124610"></a><a name="p12231415124610"></a>无限制</p>
<p id="p1223515114618"><a name="p1223515114618"></a><a name="p1223515114618"></a>【输出】</p>
<p id="p9223615134616"><a name="p9223615134616"></a><a name="p9223615134616"></a>输出Tensor，返回值：`0.` if `x &lt; -2.5`，`1.` if `x &gt; 2.5`</p>
<p id="p8223181515466"><a name="p8223181515466"></a><a name="p8223181515466"></a>当`-2.5 &lt;= x &lt;= 2.5`，返回`0.2 * x + 0.5`</p>
<p id="p922316159461"><a name="p922316159461"></a><a name="p922316159461"></a>【量化工具支持】</p>
<p id="p15223161564615"><a name="p15223161564615"></a><a name="p15223161564615"></a>否</p>
</td>
</tr>
<tr id="row182231015164619"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p17223315184618"><a name="p17223315184618"></a><a name="p17223315184618"></a>85</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p622331594619"><a name="p622331594619"></a><a name="p622331594619"></a>tf.keras.layers.ThresholdedReLU</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p122314158464"><a name="p122314158464"></a><a name="p122314158464"></a>ThresholdedReLU</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p1922321520466"><a name="p1922321520466"></a><a name="p1922321520466"></a>【参数】</p>
<p id="p82231515144613"><a name="p82231515144613"></a><a name="p82231515144613"></a>theta：标量&gt;=0，数据类型：；`float32`</p>
<p id="p222314153469"><a name="p222314153469"></a><a name="p222314153469"></a>【约束】</p>
<p id="p16223131511461"><a name="p16223131511461"></a><a name="p16223131511461"></a>无限制</p>
<p id="p10223201544611"><a name="p10223201544611"></a><a name="p10223201544611"></a>【输出】</p>
<p id="p9223415164611"><a name="p9223415164611"></a><a name="p9223415164611"></a>Tensor</p>
<p id="p422371516461"><a name="p422371516461"></a><a name="p422371516461"></a>【量化工具支持】</p>
<p id="p192231015134619"><a name="p192231015134619"></a><a name="p192231015134619"></a>否</p>
</td>
</tr>
<tr id="row822391574615"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p10223121518465"><a name="p10223121518465"></a><a name="p10223121518465"></a>86</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1022415152462"><a name="p1022415152462"></a><a name="p1022415152462"></a>tf.math.acos</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p1224191594612"><a name="p1224191594612"></a><a name="p1224191594612"></a>Acos</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p222461514460"><a name="p222461514460"></a><a name="p222461514460"></a>【参数】</p>
<p id="p2046511814410"><a name="p2046511814410"></a><a name="p2046511814410"></a>x：输入Tensor数据类型`float32`，`int32`，`int64`</p>
<p id="p546511818411"><a name="p546511818411"></a><a name="p546511818411"></a>name：string；名称（可选）</p>
<p id="p3224191513461"><a name="p3224191513461"></a><a name="p3224191513461"></a>【约束】</p>
<p id="p18224515104615"><a name="p18224515104615"></a><a name="p18224515104615"></a>输入数据范围（-1&lt;=x&lt;=1），输出数据范围（0&lt;=y&lt;=π）</p>
<p id="p132241415134615"><a name="p132241415134615"></a><a name="p132241415134615"></a>【输出】</p>
<p id="p2224161512463"><a name="p2224161512463"></a><a name="p2224161512463"></a>Tensor，数据类型同x</p>
<p id="p922471510464"><a name="p922471510464"></a><a name="p922471510464"></a>【量化工具支持】</p>
<p id="p92242155465"><a name="p92242155465"></a><a name="p92242155465"></a>否</p>
</td>
</tr>
<tr id="row1122401517466"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p1222471514466"><a name="p1222471514466"></a><a name="p1222471514466"></a>87</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p192242015184612"><a name="p192242015184612"></a><a name="p192242015184612"></a>tf.math.atan</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p82241615154617"><a name="p82241615154617"></a><a name="p82241615154617"></a>Arctan</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p15224161524610"><a name="p15224161524610"></a><a name="p15224161524610"></a>【参数】</p>
<p id="p875931220416"><a name="p875931220416"></a><a name="p875931220416"></a>x：输入Tensor数据类型`float32`，`int32`，`int64`</p>
<p id="p075915123412"><a name="p075915123412"></a><a name="p075915123412"></a>name：string；名称（可选）</p>
<p id="p722491584617"><a name="p722491584617"></a><a name="p722491584617"></a>【约束】</p>
<p id="p92241015154613"><a name="p92241015154613"></a><a name="p92241015154613"></a>输入数据范围（-65504&lt;=x&lt;=65504），输出数据范围（-π/2&lt;y&lt;π/2）</p>
<p id="p1322441564619"><a name="p1322441564619"></a><a name="p1322441564619"></a>【输出】</p>
<p id="p5224191516463"><a name="p5224191516463"></a><a name="p5224191516463"></a>Tensor，数据类型同x</p>
<p id="p132240150467"><a name="p132240150467"></a><a name="p132240150467"></a>【量化工具支持】</p>
<p id="p12245153464"><a name="p12245153464"></a><a name="p12245153464"></a>否</p>
</td>
</tr>
<tr id="row22241515134611"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p622417155468"><a name="p622417155468"></a><a name="p622417155468"></a>88</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p142241915194620"><a name="p142241915194620"></a><a name="p142241915194620"></a>tf.math.asin</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p5224815124615"><a name="p5224815124615"></a><a name="p5224815124615"></a>Asin</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p1922414150462"><a name="p1922414150462"></a><a name="p1922414150462"></a>【参数】</p>
<a name="ul1955820355413"></a><a name="ul1955820355413"></a><ul id="ul1955820355413"><li>x：输入Tensor数据类型`float32`，`int32`，`int64`</li><li>name：string；名称（可选）</li></ul>
<p id="p182241115174618"><a name="p182241115174618"></a><a name="p182241115174618"></a>【约束】</p>
<p id="p172248155464"><a name="p172248155464"></a><a name="p172248155464"></a>输入数据范围（-1&lt;=x&lt;=1），输出数据范围（-π/2&lt;=y&lt;=π/2）</p>
<p id="p18224315184619"><a name="p18224315184619"></a><a name="p18224315184619"></a>【输出】</p>
<p id="p72241915194617"><a name="p72241915194617"></a><a name="p72241915194617"></a>Tensor，数据类型同x</p>
<p id="p922415152461"><a name="p922415152461"></a><a name="p922415152461"></a>【量化工具支持】</p>
<p id="p2224141518469"><a name="p2224141518469"></a><a name="p2224141518469"></a>否</p>
</td>
</tr>
<tr id="row022416151464"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p16224141544617"><a name="p16224141544617"></a><a name="p16224141544617"></a>89</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p4225121594618"><a name="p4225121594618"></a><a name="p4225121594618"></a>tf.math.atanh</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p922571512469"><a name="p922571512469"></a><a name="p922571512469"></a>Atanh</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p422541512462"><a name="p422541512462"></a><a name="p422541512462"></a>【参数】</p>
<a name="ul969813251347"></a><a name="ul969813251347"></a><ul id="ul969813251347"><li>x：输入Tensor数据类型`float32`，`int32`，`int64`</li><li>name：string；名称（可选）</li></ul>
<p id="p62251515194611"><a name="p62251515194611"></a><a name="p62251515194611"></a>【约束】</p>
<p id="p2225131513466"><a name="p2225131513466"></a><a name="p2225131513466"></a>输入数据范围：x∈（-1，1）</p>
<p id="p622511594615"><a name="p622511594615"></a><a name="p622511594615"></a>【输出】</p>
<p id="p8225131514610"><a name="p8225131514610"></a><a name="p8225131514610"></a>Tensor，数据类型同x</p>
<p id="p32251615104617"><a name="p32251615104617"></a><a name="p32251615104617"></a>【量化工具支持】</p>
<p id="p52251815124617"><a name="p52251815124617"></a><a name="p52251815124617"></a>否</p>
</td>
</tr>
<tr id="row4225131515462"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p2225715144612"><a name="p2225715144612"></a><a name="p2225715144612"></a>90</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p7225191544612"><a name="p7225191544612"></a><a name="p7225191544612"></a>tf.math.tan</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p82252015194615"><a name="p82252015194615"></a><a name="p82252015194615"></a>Tan</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p14225191504613"><a name="p14225191504613"></a><a name="p14225191504613"></a>【参数】</p>
<a name="ul1753104318414"></a><a name="ul1753104318414"></a><ul id="ul1753104318414"><li>x：输入Tensor数据类型`float32`，`int32`，`int64`</li><li>name：string；名称（可选）</li></ul>
<p id="p322511156466"><a name="p322511156466"></a><a name="p322511156466"></a>【约束】</p>
<p id="p7225915144619"><a name="p7225915144619"></a><a name="p7225915144619"></a>无限制</p>
<p id="p82251415114614"><a name="p82251415114614"></a><a name="p82251415114614"></a>【输出】</p>
<p id="p1225915134614"><a name="p1225915134614"></a><a name="p1225915134614"></a>Tensor，数据类型同x</p>
<p id="p142251515184613"><a name="p142251515184613"></a><a name="p142251515184613"></a>【量化工具支持】</p>
<p id="p922561574611"><a name="p922561574611"></a><a name="p922561574611"></a>否</p>
</td>
</tr>
<tr id="row172251159462"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p922501584614"><a name="p922501584614"></a><a name="p922501584614"></a>91</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p20225121520463"><a name="p20225121520463"></a><a name="p20225121520463"></a>tf.math.logical_or</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p42250152461"><a name="p42250152461"></a><a name="p42250152461"></a>LogicalOr</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p192251215154616"><a name="p192251215154616"></a><a name="p192251215154616"></a>【参数】</p>
<a name="ul15457104812418"></a><a name="ul15457104812418"></a><ul id="ul15457104812418"><li>x：输入Tensor数据类型：`bool`</li><li>y：输入Tensor数据类型：`bool`</li><li>name：string；名称（可选）</li></ul>
<p id="p1522511155469"><a name="p1522511155469"></a><a name="p1522511155469"></a>【约束】</p>
<p id="p42251815134614"><a name="p42251815134614"></a><a name="p42251815134614"></a>由于支持广播broadcast，对比x和y的shape，在同一纬度上右对齐的情况下，xdim[i]和ydim[i]只能相同或者一方为1或者一方缺失</p>
<p id="p32251515174619"><a name="p32251515174619"></a><a name="p32251515174619"></a>【输出】</p>
<p id="p11225151520462"><a name="p11225151520462"></a><a name="p11225151520462"></a>Tensor，数据类型：`bool`</p>
<p id="p1122531510466"><a name="p1122531510466"></a><a name="p1122531510466"></a>【量化工具支持】</p>
<p id="p1722591574612"><a name="p1722591574612"></a><a name="p1722591574612"></a>否</p>
</td>
</tr>
<tr id="row17225615204614"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p5226151564610"><a name="p5226151564610"></a><a name="p5226151564610"></a>92</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1122661574616"><a name="p1122661574616"></a><a name="p1122661574616"></a>tf.math.reduce_min</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p322661516467"><a name="p322661516467"></a><a name="p322661516467"></a>ReduceMin</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p522651514614"><a name="p522651514614"></a><a name="p522651514614"></a>【参数】</p>
<a name="ul127801755242"></a><a name="ul127801755242"></a><ul id="ul127801755242"><li>input_tensor：输入Tensor数据类型：`float32`，`int64`，`int32`，`uint8`，`uint16`，`int8`，`int16`，</li><li>axis：reduce的维度轴向</li><li>keepdims：标量，bool类型</li><li>name：string；名称（可选）</li><li>reduction_indices：axis旧的别名</li><li>keep_dims：keepdims别名（不推荐）</li></ul>
<p id="p322661524618"><a name="p322661524618"></a><a name="p322661524618"></a>【约束】</p>
<a name="ul157886210512"></a><a name="ul157886210512"></a><ul id="ul157886210512"><li>当输入的tensor维数等于4时：输入axis={3，{1，2，3}}，keepDims=true，H*W*16*2 &lt;= 16*1024</li><li>当输入的tensor维数等于2时，输入axis={1，{1}}，keepDims=true，H*W*CEIL（C，16）*16*2 &lt;= 16*1024</li></ul>
<p id="p722671510460"><a name="p722671510460"></a><a name="p722671510460"></a>【输出】</p>
<p id="p1122641516468"><a name="p1122641516468"></a><a name="p1122641516468"></a>Tensor，数据类型同input_tensor</p>
<p id="p152261015174615"><a name="p152261015174615"></a><a name="p152261015174615"></a>【量化工具支持】</p>
<p id="p12226121534619"><a name="p12226121534619"></a><a name="p12226121534619"></a>否</p>
</td>
</tr>
<tr id="row152269159465"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p1226161517469"><a name="p1226161517469"></a><a name="p1226161517469"></a>93</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p102267155465"><a name="p102267155465"></a><a name="p102267155465"></a>tf.math.negative</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p722611157467"><a name="p722611157467"></a><a name="p722611157467"></a>Neg</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p32269157467"><a name="p32269157467"></a><a name="p32269157467"></a>【参数】</p>
<a name="ul99761591056"></a><a name="ul99761591056"></a><ul id="ul99761591056"><li>x：输入Tensor数据类型：`float32`，`int64`，`int32`</li><li>name：string；名称（可选）</li></ul>
<p id="p022621514469"><a name="p022621514469"></a><a name="p022621514469"></a>【约束】</p>
<p id="p4226121524618"><a name="p4226121524618"></a><a name="p4226121524618"></a>输入数据范围（-65504&lt;=x&lt;=65504），输出数据范围（-65504&lt;=y&lt;=65504）</p>
<p id="p2022614151464"><a name="p2022614151464"></a><a name="p2022614151464"></a>【输出】</p>
<p id="p1822681512463"><a name="p1822681512463"></a><a name="p1822681512463"></a>Tensor，输出=-x</p>
<p id="p12226201512468"><a name="p12226201512468"></a><a name="p12226201512468"></a>【量化工具支持】</p>
<p id="p13226191515461"><a name="p13226191515461"></a><a name="p13226191515461"></a>否</p>
</td>
</tr>
<tr id="row4226171544617"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p122613157463"><a name="p122613157463"></a><a name="p122613157463"></a>94</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p722621514611"><a name="p722621514611"></a><a name="p722621514611"></a>tf.math.greater_equal</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p12260150468"><a name="p12260150468"></a><a name="p12260150468"></a>Greaterequal</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p82261815144615"><a name="p82261815144615"></a><a name="p82261815144615"></a>【参数】</p>
<a name="ul38381017357"></a><a name="ul38381017357"></a><ul id="ul38381017357"><li>x：输入Tensor数据类型：`float32`，`int64`，`int32`，`uint8`，`uint16`，`int8`，`int16`</li><li>y：输入Tensor数据类型同x</li><li>name：string；名称（可选）</li></ul>
<p id="p522721524619"><a name="p522721524619"></a><a name="p522721524619"></a>【约束】</p>
<p id="p4227815144615"><a name="p4227815144615"></a><a name="p4227815144615"></a>输入数据范围（-65504&lt;=x&lt;=65504）</p>
<p id="p1622791510463"><a name="p1622791510463"></a><a name="p1622791510463"></a>【输出】</p>
<p id="p422741516466"><a name="p422741516466"></a><a name="p422741516466"></a>Tensor，输出类型bool</p>
<p id="p422718155468"><a name="p422718155468"></a><a name="p422718155468"></a>【量化工具支持】</p>
<p id="p1722751520469"><a name="p1722751520469"></a><a name="p1722751520469"></a>否</p>
</td>
</tr>
<tr id="row8227111524611"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p1122741584611"><a name="p1122741584611"></a><a name="p1122741584611"></a>95</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p14227215154614"><a name="p14227215154614"></a><a name="p14227215154614"></a>tf.space_to_depth</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p1222716155468"><a name="p1222716155468"></a><a name="p1222716155468"></a>SpaceToDepth</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p522721517465"><a name="p522721517465"></a><a name="p522721517465"></a>【参数】</p>
<a name="ul6687122719519"></a><a name="ul6687122719519"></a><ul id="ul6687122719519"><li>input：输入Tensor数据类型：`float32`，`int64`，`int32`，`uint8`，`int8`</li><li>block_size：标量，整型，值&gt;=2</li><li>data_format：数据类型：string值："NHWC"，"NCHW"，"NCHW_VECT_C"；默认值"NHWC"</li><li>name：string；名称（可选）</li></ul>
<p id="p9227201554610"><a name="p9227201554610"></a><a name="p9227201554610"></a>【约束】</p>
<p id="p10227161564610"><a name="p10227161564610"></a><a name="p10227161564610"></a>blockSize的大小必须大于等于1，且能被H和W整除</p>
<p id="p122701514468"><a name="p122701514468"></a><a name="p122701514468"></a>【输出】</p>
<p id="p1622781594618"><a name="p1622781594618"></a><a name="p1622781594618"></a>Tensor，输出类型input</p>
<p id="p1227215144620"><a name="p1227215144620"></a><a name="p1227215144620"></a>【量化工具支持】</p>
<p id="p1522781534617"><a name="p1522781534617"></a><a name="p1522781534617"></a>否</p>
</td>
</tr>
<tr id="row12227141514616"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p922741519460"><a name="p922741519460"></a><a name="p922741519460"></a>96</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1522718156464"><a name="p1522718156464"></a><a name="p1522718156464"></a>tf.depth_to_space</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p522781510468"><a name="p522781510468"></a><a name="p522781510468"></a>DepthToSpace</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p1227171504614"><a name="p1227171504614"></a><a name="p1227171504614"></a>【参数】</p>
<a name="ul557011351953"></a><a name="ul557011351953"></a><ul id="ul557011351953"><li>input：输入Tensor数据类型：`float32`，`int64`，`int32`，`uint8`，`int8`</li><li>block_size：标量，整型，值&gt;=2</li><li>data_format：数据类型：string值："NHWC"，"NCHW"，"NCHW_VECT_C"；默认值是"NHWC"</li><li>name：string；名称（可选）</li></ul>
<p id="p5227415114614"><a name="p5227415114614"></a><a name="p5227415114614"></a>【约束】</p>
<p id="p5227121584619"><a name="p5227121584619"></a><a name="p5227121584619"></a>blockSize必须大于等于1，且blockSize*blockSize必须能被C整除</p>
<p id="p192271151461"><a name="p192271151461"></a><a name="p192271151461"></a>【输出】</p>
<p id="p0227191514614"><a name="p0227191514614"></a><a name="p0227191514614"></a>Tensor，输出类型input</p>
<p id="p122719152466"><a name="p122719152466"></a><a name="p122719152466"></a>【量化工具支持】</p>
<p id="p202271215144618"><a name="p202271215144618"></a><a name="p202271215144618"></a>否</p>
</td>
</tr>
<tr id="row7227615124620"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p1222761574619"><a name="p1222761574619"></a><a name="p1222761574619"></a>97</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p2228515144613"><a name="p2228515144613"></a><a name="p2228515144613"></a>tf.math.round</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p822819155461"><a name="p822819155461"></a><a name="p822819155461"></a>Round</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p4228161594619"><a name="p4228161594619"></a><a name="p4228161594619"></a>【参数】</p>
<a name="ul2231742852"></a><a name="ul2231742852"></a><ul id="ul2231742852"><li>x：输入Tensor；数据类型：`float32`，`int64`，`int32`</li><li>name：string；名称（可选）</li></ul>
<p id="p62281015124612"><a name="p62281015124612"></a><a name="p62281015124612"></a>【约束】</p>
<p id="p5228151517460"><a name="p5228151517460"></a><a name="p5228151517460"></a>无限制</p>
<p id="p1922831515460"><a name="p1922831515460"></a><a name="p1922831515460"></a>【输出】</p>
<p id="p14228515194617"><a name="p14228515194617"></a><a name="p14228515194617"></a>Tensor，输出类型同x，输出shape同x</p>
<p id="p162281151465"><a name="p162281151465"></a><a name="p162281151465"></a>【量化工具支持】</p>
<p id="p1022811154462"><a name="p1022811154462"></a><a name="p1022811154462"></a>否</p>
</td>
</tr>
<tr id="row622813157462"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p422811564610"><a name="p422811564610"></a><a name="p422811564610"></a>98</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1522881564615"><a name="p1522881564615"></a><a name="p1522881564615"></a>tf.math.rint</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p122817153467"><a name="p122817153467"></a><a name="p122817153467"></a>Rint</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p3228515194614"><a name="p3228515194614"></a><a name="p3228515194614"></a>【参数】</p>
<a name="ul15281849459"></a><a name="ul15281849459"></a><ul id="ul15281849459"><li>x：输入Tensor；数据类型：`float32`，`int64`，`int32`，`uint8`，`int8`</li><li>name：string；名称（可选）</li></ul>
<p id="p20228015174613"><a name="p20228015174613"></a><a name="p20228015174613"></a>【约束】</p>
<p id="p92281315184614"><a name="p92281315184614"></a><a name="p92281315184614"></a>无限制</p>
<p id="p102281815114613"><a name="p102281815114613"></a><a name="p102281815114613"></a>【输出】</p>
<p id="p422891517468"><a name="p422891517468"></a><a name="p422891517468"></a>Tensor，输出类型同x，输出shape同x</p>
<p id="p8228615144611"><a name="p8228615144611"></a><a name="p8228615144611"></a>【量化工具支持】</p>
<p id="p15228101510464"><a name="p15228101510464"></a><a name="p15228101510464"></a>否</p>
</td>
</tr>
<tr id="row20228151514464"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p0228315184614"><a name="p0228315184614"></a><a name="p0228315184614"></a>99</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p822821554611"><a name="p822821554611"></a><a name="p822821554611"></a>tf.math.less</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p15228161520462"><a name="p15228161520462"></a><a name="p15228161520462"></a>Less</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p112282157466"><a name="p112282157466"></a><a name="p112282157466"></a>【参数】</p>
<a name="ul172447551654"></a><a name="ul172447551654"></a><ul id="ul172447551654"><li>x：输入Tensor数据类型：`float32`，`int64`，`int32`，`uint8`，`uint16`，`int8`，`int16`</li><li>y：输入Tensor数据类型同x，</li><li>name：string；名称（可选）</li></ul>
<p id="p9228315134610"><a name="p9228315134610"></a><a name="p9228315134610"></a>【约束】</p>
<p id="p122283154467"><a name="p122283154467"></a><a name="p122283154467"></a>无限制</p>
<p id="p42287153464"><a name="p42287153464"></a><a name="p42287153464"></a>【输出】</p>
<p id="p13228151519463"><a name="p13228151519463"></a><a name="p13228151519463"></a>Tensor，输出类型bool</p>
<p id="p422831594616"><a name="p422831594616"></a><a name="p422831594616"></a>【量化工具支持】</p>
<p id="p42281155466"><a name="p42281155466"></a><a name="p42281155466"></a>否</p>
</td>
</tr>
<tr id="row17228151518466"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p722861512464"><a name="p722861512464"></a><a name="p722861512464"></a>100</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p102291153468"><a name="p102291153468"></a><a name="p102291153468"></a>tf.math.sinh</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p162290158463"><a name="p162290158463"></a><a name="p162290158463"></a>Sinh</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p1922951516460"><a name="p1922951516460"></a><a name="p1922951516460"></a>【参数】</p>
<a name="ul1277611011612"></a><a name="ul1277611011612"></a><ul id="ul1277611011612"><li>x：输入Tensor数据类型：`float32`</li><li>name：string；名称（可选）</li></ul>
<p id="p022971518469"><a name="p022971518469"></a><a name="p022971518469"></a>【约束】</p>
<p id="p1122919154461"><a name="p1122919154461"></a><a name="p1122919154461"></a>无限制</p>
<p id="p11229101511466"><a name="p11229101511466"></a><a name="p11229101511466"></a>【输出】</p>
<p id="p1122901544611"><a name="p1122901544611"></a><a name="p1122901544611"></a>Tensor，输出类型同x</p>
<p id="p9229315134614"><a name="p9229315134614"></a><a name="p9229315134614"></a>【量化工具支持】</p>
<p id="p19229131510462"><a name="p19229131510462"></a><a name="p19229131510462"></a>否</p>
</td>
</tr>
<tr id="row1722981554615"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p82291153463"><a name="p82291153463"></a><a name="p82291153463"></a>101</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1922910151460"><a name="p1922910151460"></a><a name="p1922910151460"></a>tf.math.cosh</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p9229151512464"><a name="p9229151512464"></a><a name="p9229151512464"></a>Cosh</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p6229171515468"><a name="p6229171515468"></a><a name="p6229171515468"></a>【参数】</p>
<a name="ul1130714717618"></a><a name="ul1130714717618"></a><ul id="ul1130714717618"><li>x：输入Tensor数据类型：`float32`</li><li>name：string；名称（可选）</li></ul>
<p id="p2229171534615"><a name="p2229171534615"></a><a name="p2229171534615"></a>【约束】</p>
<p id="p102296151463"><a name="p102296151463"></a><a name="p102296151463"></a>无限制</p>
<p id="p172291615144617"><a name="p172291615144617"></a><a name="p172291615144617"></a>【输出】</p>
<p id="p152297157464"><a name="p152297157464"></a><a name="p152297157464"></a>Tensor，输出类型同x</p>
<p id="p2229715124618"><a name="p2229715124618"></a><a name="p2229715124618"></a>【量化工具支持】</p>
<p id="p182291415174615"><a name="p182291415174615"></a><a name="p182291415174615"></a>否</p>
</td>
</tr>
<tr id="row9229161518467"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.1 "><p id="p18229141594618"><a name="p18229141594618"></a><a name="p18229141594618"></a>102</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p122291515164610"><a name="p122291515164610"></a><a name="p122291515164610"></a>tf.math.squared_difference</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p722981513468"><a name="p722981513468"></a><a name="p722981513468"></a>Squared_difference</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p42291015174618"><a name="p42291015174618"></a><a name="p42291015174618"></a>【参数】</p>
<a name="ul185131318615"></a><a name="ul185131318615"></a><ul id="ul185131318615"><li>x：输入Tensor；数据类型：`float32`，`int64`，`int32`</li><li>y：输入Tensor数据类型同x</li><li>name：string；名称（可选）</li></ul>
<p id="p102291715124618"><a name="p102291715124618"></a><a name="p102291715124618"></a>【约束】</p>
<p id="p8229201519467"><a name="p8229201519467"></a><a name="p8229201519467"></a>广播模式只支持下列场景：</p>
<p id="p62290154460"><a name="p62290154460"></a><a name="p62290154460"></a>第1个的tensor_format是NCHW，另1个的dim{}可以是[1，1，1，1]，[N，C，H，W]，[N，1，H，W]，[1，C，H，W]，[N，C，1，1]，[1，C，1，1]，[1，1，H，W]，[N，1，1，1]这几种情况</p>
<p id="p4229161510464"><a name="p4229161510464"></a><a name="p4229161510464"></a>【输出】</p>
<p id="p42291915194610"><a name="p42291915194610"></a><a name="p42291915194610"></a>Tensor，数据类型同x</p>
<p id="p1922913158465"><a name="p1922913158465"></a><a name="p1922913158465"></a>【量化工具支持】</p>
<p id="p22291215184613"><a name="p22291215184613"></a><a name="p22291215184613"></a>否</p>
</td>
</tr>
</tbody>
</table>

