# 使用SD卡<a name="hilens_02_0123"></a>

HiLens Kit是端云协同多模态AI开发套件，使用过程中会产生视频、图像等数据，通常情况下通过接口将数据存储在OBS。如果需要将数据存储在本地，由于HiLens Kit自带的硬盘空间有限，需要外插SD卡来存储。

## 操作步骤<a name="section1960121211325"></a>

1.  SD卡插入HiLens Kit后面板接口“Micro SD“。
2.  SSH登录HiLens Kit，详情请见[SSH登录HiLens Kit设备](SSH登录HiLens-Kit设备.md)。
3.  查找SD卡位置，执行命令

    **ls -al /dev/mmcblk\***

    执行结果为

    **dev/mmcblk1**

4.  保存和备份SD卡已存储内容，格式化SD卡。

    **mkfs.ext4 /dev/mmcblk1**

    请在EulerOS提示符下执行。

    如果SD卡已格式化，请忽略此步骤。

5.  创建SD路径，执行命令

    **mkdir /mnt/sd**

    设备挂载到该路径下“mount /dev/ mmcblk1/mnt/sd“。

6.  查询文件系统，执行命令**df**。

    可执行以下命令，对本地文件test.txt进行读写测试。

    -   写命令：**cp test.txt /mnt/sd**
    -   读命令：**cp /mnt/sd/test.txt ./**


>![](public_sys-resources/icon-note.gif) **说明：** 
>SD卡使用完并拔出之前，请先卸载设备挂载的分区，执行命令
>**umount /mnt/sd**
>防止有文件损坏。

