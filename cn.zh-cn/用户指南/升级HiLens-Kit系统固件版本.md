# 升级HiLens Kit系统固件版本<a name="hilens_02_0084"></a>

使用智能边缘系统注册设备之前需要升级HiLens Kit系统固件版本至2.2.200.011。升级HiLens Kit系统固件版本前请仔细阅读如下内容。

## 升级须知<a name="section1735119570810"></a>

-   系统固件版本低于2.2.200.011，可以进行升级固件。系统固件版本查询方式：[登录Huawei HiLens智能边缘管理系统用户界面](https://support.huawei.com/enterprise/zh/doc/EDOC1100133284/1e2e9a10)，进入“维护\>固件升级“页面，查看“当前版本号“。

    详情请参见[HiLens Kit升级指导书](https://support.huawei.com/enterprise/zh/doc/EDOC1100133290?idPath=7919749%7C9856522%7C22892968%7C23710428%7C250700826)。

-   固件升级后，硬件版本会升级到2.2.200.011，同时HiLens固件会升级到1.0.6（如果HiLens Kit处于使用状态，且当前版本高于1.0.6，则会保留最新的HiLens 固件版本，不做更新）。
-   如果HiLens Kit为全新设备首次注册使用，我们推荐升级到最新固件版本，以获取更好的系统稳定性。
-   如果HiLens Kit已处于注册使用状态，我们建议您详细阅读[升级风险](#section1035617614114)后，决定是否升级。

## 升级风险<a name="section1035617614114"></a>

升级前请仔细阅读以下风险，谨慎升级。

-   HiLens Kit处于注册使用状态时，升级HiLens Kit系统固件版本前，请先联系接口人评估升级操作对业务连续性的风险。

-   升级HiLens Kit系统固件版本会重装整个系统目录，将导致系统目录下安装的软件会丢失。可采用如下方法确定系统目录的位置，用**df -h**命令可查看当前分区信息，“/dev/mmcblk0p2“对应根目录即是系统目录。此目录为软件默认安装目录，升级时该目录下安装的软件会丢失。其他非系统目录中的文件在升级过程中不受影响，如：“/dev/mmcblk0p\*“对应的目录。

    攻略：为了后面系统升级不受系统目录的影响，对于支持重定向安装的软件包，可以通过重定向安装到HiLens Kit设备系统“/opt“目录，规避以后系统升级，文件丢失问题。例如yum重定向安装软件包“XXX“，执行命令**yum --installroot=/opt install xxx**。对于不支持重定向安装的软件包，如yum安装、ROS安装涉及的rpm包，只能部署在系统目录，升级后会丢失。

-   升级HiLens Kit系统固件版本后可能会导致部分原有技能无法运行，请谨慎升级。

## 升级操作<a name="section13364545171415"></a>

已使用过HiLens Kit的用户，升级前请仔细阅读[升级风险](升级HiLens-Kit系统固件版本.md#section1035617614114)。

请执行**两次**升级系统固件版本操作，操作步骤如下：

详细升级操作请参见[HiLens Kit升级指导书](https://support.huawei.com/enterprise/zh/doc/EDOC1100133290?idPath=7919749%7C9856522%7C22892968%7C23710428%7C250700826)。

1.  首次获取升级包时，在企业技术支持网站（Support-E网站）[注册账号](https://uniportal.huawei.com/accounts/register.do?method=toRegister&appurl=http://support.huawei.com/enterprise?isFirstLogin=true&nls=zh)并[注册产品](https://support.huawei.com/enterprisemysupport/mysupport#click=productreg)，输入HiLens Kit的产品序列号（SN），系统默认输入产品名称，完成产品注册申请，详情请参见[提升权限](https://support.huawei.com/enterprise/enhanceMyPrivilege)。

    SN码标注于HiLens Kit底部，为一串长达20的字符串，例如“21023XXXXXXXXXXXXXXX“。

    产品注册申请提交之后，若是显示为“产品注册成功“，则可以直接执行下一步；若提示“产品待审核“则需要等待审核成功之后执行下一步，一个工作日之内审核。

2.  在[软件版本列表](https://support.huawei.com/enterprise/zh/ai-computing-platform/a200-3000hilens-pid-250700826/software/251268332?idAbsPath=fixnode01%7C7919749%7C9856522%7C22892968%7C23710428%7C250700826)中选择目标版本“A200-3000HiLens-FWV2.2.200.011.hpm“，下载升级包至本地PC。
3.  登录Huawei HiLens智能边缘管理系统，在本地PC中打开浏览器。在地址栏中输入华为HiLens智能边缘管理系统的地址，地址格式为“**https**://_华为HiLens__智能边缘管理系统的访问IP地址_”（默认IP为192.168.2.111）。

    详细操作请参见[登录Huawei HiLens智能边缘系统](https://support.huawei.com/enterprise/zh/doc/EDOC1100112066/a6312166)。

4.  在主菜单中选择“维护 \> 固件升级 \> 系统固件升级“。

    进入“系统固件升级“页面。

5.  单击“升级文件“后的  ![](figures/zh-cn_image_0241995390.png)，选择文件，即步骤2中下载的升级包。

    界面提示“已添加文件“。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >上传过程中，请勿切换或者关闭当前页面，否则会导致上传失败。  

6.  单击“升级“，在弹出的提示框中 勾选“升级完成后系统自动重启生效“。

    如果不勾选该选项，则需手动重启生效。

7.  单击“确定“。

    可在页面查看升级包版本号、升级进度等信息。

8.  等待10分钟左右，提示升级成功。

    若首次执行升级操作，重新登录Huawei HiLens智能边缘管理系统，请**重复执行**步骤3-步骤8。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >为确保设备注册成功，在执行第二次升级操作时，请使用同一个升级包。  


## 升级后<a name="section1785051216162"></a>

-   支持智能边缘系统注册设备，详情请参见[智能边缘系统注册设备](智能边缘系统注册设备.md)。
-   支持端侧通过admin登录最长1个小时不掉线。

    升级后，在admin用户模式下，通过命令**timeout**设置超时时间，最长1小时，例如设置超时时间为1小时，则执行命令**timeout 3600**。

-   首次登录智能边缘系统必须修改默认用户名、密码，防止使用默认用户名、密码带来的安全问题。
-   增加硬件设备和资源监测，当硬件异常或资源使用超过告警线，会上报告警提示您。
-   对第三方组件进行相关的安全升级。

