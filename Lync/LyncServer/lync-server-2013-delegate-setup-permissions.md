---
title: 'Lync Server 2013: セットアップのアクセス許可の委任'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delegate setup permissions
ms:assetid: 9dca1683-4c69-4534-8ebe-6bd635cbae49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412735(v=OCS.15)
ms:contentKeyID: 48184997
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 453da166895c79cafe9f9637163e93a63ebccd75
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504284"
---
# <a name="delegate-setup-permissions-in-lync-server-2013"></a>Lync Server 2013 でのセットアップのアクセス許可の委任

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-02-05_

Lync Server 2013 を展開しているユーザーまたはグループに Domain Admins グループのメンバーシップを付与しない場合は、RTCUniversalServerAdmins グループのメンバーが、Lync Server 2013 を実行しているサーバーで、 **enable-CsTopology**   Windows PowerShell コマンドレットを実行できるようにすることができます。 既定では、RTCUniversalServerAdmins グループのメンバーは、このコマンドレットを実行することはできません。 Lync Server を実行しているサーバーで **Enable-CsTopology** を実行する **ための管理** 者権限とアクセス許可を付与するには、lync server 2013 を実行しているサーバーのコンピューターオブジェクトが配置されている組織単位 (OU) を指定します。

Lync Server をインストールするときに実行されるドメインの準備には、RTCUniversalServerAdmins グループのメンバーが Enable-CsTopology コマンドレットを実行できるようにするアクセス許可が自動的に追加されることはありません。 つまり、既定では、トポロジを有効にするためにはドメイン管理者である必要があります。 RTCUniversalServerAdmins グループのメンバーにトポロジを有効にする権限を付与するには、Grant-CsSetupPermissions コマンドレットを実行する必要があります。 さらに、Lync Server を実行しているコンピューターを格納する各 Active Directory コンテナーに対して、このコマンドレットを実行する必要があります。

このコマンドレットは、RTCUniversalServerAdmins グループのみにアクセス許可を付与する点に留意してください。他のセキュリティ グループまたは個別のユーザーにアクセス許可を付与するために使用することはできません。

<div>


> [!NOTE]  
> <STRONG>Enable-CsTopology</STRONG> は、RTCUniversalServerAdmins グループのメンバーが Lync Server 2013 のセットアップと展開を行えるようにするためのキーコマンドレットです。



</div>

<div>

## <a name="to-add-the-ability-to-run-enable-cstopology-to-the-rtcuniversalserveradmins-group"></a>RTCUniversalServerAdmins グループに、Enable-CsTopology を実行する権限を追加するには

1.  委任されたユーザーが **Enable-CsTopology** を実行する予定のドメインの Domain Admins グループのメンバーとしてサーバーにログオンします。

2.  Lync Server 2013 管理シェルを開きます。 Lync Server 2013 管理シェルは、各フロントエンドサーバーまたは Lync Server 2013 管理ツールがインストールされているすべてのコンピューターに、自動的にインストールされます。 Lync Server 2013 管理シェルの詳細については、「操作」のドキュメントの「 [Lync server 2013 Management shell](lync-server-2013-lync-server-management-shell.md) 」を参照してください。

3.  Lync Server 2013 管理シェルから、次のコマンドレットを実行します。
    
        Grant-CsSetupPermission -ComputerOU <DN of the OU> -Domain <Domain FQDN>
    
    <div>
    

    > [!NOTE]  
    > OU が最上位レベルでない場合は、完全ドメイン名を指定する必要があります。

    
    </div>
    
    次の例では、OU は、contoso.com ドメインにある "Lync Servers" です。
    
        Grant-CsSetupPermission -ComputerOU "OU=Lync Servers" -Domain contoso.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

