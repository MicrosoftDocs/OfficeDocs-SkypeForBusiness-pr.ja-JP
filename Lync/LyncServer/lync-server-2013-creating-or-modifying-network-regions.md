---
title: 'Lync Server 2013: ネットワーク領域の作成または変更'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying network regions
ms:assetid: bd08bb66-5976-4ece-b45c-7de19569f814
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182579(v=OCS.15)
ms:contentKeyID: 48185266
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fbebccd02b74c4fbfb69225a6397c1dd7cef862d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756281"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-network-regions-in-lync-server-2013"></a>Lync Server 2013 でのネットワーク領域の作成または変更

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-11-01_

ネットワーク領域は、ネットワークのさまざまな部分を複数の地域で相互接続します。 すべてのネットワーク領域はセントラルサイトと関連付けられている必要があります。 セントラルサイトは、通話受付制御 (CAC) 帯域幅ポリシーサービスが実行されているデータセンターサイトです。 Lync Server コントロールパネルを使用して、ネットワークの領域を構成することができます。 [ネットワーク] 領域には、インターネット経由の代替パスが音声とビデオに接続できるかどうかを決定する設定が含まれます。 Lync Server コントロールパネルから、ネットワークの領域を作成、変更、または削除することができます。 このトピックは、ネットワーク領域の作成と変更に使用します。 既存のネットワーク領域の削除の詳細については、「 [Lync Server 2013 で既存のネットワーク領域を削除](lync-server-2013-deleting-existing-network-regions.md)する」を参照してください。

<div>

## <a name="to-create-a-network-region"></a>ネットワークの領域を作成するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**地域**] をクリックします。

4.  [**領域**] ページで、[**新規**] をクリックします。

5.  [**新しい領域**] ページで、[**名前**] フィールドに値を入力します。 この値は、Microsoft Lync Server 2013 の展開内で一意である必要があります。

6.  [**セントラルサイト**] ドロップダウンリストから、このネットワーク領域のセントラルサイトを選びます。

7.  [**オーディオ代替パスを有効にする**] チェックボックスは、既定でオンになっています。 このフィールドは、十分な帯域幅がプライマリパスに存在しない場合に、代替パスを介して音声通話をルーティングするかどうかを決定します。 オフロードをインターネットにオフにする必要がある場合にのみ、このチェックボックスをオフにします。 いずれかの通話がインターネット通話の場合は、帯域幅の設定に関係なく、このチェックボックスをオンにする必要があります。

8.  [**ビデオの代替パスを有効にする**] チェックボックスは、既定でオンになっています。 このフィールドは、ビデオ通話が、プライマリパスに十分な帯域幅が存在しない場合に、代替パスを使用してビデオ通話をルーティングするかどうかを決定します。 オフロードをインターネットにオフにする必要がある場合にのみ、このチェックボックスをオフにします。 いずれかの通話がインターネット通話の場合は、帯域幅の設定に関係なく、このチェックボックスをオンにする必要があります。

9.  省略[**説明**] フィールドに値を入力して、この領域について、名前だけでは表現できない詳細情報を入力します。

10. [**コミット**] をクリックします。

**関連付けら**れたサイトテーブルは、ネットワーク領域の作成には使用されません。 サイトを作成または変更するときに、サイトを地域に関連付けます。 詳細について[は、「Lync Server 2013 でネットワークサイトを作成または変更する](lync-server-2013-creating-or-modifying-network-sites.md)」を参照してください。

</div>

<div>

## <a name="to-modify-a-network-region"></a>ネットワークの領域を変更するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**地域**] をクリックします。

4.  [**領域**] ページで、変更する領域をクリックします。

5.  [**編集**] メニューの [**詳細の表示**] をクリックします。

6.  [**領域の編集**] ページで、オーディオおよびビデオの代替パスを有効または無効にする設定を変更したり、説明を変更したりすることができます (詳細については、このトピックの「ネットワーク領域を作成する」セクションを参照してください)。

7.  [**コミット**] をクリックします。

このページでは、**関連付けられたサイト**を変更することはできません。 関連付けられたサイトの一覧は参照用に提供されるため、地域設定を変更したときに影響を受けるサイトがわかります。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 で既存のネットワーク領域を削除する](lync-server-2013-deleting-existing-network-regions.md)  
[Lync Server 2013 での CAC のネットワーク領域の構成](lync-server-2013-configure-network-regions-for-cac.md)  


[新しい CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)  
[Set-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)  
[CsNetworkRegion の削除](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)  
[Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

