---
title: Lync Server 2013;ネットワーク地域間ルートを作成する
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: admin
manager: serdars
f1.keywords:
- NOCSH
TOCTitle: Create network interregion routes
ms:assetid: 5555262a-a502-4b01-9593-836dd30064f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398368(v=OCS.15)
ms:contentKeyID: 48184159
ms.date: 07/23/2014
mtps_version: v=OCS.15
ms.openlocfilehash: 156f2322d5b1b7cc1951f1cbd4df41eb231a8170
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757208"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-network-interregion-routes-in-lync-server-2013"></a>Lync Server 2013 でのネットワーク地域間ルートの作成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-20_

A *network interregion route* defines the route between a pair of network regions. Each pair of network regions in your call admission control deployment requires a network interregion route. This enables every network region within the deployment to access every other region.

地域のリンクが地域間の接続に対する帯域幅制限を設定し、地域間ルートはある地域から別の地域へ接続が通過するリンクされたパスを決定します。

ネットワーク地域間ルートの使用の詳細については、以下のコマンドレットの Lync Server Management Shell のドキュメントを参照してください。

  - [新しい-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)

  - [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)

  - [設定-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute)

  - [-CsNetworkInterRegionRoute の削除](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)

トポロジの例では、北アメリカ/EMEA、EMEA/APAC、および北アメリカ/APAC の 3 つの各地域ペアにネットワーク地域間ルートを定義する必要があります。

<div>

## <a name="to-create-network-interregion-routes-by-using-lync-server-management-shell"></a>Lync Server 管理シェルを使用してネットワーク地域間ルートを作成するには

1.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

2.  **New-CsNetworkInterRegionRoute** コマンドレットを実行して、必要なルートを定義します。 たとえば、以下を実行します。
    
       ```PowerShell
        New-CsNetworkInterRegionRoute -Identity NorthAmerica_EMEA_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -NetworkRegionLinkIDs "NA-EMEA-LINK"
       ```
    
       ```PowerShell
        New-CsNetworkInterRegionRoute -Identity NorthAmerica_APAC_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 APAC -NetworkRegionLinkIDs "NA-EMEA-LINK, EMEA-APAC-LINK"
       ```
    
       ```PowerShell
        New-CsNetworkInterRegionRoute -Identity EMEA_APAC_Route -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -NetworkRegionLinkIDs "EMEA-APAC-LINK"
       ```
    
    <div class=" ">
    

    > [!NOTE]  
    > 北アメリカ/APAC 間には直接のネットワーク地域リンクがないため、このネットワーク地域間ルートには 2 つのネットワーク地域リンクが必要です。

    
    </div>

</div>

<div>

## <a name="to-create-network-interregion-routes-by-using-lync-server-control-panel"></a>Lync Server コントロールパネルを使用してネットワーク地域間ルートを作成するには

1.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

2.  左側のナビゲーション バーで [**ネットワーク構成**] をクリックします。

3.  [**地域ルート**] ナビゲーション ボタンをクリックします。

4.  [**新規**] をクリックします。

5.  [**新しい地域ルート**] ページで、[**名前**] をクリックし、ネットワーク地域間ルートの名前を入力します。

6.  [**ネットワーク地域 \# 1**] をクリックし、一覧でネットワーク地域2にルーティングするネットワーク地域をクリックし \# ます。

7.  [**ネットワーク地域 \# 2**] をクリックし、一覧でネットワーク地域1にルーティングするネットワーク地域をクリックし \# ます。

8.  [**ネットワーク地域リンク**] フィールドの横の [**追加**] をクリックし、ネットワーク地域間ルートで使用するネットワーク地域リンクを追加します。
    
    <div class=" ">
    

    > [!NOTE]  
    > If you are creating a route for two network regions that do not have a direct network region link between them, you must add all the necessary links to complete the route. For example, the North America/APAC network interregion route requires two network region links because there is no direct network region link between them.

    
    </div>

9.  [**確定**] をクリックします。

10. トポロジのネットワーク地域間ルートを作成するには、他のネットワーク地域間ルートに関してステップ 4 ～ 9 を繰り返します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

