---
title: 'Lync Server 2013: ネットワーク地域の作成または変更'
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
ms.openlocfilehash: 60e8a5309344a7d504cf958e29dc50a67d50ed29
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516734"
---
# <a name="creating-or-modifying-network-regions-in-lync-server-2013"></a>Lync Server 2013 でのネットワーク地域の作成または変更

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-11-01_

ネットワーク地域は、複数の地理的な領域にまたがるネットワークのさまざまな部分を相互接続します。 すべてのネットワーク地域は、セントラル サイトと関連付ける必要があります。 このセントラル サイトは、通話受付管理 (CAC) 帯域幅ポリシー サービスが実行されているデータ センター サイトです。 Lync Server コントロールパネルを使用して、ネットワーク地域を構成できます。 ネットワーク地域には、オーディオとビデオの接続でインターネット経由の代替パスを許可するかどうかを決定する設定が含まれます。 Lync Server コントロールパネルから、ネットワーク地域を作成、変更、または削除することができます。 ネットワーク地域を作成および変更するには、このトピックを参考にしてください。 既存のネットワーク領域の削除の詳細については、「 [Lync Server 2013 の既存のネットワーク地域の削除](lync-server-2013-deleting-existing-network-regions.md)」を参照してください。

<div>

## <a name="to-create-a-network-region"></a>ネットワーク地域を作成するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**ネットワーク構成**] をクリックし、[**地域**] をクリックします。

4.  [**地域**] ページで [**新規**] をクリックします。

5.  [**新しい地域**] ページで、[**名前**] フィールドに値を入力します。 この値は、Microsoft Lync Server 2013 展開内で一意である必要があります。

6.  [**セントラル サイト**] ドロップダウン リストで、このネットワーク地域に対応するセントラル サイトを選択します。

7.  既定では、[**オーディオ代替パスを有効にする**] チェック ボックスはオンになっています。このフィールドで、プライマリ パスに適当な帯域幅がない場合に音声通話を代替パスにルーティングするかどうかを設定します。インターネットへの負荷分散を無効する必要がある場合にのみ、このチェック ボックスをオフにします。いずれかの通話をインターネット通話にする場合は、帯域幅設定に関係なく、このチェック ボックスをオンにする必要があります。

8.  既定では、[**ビデオ代替パスを有効にする**] チェック ボックスはオンになっています。このフィールドで、プライマリ パスに適当な帯域幅がない場合にビデオ通話を代替パスにルーティングするかどうかを設定します。インターネットへの負荷分散を無効する必要がある場合にのみ、このチェック ボックスをオフにします。いずれかの通話をインターネット通話にする場合は、帯域幅設定に関係なく、このチェック ボックスをオンにする必要があります。

9.  (オプション) [**説明**] フィールドに値を入力して、名前だけでは表現できないこの地域に関する詳細を設定します。

10. [**コミット**] をクリックします。

[**関連付けられているサイト**] テーブルは、ネットワーク地域の作成では使用しません。 サイトを作成または変更するときに、サイトと地域を関連付けます。 詳細については、「 [Lync Server 2013 でのネットワークサイトの作成または変更](lync-server-2013-creating-or-modifying-network-sites.md)」を参照してください。

</div>

<div>

## <a name="to-modify-a-network-region"></a>ネットワーク地域を変更するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**ネットワーク構成**] をクリックし、[**地域**] をクリックします。

4.  [**地域**] ページで、変更する地域をクリックします。

5.  [**編集**] メニューの [**詳細の表示**] をクリックします。

6.  [**編集 地域**] ページで、オーディオとビデオの代替パスを有効または無効に切り替えたり、説明を変更したりできます。詳細については、このトピック前半の「ネットワーク地域を作成するには」のセクションを参照してください。

7.  [**コミット**] をクリックします。

このページでは [**関連付けられているサイト**] を変更できません。関連付けられているサイトの一覧は参考のために表示されています。これにより、地域設定を変更するとどのサイトが影響を受けるか確認することができます。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 の既存のネットワーク領域の削除](lync-server-2013-deleting-existing-network-regions.md)  
[Lync Server 2013 で CAC のネットワーク地域を構成する](lync-server-2013-configure-network-regions-for-cac.md)  


[新しい-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)  
[設定-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)  
[-CsNetworkRegion の削除](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)  
[取得-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

