---
title: 'Lync Server 2013: 既存のネットワーク地域ルートの削除'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting existing network region routes
ms:assetid: 6256ff80-5f1e-48b4-928b-24aeb3c1a0e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688074(v=OCS.15)
ms:contentKeyID: 49733669
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f07a0331563c4d78c4e8fc3391b7f8423a2ecc21
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525394"
---
# <a name="deleting-existing-network-region-routes-in-lync-server-2013"></a>Lync Server 2013 での既存のネットワーク地域ルートの削除

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-11-01_

通話受付管理 (CAC) 構成内のすべての地域には、他のすべての地域へのアクセス方法がいくつかある必要があります。 地域のリンクが地域間の接続に対する帯域幅制限を設定し、物理リンクも表す一方、ルートはある地域から別の地域へ接続が通過するリンクされたパスを決定します。 Lync Server コントロールパネルを使用して、ネットワーク地域ルートを構成できます。 Lync Server コントロールパネルから、ネットワーク地域ルートを作成、変更、または削除することができます。 このトピックを使用して、既存のネットワーク地域ルートを削除できます。 ネットワーク地域ルートの作成または変更の詳細については、「 [Lync Server 2013 でのネットワーク地域ルートの作成または変更](lync-server-2013-creating-or-modifying-network-region-routes.md)」を参照してください。

<div>

## <a name="to-delete-a-network-region-route"></a>ネットワーク地域ルートを削除するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**ネットワーク構成**] をクリックし、[**地域ルート**] をクリックします。

4.  [**地域ルート**] ページで、削除する地域ルートをクリックします。
    
    <div>
    

    > [!NOTE]  
    > 1 つ以上の地域ルートを一度に削除できます。これを実行するには、Ctrl キーを押しながら、複数のルートを選択します。また、すべての地域ルートを選択するには、[<STRONG>編集</STRONG>] メニューの [<STRONG>すべて選択</STRONG>] をクリックします。

    
    </div>

5.  [**編集**] メニューの [**削除**] をクリックします。

6.  [**OK**] をクリックします。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのネットワーク地域ルートの作成または変更](lync-server-2013-creating-or-modifying-network-region-routes.md)  


[ネットワーク地域ルートの構成](https://technet.microsoft.com/library/gg133706\(v=ocs.15\))  


[新しい-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)  
[設定-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute)  
[-CsNetworkInterRegionRoute の削除](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  
[Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

