---
title: 'Lync Server 2013: 既存のネットワーク領域ルートの削除'
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
ms.openlocfilehash: e9f9ba7c20aff0bba3101edc9b04f3704314cfc8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763055"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-existing-network-region-routes-in-lync-server-2013"></a>Lync Server 2013 での既存のネットワーク領域ルートの削除

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-11-01_

通話受付制御 (CAC) 構成内のすべての領域は、他のすべての領域にアクセスするための何らかの手段を持っている必要があります。 地域のリンクでは、地域間の接続について帯域幅の制限を設定していますが、物理的なリンクも示しています。ルートによって、ある領域から別の領域に接続するリンク先のパスが決定されます。 Lync Server コントロールパネルを使用して、ネットワーク領域ルートを構成することができます。 Lync Server コントロールパネルでは、ネットワーク領域ルートの作成、変更、または削除を行うことができます。 このトピックを使用して、既存のネットワーク領域ルートを削除します。 ネットワーク領域ルートの作成または変更の詳細については、「 [Lync Server 2013 でネットワーク領域ルートを作成または変更する](lync-server-2013-creating-or-modifying-network-region-routes.md)」を参照してください。

<div>

## <a name="to-delete-a-network-region-route"></a>ネットワーク領域ルートを削除するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**地域ルート**] をクリックします。

4.  [**地域ルート**] ページで、削除する地域ルートをクリックします。
    
    <div>
    

    > [!NOTE]  
    > 複数の地域のルートを一度に削除できます。 これを行うには、ctrl キーを押しながら、CTRL キーを押しながら複数の領域ルートを選択します。 または、すべての地域ルートを選択するには、[<STRONG>編集</STRONG>] メニューの [<STRONG>すべて選択</STRONG>] をクリックします。

    
    </div>

5.  [**編集**] メニューの [**削除**] をクリックします。

6.  **[OK]** をクリックします。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのネットワーク領域ルートの作成または変更](lync-server-2013-creating-or-modifying-network-region-routes.md)  


[ネットワーク地域ルートの構成](https://technet.microsoft.com/en-us/library/gg133706\(v=ocs.15\))  


[新しい (CsNetworkInterRegionRoute)](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)  
[設定-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute)  
[CsNetworkInterRegionRoute の削除](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  
[Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

