查看集群运行详情
================

你可在\ **集群指标**\ 和\ **集群状态**\ 面板查看集群和集群中各主机及节点的近实时运行状态和数据指标，例如主机运行状态、CPU、内存及网络使用情况等。

前提条件
--------

要访问\ **集群指标**\ 和\ **集群状态**\ 面板，你需要：

1. 确保当前集群是通过可视化部署方法部署的。详情参见\ :ref:`可视化部署 <deploy-guides/physical-deploy/visualized-deploy:可视化部署>`\ 。
2. 在浏览器中通过 ``http://<集群节点 IP>:7788/`` 访问 Web Platform 面板。
3. 在左侧导航点击\ **集群指标**\ 或\ **集群状态**\ ，即可进入该页面。

查看集群整体运行状态
--------------------

.. image:: /images/web-platform-view-cluster-status-1.png

**集群指标**\ 面板展示了集群的 CPU、内存、磁盘 I/O 和网络繁忙程度等数据。

你可以通过页面右上方的下拉菜单来调整数据展示的时间范围，可选时间范围为“2 小时”、“6 小时”、“1 天”和“7 天”。数据计算时间单位随所选时间范围变化。

图表以时间为横轴，数值或百分比为纵轴。

当鼠标悬停在某一时点时，会弹出该时点的数据。可通过横向滑动光标查看不同时点的数据。每个图表右上角提供了相应的图例。

集群 CPU 使用状况
~~~~~~~~~~~~~~~~~

该图表展示如下指标：

-  所有用户进程 CPU 使用 (%) 的平均值、倾斜和最大值
-  所有系统进程 CPU 使用 (%) 的平均值、倾斜和最大值
-  总 CPU 使用 (%) 的平均值、倾斜和最大值
-  最繁忙的主机

集群内存使用状况
~~~~~~~~~~~~~~~~

该图表展示如下指标：

-  正在使用总内存 (%) 的平均值、倾斜和最大值
-  总缓冲区内存 (%) 的平均值、倾斜和最大值
-  可用内存 (%) 的平均值、倾斜和最大值
-  最繁忙的主机

集群磁盘 I/O 速率
~~~~~~~~~~~~~~~~~

-  磁盘读取速率 (MB/s) 的平均值、倾斜和最大值
-  磁盘写入速率 (MB/s) 的平均值、倾斜和最大值
-  读取最繁忙的主机
-  写入最繁忙的主机

.. attention:: 该图表横轴以上部分显示磁盘读取数据，横轴以下部分显示写入数据。

网络繁忙程度
~~~~~~~~~~~~

-  网络读取速率 (MB/s) 的平均值、倾斜和最大值
-  网络写入速率 (MB/s) 的平均值、倾斜和最大值
-  读取最繁忙的主机
-  写入最繁忙的主机
-  **注意：**\ 该图表横轴以上部分显示网络读取数据，横轴以下部分显示写入数据。

查看集群中节点和主机运行状态
----------------------------

**集群状态**\ 面板展示了主机和 Segment 节点的运行状态和各项指标。你可在页面左上角选择查看\ **主机指标**\ 或 **Segment 状态**\ 。

.. image:: /images/web-platform-view-cluster-status-2.png

主机指标
~~~~~~~~

**主机指标**\ 子面板分别展示了 Coordinator 主机及其备用主机，以及 Segment 主机的运行状态和各项指标：

**注意**\ ：Segment 主机数据表提供了按主机名搜索功能。

========================== ========================================
**字段**                   **描述**
========================== ========================================
主机名                     Coordinator 或 Segment 主机的主机名
CPU 用户进程/系统进程/闲置 用户进程使用、系统进程使用和闲置 CPU (%)
内存空间 (GB)              已使用内存和可用内存
磁盘读 (MB/s)              磁盘读取速率
磁盘写 (MB/s)              磁盘写入速率
网络读 (MB/s)              网络读取速率
网络写 (MB/s)              网络写入速率
========================== ========================================

Segment 状态
~~~~~~~~~~~~

**Segment 状态**\ 子面板展示了各个 Segment 的数据及状态。

页面上方在展示了数据库整体状态、Segment 总数、Segment 主机数及状态为 ``Up`` 和 ``Down`` 的 Segment 数量。

下方图表展示了如下指标和状态：

+----------+----------------------------------------------------------+
| **字段** | **描述**                                                 |
+==========+==========================================================+
| 主机名   | Segment 主机的主机名。                                   |
+----------+----------------------------------------------------------+
| 地址     | Segment 主机在集群中的地址。                             |
+----------+----------------------------------------------------------+
| 端口     | Segment 主机的监听端口。                                 |
+----------+----------------------------------------------------------+
| DB ID    | 数据库 ID。                                              |
+----------+----------------------------------------------------------+
| 内容 ID  | Segment 的内容标识符。                                   |
+----------+----------------------------------------------------------+
| 状态     | Segment 状态，可选值为：\ ``Up`` 或 ``Down``\ 。         |
+----------+----------------------------------------------------------+
| 当前角色 | Segment 当前充当的角色，值： ``p`` (Primary) 或 ``m``    |
|          | (Mirror)。                                               |
+----------+----------------------------------------------------------+
| 初始角色 | Segment 在初始化时被赋予的角色，值：\ ``p`` (Primary) 或 |
|          | ``m`` (Mirror)。                                         |
+----------+----------------------------------------------------------+
| 备份模式 | Segment 和其镜像备份的同步状态，值：\ ``s``              |
|          | (Synchronized) or ``n`` (Not In Sync)。                  |
+----------+----------------------------------------------------------+
