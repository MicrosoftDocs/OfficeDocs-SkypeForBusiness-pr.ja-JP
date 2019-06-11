---
title: 'Lync Server 2013: セットアップのアクセス許可の委任'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delegate setup permissions
ms:assetid: 9dca1683-4c69-4534-8ebe-6bd635cbae49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412735(v=OCS.15)
ms:contentKeyID: 48184997
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7df00740ac971fd56e289da04ca43abb1619329
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833662"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delegate-setup-permissions-in-lync-server-2013"></a>Lync Server 2013 でのセットアップのアクセス許可の委任

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-02-05_

Lync Server 2013 を展開しているユーザーまたはグループに domain Admins グループのメンバーシップを付与しない場合は、RTCUniversalServerAdmins グループのメンバーを有効にして、**有効** にすることができます。Lync Server 2013 を実行しているサーバー。 既定では、RTCUniversalServerAdmins グループのメンバーはこのコマンドレットを実行することはできません。 管理者の権限とアクセス許可を付与して、Lync Server を実行しているサーバーで**Enable-CsTopology**権限を付与するには、**グラント/cssetuppermission**レットを使用し、サーバーのコンピューターオブジェクトが実行されている組織単位 (OU) を指定します。Lync Server 2013 があります。

Lync Server をインストールするときに実行されるドメインの準備によって、RTCUniversalServerAdmins グループのメンバーが Enable-CsTopology コマンドレットを実行できるようにする権限が自動的に追加されることはありません。 つまり、トポロジを有効にするには、既定でドメイン管理者である必要があることを意味します。 トポロジを有効にする権利を RTCUniversalServerAdmins グループのメンバーに付与するには、グラント Setuppermissions コマンドレットを実行する必要があります。 さらに、Lync Server を実行しているコンピューターを格納する各 Active Directory コンテナーに対して、このコマンドレットを実行する必要があります。

このコマンドレットは、RTCUniversalServerAdmins グループに対してのみアクセス許可を付与することに注意してください。コマンドレットを使用して、他のセキュリティグループまたは個々のユーザーに権限を付与することはできません。

<div>


> [!NOTE]  
> <STRONG>Enable-CsTopology</STRONG>は、RTCUniversalServerAdmins group メンバーが Lync Server 2013 をセットアップして展開できるようにするためのキーコマンドレットです。



</div>

<div>

## <a name="to-add-the-ability-to-run-enable-cstopology-to-the-rtcuniversalserveradmins-group"></a>Enable-CsTopology ツールを実行する機能を RTCUniversalServerAdmins グループに追加するには

1.  委任されたユーザーが実行**可能な**ドメインの domain Admins グループのメンバーとしてサーバーにログオンします。

2.  Lync Server 2013 管理シェルを開きます。 Lync Server 2013 管理シェルは、各フロントエンドサーバーまたは Lync Server 2013 管理ツールがインストールされているすべてのコンピューターに自動的にインストールされます。 Lync Server 2013 管理シェルの詳細については、「運用ドキュメントの[Lync server 2013 管理シェル](lync-server-2013-lync-server-management-shell.md)」を参照してください。

3.  Lync Server 2013 管理シェルから次のコマンドレットを実行します。
    
        Grant-CsSetupPermission -ComputerOU <DN of the OU> -Domain <Domain FQDN>
    
    <div>
    

    > [!NOTE]  
    > OU が最上位レベルではない場合は、完全なドメイン名を指定する必要があります。

    
    </div>
    
    次の例では、OU は contoso.com ドメイン内の "Lync Servers" です。
    
        Grant-CsSetupPermission -ComputerOU "OU=Lync Servers" -Domain contoso.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

