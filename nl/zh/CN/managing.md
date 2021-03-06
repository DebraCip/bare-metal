---



copyright:

  years: 2016
lastupdated: "2016-01-19"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# 管理裸机服务器
{: #managing}


您可以停止、启动、重新启动和取消服务器。
{:shortdesc}

## 复制服务器实例
可以复制或克隆裸机服务器实例，以复制服务器配置以及快速启动并运行新服务器。
{:shortdesc}

要克隆实例，请执行以下操作：
 1. 转至菜单并选择**配置副本**。这将复制所有配置。但并非所有日期或内容都会复制。
 2. 输入唯一的服务器名称。
 3. 指定域名。

## 重装操作系统
有时，您可能希望在服务器上重装操作系统。
{:shortdesc}

要重装操作系统，请执行以下操作：
 1. 开始之前，先备份所有数据。如果跳过此步骤，那么所有现有数据都将丢失，并且无法取回。
 2. 转至菜单并选择**操作系统重装**。可以选择：
  * 将操作系统更改为其他操作系统，然后使用新配置重新开始。
  * 保留使用当前配置的现有操作系统，但擦除服务器以重新开始。

在操作系统重装期间，服务器将处于脱机状态且不可用。根据服务器容量和操作系统，重装时间会有所不同。如果定义了供应脚本，那么将在重装完成后复原所有配置。如果在操作系统重装之前备份了数据，那么可以在服务器可用后，将这些数据上载到服务器。

## 删除服务器实例
如果不再需要裸机服务器实例，也不想再为其支付费用，那么可以随时删除该实例。
{:shortdesc}

要删除实例，请转至菜单并选择**取消服务器**。

## 关闭服务器的电源
可以预先创建服务器以准备使用，但接着关闭其电源以确保不会发生任何更改，并且任何人都无法对其进行访问。准备就绪后，可以打开服务器电源，服务器在数分钟内就可就绪。
{:shortdesc}

要关闭服务器电源，请转至菜单并选择**打开/关闭电源**。服务器电源关闭期间，仍将对您进行记帐。

**注：**如果服务器电源已关闭，那么它会一直保持电源关闭状态，您必须手动打开其电源。
