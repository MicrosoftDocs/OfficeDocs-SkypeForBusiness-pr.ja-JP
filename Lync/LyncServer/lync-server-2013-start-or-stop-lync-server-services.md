---
title: 'Lync Server 2013: Lync Server サービスを開始または停止する'
description: 'Lync Server 2013: Lync Server サービスを開始または停止します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Start or stop Lync Server 2013 services
ms:assetid: 1c70b4ec-9de5-4f7a-a3c9-c0eb76710505
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520958(v=OCS.15)
ms:contentKeyID: 48183554
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d6e6520cbf6fda38676beab984c2d006061b019
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48541863"
---
# <a name="start-or-stop-lync-server-2013-services"></a>Lync Server 2013 サービスを開始または停止する

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-02-05_

Lync Server コントロールパネルを使用して、特定のコンピューターで実行されているすべての Lync Server 2013 サービスを開始または停止したり、特定のサービスを開始または停止したりすることができます。

<div>

## <a name="to-start-or-stop-all-lync-server-services-on-a-computer"></a>コンピューター上のすべての Lync Server サービスを開始または停止するには

1.  RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウント、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、Lync Server 2013 を展開したネットワーク内の任意のコンピューターにログオンします。 CsServerAdministrator または CsAdministrator の RBAC の役割が割り当てられているかどうかは、次のようなコマンドを実行することで確認できます。
    
        Get-CsAdminRoleAssignment -Identity "kenmyer"

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**トポロジ**] をクリックし、[**状態**] をクリックします。

4.  [**状態**] ページで、必要に応じてリストを並べ替えるかまたは検索して、開始または停止するサービスを実行しているコンピューターを見つけ、クリックします。

5.  [**アクション**] をクリックします。

6.  [**すべてのサービスの開始**] または [**すべてのサービスの停止**] をクリックします。

</div>

<div>

## <a name="to-start-or-stop-a-specific-service"></a>特定のサービスを開始または停止するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**トポロジ**] をクリックし、[**状態**] をクリックします。

4.  [**状態**] ページで、必要に応じて一覧を並べ替えるかまたは検索して、開始または停止するサービスを実行しているコンピューターを確認してクリックします。

5.  [**プロパティ**] をクリックします。

6.  必要に応じて、サービスのリストを並べ替え、開始または停止するサービスをクリックします。

7.  [**アクション**] をクリックします。

8.  [**サービスの開始**] または [**サービスの停止**] をクリックします。

9.  [**閉じる**] をクリックします。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのサービスのセッションを禁止する](lync-server-2013-prevent-sessions-for-services.md)  


[Lync Server 2013 トポロジの管理](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

