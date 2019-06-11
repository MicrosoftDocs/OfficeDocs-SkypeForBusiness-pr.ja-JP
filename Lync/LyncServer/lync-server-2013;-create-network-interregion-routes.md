---
title: Lync Server 2013;ネットワーク間の領域ルートを作成する
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Create network interregion routes
ms:assetid: 5555262a-a502-4b01-9593-836dd30064f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398368(v=OCS.15)
ms:contentKeyID: 48184159
ms.date: 07/23/2014
mtps_version: v=OCS.15
ms.openlocfilehash: be1c28450708660e2322144802c81d5458ded6da
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "34821818"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-network-interregion-routes-in-lync-server-2013"></a>Lync Server 2013 でのネットワーク間通信領域ルートの作成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-20_

*ネットワークインター領域ルート*は、ネットワーク領域のペア間のルートを定義します。 通話受付制御の展開におけるネットワーク領域の各ペアには、ネットワークインター領域ルートが必要です。 これにより、展開内の各ネットワーク地域が他のすべての地域にアクセスできるようになります。

地域のリンクでは、領域間の接続に帯域幅の制限を設定していますが、相互領域ルートによって、接続が1つの領域から別の領域に移動するリンク先のパスが決定されます。

ネットワークインターセクションルートの操作の詳細については、次のコマンドレットの Lync Server 管理シェルに関するドキュメントを参照してください。

  - [新しい (CsNetworkInterRegionRoute)](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)

  - [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)

  - [設定-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute)

  - [CsNetworkInterRegionRoute の削除](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)

このトポロジの例では、北米、EMEA、EMEA、APAC、北米/APAC という3つの地域のペアのそれぞれに対して、ネットワークの interregion ルートを定義する必要があります。

<div>

## <a name="to-create-network-interregion-routes-by-using-lync-server-management-shell"></a>Lync Server 管理シェルを使用してネットワーク間の領域ルートを作成するには

1.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

2.  **New-CsNetworkInterRegionRoute** コマンドレットを実行して、必要なルートを定義します。 たとえば、以下を実行します。
    
       ```
        New-CsNetworkInterRegionRoute -Identity NorthAmerica_EMEA_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -NetworkRegionLinkIDs "NA-EMEA-LINK"
       ```
    
       ```
        New-CsNetworkInterRegionRoute -Identity NorthAmerica_APAC_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 APAC -NetworkRegionLinkIDs "NA-EMEA-LINK, EMEA-APAC-LINK"
       ```
    
       ```
        New-CsNetworkInterRegionRoute -Identity EMEA_APAC_Route -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -NetworkRegionLinkIDs "EMEA-APAC-LINK"
       ```
    
    <div class=" ">
    

    > [!NOTE]  
    > 北米/APAC ネットワーク interregion ルートには、ネットワーク領域間の直接リンクがないため、2つのネットワークリージョンリンクが必要です。

    
    </div>

</div>

<div>

## <a name="to-create-network-interregion-routes-by-using-lync-server-control-panel"></a>Lync Server コントロールパネルを使用してネットワーク間の領域ルートを作成するには

1.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

2.  左側のナビゲーション バーで [**ネットワーク構成**] をクリックします。

3.  [**地域ルート**] ナビゲーション ボタンをクリックします。

4.  [**新規**] をクリックします。

5.  [**新しい地域ルート**] ページで、[**名前**] をクリックし、ネットワークインターセクションルートの名前を入力します。

6.  [**ネットワーク領域\#1**] をクリックし、ネットワーク領域\#2 にルーティングするリスト内のネットワーク領域をクリックします。

7.  [**ネットワーク領域\#2**] をクリックし、ネットワーク領域\#1 にルーティングするリスト内のネットワーク領域をクリックします。

8.  [**ネットワークの領域リンク**] フィールドの横にある [**追加**] をクリックし、ネットワークのインターセクションルートで使用されるネットワーク領域のリンクを追加します。
    
    <div class=" ">
    

    > [!NOTE]  
    > 2 つのネットワーク地域のルートを作成する場合、その間に直接のネットワーク地域リンクがなければ、必要なすべてのリンクを追加してルートを完成させる必要があります。 たとえば、北米/APAC ネットワーク interregion ルートには、2つのネットワーク領域リンクが必要です。これには、その間にネットワークの直接リンクがありません。

    
    </div>

9.  [**コミット**] をクリックします。

10. トポロジのネットワークでのネットワーク間ルートの作成を完了するには、他のネットワークインターセクションルートの設定を使用して、手順4から9を繰り返します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

