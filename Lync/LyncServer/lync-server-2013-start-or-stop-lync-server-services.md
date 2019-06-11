---
title: 'Lync Server 2013: Lync Server サービスを開始または停止する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Start or stop Lync Server 2013 services
ms:assetid: 1c70b4ec-9de5-4f7a-a3c9-c0eb76710505
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520958(v=OCS.15)
ms:contentKeyID: 48183554
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a44e0725aa622b061acc936606bdf2941050952
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848663"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="start-or-stop-lync-server-2013-services"></a>Lync Server 2013 サービスを開始または停止する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-02-05_

Lync Server コントロールパネルを使用すると、特定のコンピューターで実行されているすべての Lync Server 2013 サービスを開始または停止したり、特定のサービスを開始または停止することができます。

<div>

## <a name="to-start-or-stop-all-lync-server-services-on-a-computer"></a>コンピューター上のすべての Lync Server サービスを開始または停止するには

1.  RTCUniversalServerAdmins グループのメンバーであるか (または同等のユーザー権限を持っている)、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザーアカウントで、Lync Server 2013 を展開したネットワーク上のコンピューターにログオンします。 次のようなコマンドを実行すると、CsServerAdministrator または CsAdministrator の RBAC 役割が割り当てられているかどうかを確認できます。
    
        Get-CsAdminRoleAssignment -Identity "kenmyer"

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーションバーで、[**トポロジ**] をクリックし、[**状態**] をクリックします。

4.  [**状態**] ページで、必要に応じて一覧を並べ替えて検索するか、開始または停止するサービスを実行しているコンピューターを検索して、それをクリックします。

5.  [**アクション**] をクリックします。

6.  [**すべてのサービスの開始**] または [**すべてのサービスの停止**] をクリックします。

</div>

<div>

## <a name="to-start-or-stop-a-specific-service"></a>特定のサービスを開始または停止するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーションバーで、[**トポロジ**] をクリックし、[**状態**] をクリックします。

4.  [**状態**] ページで、必要に応じて一覧を並べ替えます。または、開始または停止するサービスを実行しているコンピューターを検索して、それをクリックします。

5.  [**プロパティ**] をクリックします。

6.  必要に応じてサービスの一覧を並べ替え、開始または停止するサービスをクリックします。

7.  [**アクション**] をクリックします。

8.  [**サービスの開始**] または [**サービスの停止**] をクリックします。

9.  [**閉じる**] をクリックします。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でサービスのセッションを禁止する](lync-server-2013-prevent-sessions-for-services.md)  


[Lync Server 2013 トポロジの管理](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

