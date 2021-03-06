﻿---
title: Lync Server 2013：配置类别
TOCTitle: 配置类别
ms:assetid: 4547f514-f0c0-404d-890f-092ddeeac852
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204859(v=OCS.15)
ms:contentKeyID: 49312701
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中配置类别

 

_**上一次修改主题：** 2012-10-06_

在 Lync Server 2013 控制面板中，您可以使用“持久聊天”页的“类别”部分配置类别。持久聊天聊天室类别是组织聊天室的逻辑结构。类别定义一组默认的访问控制列表 (ACL)，以便控制可以创建或加入聊天室的用户和用户组。您还可以在组织中不同部门之间强制使用信息隔离墙。

聊天室类别可以包含聊天室，但不包含其他类别。每个类别使用*Name* 和*Description*元数据描述其内容。此外，类别还具有可以设置以控制其所拥有聊天室的行为的属性，例如聊天室是否允许执行*Invitations*或*File Uploads*操作，或者包含*Chat History*。

## 配置聊天室的类别

1.  使用分配给 CsPersistentChatAdministrator 或 CsAdministrator 角色的用户帐户登录您的本地部署中的任一计算机。

2.  从“开始”菜单中选择 Lync Server 控制面板或打开浏览器窗口，然后输入管理 URL。有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。
    
    > [!IMPORTANT]  
    > 您还可以使用 Windows PowerShell cmdlet。有关详细信息，请参阅部署文档中的 <a href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">使用 Windows PowerShell Cmdlet 配置持久聊天服务器</a>。


3.  在左侧导航栏中，单击“持久聊天”，然后单击“类别”。
    
    对于多个 持久聊天服务器池部署，从下拉列表中选择相应的池。

4.  在“类别”页上，单击“新建”或“编辑”。

5.  在“选择服务”中，选择需要在其上创建类别的 持久聊天服务器池对应的服务。该服务是 持久聊天服务器池，持久聊天（客户端）使用它来确定该类别属于哪个池。类别仅可属于一个 持久聊天服务器池，并且不能将其移到其他池或与其他池共享。

6.  在“新建类别”中，执行下列操作：
    
    1.  在“名称”中，指定新聊天室类别的名称。
    
    2.  在“描述”中，提供有关聊天室类别（例如 Contoso 聊天室类别）的详细描述。
    
    3.  要控制是否为属于此类别的聊天室启用邀请，请选中或清除“启用邀请”复选框。如果选中，则此类别的聊天室将打开或关闭邀请；如果清除，则不允许此类别的聊天室具有邀请。如果聊天室启用了邀请，则新成员添加到聊天室时，他/她将在其 持久聊天客户端中收到新聊天室的通知。
    
    4.  要控制属于此类别的聊天室中的文件上载，请选中或清除“启用文件上载”复选框。如果选中，该类别的聊天室可以启用或禁用文件上载；如果清除，则不允许该类别的聊天室执行文件上载操作。
        
        > [!IMPORTANT]  
		> 此设置在服务器上强制实施，因为使用 Office Communications Server 2007 R2群聊服务器或 Lync Server 2010 群聊的自定义应用程序或之前的 群聊客户端可以将文件发布到聊天室。 Lync 2013 客户端不具有文件上载/下载功能，因此如果您采用纯 Lync 2013 部署或 Lync 2013 客户端，则无法在 持久聊天服务器聊天室中发布文件。
    
    5.  要控制聊天历史记录，请选中或清除“启用聊天历史记录”复选框。如果选中，则聊天室聊天内容将变成持久的；否则，将不会保留聊天消息。如果启用了合规性，则将按合规性保存聊天室聊天内容，但用户无法访问较早的消息。此选项可用于指定为无需保留聊天历史记录的实时、临时协作的聊天室。

7.  在“编辑类别”中，执行下列操作：
    
      - 在“成员身份”的“允许的成员”部分中，添加或删除允许作为属于此类别的聊天室的成员添加的其他 Active Directory 域服务 主体（用户、通讯组、组织单位等）。类别允许的主体可搜索此类别的聊天室（除非隐藏了聊天室，在这种情况下，仅聊天室的成员可在此目录中搜索聊天室）。
    
      - 在“成员身份”的“拒绝的成员”部分，添加或删除与聊天室中拒绝的成员关联的用户和其他 Active Directory 主体。
    
      - 在“成员身份”的“创建者”部分，添加或删除与类别创建者关联的用户和其他 Active Directory 主体。创建者是有权创建聊天室并指定聊天室管理员和成员的用户。

8.  单击“提交”。

