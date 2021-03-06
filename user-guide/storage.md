# 3.4 存储
这里的存储指的是「有状态服务」的持久化存储卷，采用的是ceph分布式存储方案，具备高可靠、高可用、高安全的特性。

***
## 3.4.1 属性说明

### 3.4.1.1 存储卷本身
![](_figures/user-guide/storage-service.png)

**1. 名称：**存储卷一旦创建完成，「名称」就不能被修改

!> **命名规则：**2-64位的小写字母、数字或"-"，不能以"-"开头或结尾

**2. 大小：**最小为1G，最大为1024G，调整的最小粒度为1G。

### 3.4.1.2 挂载到服务
![](_figures/user-guide/storage-create.png)

**1. 名称：**存储卷挂载的服务名称

**2. 读写方式：**服务对存储卷的操作权限，分读写和只读    

**3. 挂载路径：**存储卷挂载到容器内的文件路径，对存储卷的读写需要在该路径下操作    
***

!>**注意**：如果挂载到的目录内原原先已有文件，挂载存储卷后，整个目录将会被覆盖

## 3.4.2 如何创建存储卷，并挂载到服务

添加存储卷到服务有两种方式：    
第一种是在「创建服务」时添加。    
第二种是先在「存储」组件页面下创建存储卷，再选择需要挂载到的服务。

### 3.4.2.1 「创建服务」时添加
首先要保证创建的是有状态服务，接下来操作如下：

**1）在「存储卷配置」处，点击「添加存储配置」**    
![](_figures/user-guide/storage-create-service.png)

**2）如果存储卷已经存在，可以直接下拉选择；如果存储卷不存在，可以点击「添加」icon，创建一个存储卷实例**    
![](_figures/user-guide/storage-create-service-2.png)

### 3.4.2.2 先创建存储卷，再选择挂载的服务
操作如下：

**1）点击控制台左边栏的「存储」，切换至存储页面**

**2）点击「添加存储配置」**    

**3）创建完成后，点击「挂载到服务」icon**    
![](_figures/user-guide/storage-storage-service.png)
***

## 3.4.3 如何将存储卷从服务解绑

从服务解绑存储卷有两种方式：    
第一种是选择需要解绑的服务，通过「服务升级」删除存储卷。[详见3.3.5](user-guide/service?id=_335-如何做服务升级)    
第二种是选择需要解绑的存储卷，通过「从服务移除」操作解绑。

!>**注意：**解绑存储卷，可能会导致服务不可用，请谨慎操作

### 3.4.3.1 通过「从服务移除」解绑存储卷

操作如下：

**1）点击控制台左边栏的「存储」，切换至存储页面** 

**2）查找需要解绑的存储卷，点击「从服务移除」icon**  
![](_figures/user-guide/storage-storage-service-off.png)
***

## 3.4.4 如何删除存储卷
删除存储卷前，先要保证该存储卷已经从服务解绑。

!>**注意：**删除存储卷，会导致数据不可恢复

![](_figures/user-guide/storage-delete.gif)
