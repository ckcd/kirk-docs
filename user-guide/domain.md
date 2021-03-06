# 3.7 域名
用户可以自主添加域名到平台，通过绑定域名到「HTTP/HTTPS七层负载均衡」，使负载均衡绑定的服务能够以用户域名的方式在外网暴露。
***

## 3.7.1 属性说明

![](_figures/user-guide/domain_para.jpg)

**1. 域名名称：**域名一旦被添加，就不能修改域名名称

**2. 选择证书：**添加证书是为了开启HTTPS，证书购买和管理使用的是[七牛云开发者平台 - SSL证书服务](https://portal.qiniu.com/certificate/ssl#cert)<br>

!> 注意：证书对应的域名需要与「域名名称」一致并且证书需要在有效期内。

**3. 开启HTTPS：**开启HTTPS需要先「选择证书」。开启后，对域名的请求将转成HTTPS请求
***

## 3.7.2 如何添加域名

操作如下：

**1）点击左侧菜单栏「域名管理」，进入域名管理界面**

**2）点击「添加域名」**

?> 域名名称：域名一旦被添加，就不能修改域名名称<br>
   选择证书：添加证书是为了开启HTTPS，证书购买和管理使用的是[七牛云开发者平台 - SSL证书服务](https://portal.qiniu.com/certificate/ssl#cert)<br>
   开启HTTPS：开启HTTPS需要先「选择证书」。开启后，对域名的请求将转成HTTPS请求<br>

!> 注意：证书对应的域名需要与「域名名称」一致并且证书需要在有效期内。
***

## 3.7.2 如何配置 CNAME

添加域名完成后，会提示需要配置域名 CNAME 到指定的「CNAME 域名」，「CNAME 域名」只能用于配置 CNAME，不能访问，CNAME 生效后方可使用。

![配置 CNAME](_figures/user-guide/domain_cname.jpg)

**如何配置 CNAME？**<br>
配置 CNAME 需要前往您的域名服务商添加一条 CNAME 记录，并把系统显示的「 CNAME 域名」填写在记录值中。等待一段时间后，域名列表中的域名状态会从「未绑定」变成「已绑定」。

?> **添加的域名会有两种状态：**  
**未绑定** - CNAME 地址未绑定到域名。刚结束绑定操作，需要等候约5分钟完成系统验证，请及时刷新列表以更新绑定状态  
**已绑定** - CNAME 地址成功绑定到域名
***

## 3.7.3 如何更新域名证书

操作如下：

**1）点击左侧菜单栏「域名管理」，进入域名管理界面**

**2）点击域名右侧的「编辑」icon**

![编辑域名](_figures/user-guide/domain_edit.jpg)

**3）点击「选择证书」，进行证书切换**

?>如果需要从域名下线证书，必须先将「开启HTTPS」置为否。
***

## 3.7.4 如何删除域名

操作如下：

**1）点击左侧菜单栏「域名管理」，进入域名管理界面**

**2）勾选需要删除的域名，点击上方的「删除域名」按钮即可删除域名**

!> 已被添加至负载均衡的域名需要先从负载均衡中移除才可删除。

![删除域名](_figures/user-guide/domain_delete.jpg)
