---
title: 'Lync Server 2013: ネットワーク領域ルート情報の表示'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Viewing network region route information
ms:assetid: 34dd9fa3-e695-4680-b244-3019298b5009
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688021(v=OCS.15)
ms:contentKeyID: 49733611
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4438a3af4a9bfbdaf88d4412b769cdaaba9d3d43
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848166"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-network-region-route-information-in-lync-server-2013"></a>Lync Server 2013 でのネットワーク領域ルート情報の表示

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-23_

通話受付制御 (CAC) 構成内のすべての領域は、他のすべての領域にアクセスするための何らかの手段を持っている必要があります。 地域のリンクでは、地域間の接続について帯域幅の制限を設定していますが、物理的なリンクも示しています。ルートによって、ある領域から別の領域に接続するリンク先のパスが決定されます。 次の手順を使用して、Lync Server 2013 コントロールパネルまたは Lync Server 2013 管理シェルで既存のネットワーク領域ルートを表示します。 ネットワーク領域ルートの作成または変更の詳細については、「 [Lync Server 2013 でネットワーク領域ルートを作成または変更する](lync-server-2013-creating-or-modifying-network-region-routes.md)」を参照してください。

<div>

## <a name="to-view-network-region-route-information-in-lync-server-control-panel"></a>Lync Server コントロールパネルのネットワーク領域ルート情報を表示するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**地域ルート**] をクリックします。

4.  [**地域ルート**] ページで、表示する地域ルートをクリックします。
    
    <div>
    

    > [!NOTE]  
    > 表示できる地域ルートは一度に1つだけです。

    
    </div>

5.  [**編集**] メニューの [**詳細の表示**] をクリックします。

</div>

<div>

## <a name="viewing-network-region-route-information-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用したネットワーク領域ルート情報の表示

ネットワーク領域のルート情報を表示するには、Windows PowerShell を使用するか、または CsNetworkInterRegionRoute コマンドレットを使用します。 このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、「Lync Server Windows PowerShell のブログ記事」を参照してください[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。「リモート PowerShell を使用して Microsoft Lync Server 2010 を管理する」を参照してください。

<div>

## <a name="to-view-network-region-route-information"></a>ネットワーク領域ルート情報を表示するには

  - すべてのネットワーク領域のルートに関する情報を表示するには、Lync Server 管理シェルで次のコマンドを入力し、enter キーを押します。
    
        Get-CsNetworkInterRegionRoute
    
    次のような情報が表示されます。
    
        Identity                  : TransAmericaRoute
        NetworkRegionLinks        : {NorthwestToNortheast}
        InterNetworkRegionRouteID : TransAmericaRoute
        NetworkRegionID1          : Pacific Northwest
        NetworkRegionID2          : Northeast

</div>

詳細については、「 [CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)コマンドレット」のヘルプトピックを参照してください。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのネットワーク領域ルートの作成または変更](lync-server-2013-creating-or-modifying-network-region-routes.md)  
[Lync Server 2013 での既存のネットワーク領域ルートの削除](lync-server-2013-deleting-existing-network-region-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

