---
title: 'Lync Server 2013: ネットワーク地域を作成または変更する'
description: 'Lync Server 2013: ネットワーク地域を作成または変更します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a network region
ms:assetid: bf7a3dc4-71a2-4559-a547-d90305d4f904
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412933(v=OCS.15)
ms:contentKeyID: 48185281
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a149a668f64df804d2631243d9bb63401bd8a284
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562233"
---
# <a name="create-or-modify-a-network-region-in-lync-server-2013"></a>Lync Server 2013 でネットワーク地域を作成または変更する

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-19_

*ネットワーク地域* は、通話受付管理、E9-1-1、およびメディアバイパスの構成で使用されるネットワークハブまたはバックボーンです。 ネットワーク地域を作成または変更するには、以下の手順を使用します。 たとえば、1つの音声機能に対してネットワーク地域が既に作成されている場合、新しいネットワーク地域を作成する必要はありません。その他の高度なエンタープライズ Voip 機能でも同じネットワーク地域が使用されます。 ただし、機能固有の設定を適用するために、既存のネットワーク地域定義を変更することが必要になる場合があります。 たとえば、E9-1-1 用のネットワーク地域を作成していて、通話受付管理を展開する場合は、ネットワーク地域定義を変更して中央サイトを指定する必要があります。 詳細については、「 [Lync Server 2013 での CAC のネットワーク地域の構成](lync-server-2013-configure-network-regions-for-cac.md)」を参照してください。

<div>


> [!NOTE]  
> ネットワーク地域の定義で機能固有の要件については、すべてその機能の「展開」のトピックで説明されています。



</div>

ネットワーク地域の使用の詳細については、以下のコマンドレットの Lync Server Management Shell のドキュメントを参照してください。

  - [新しい-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)

  - [取得-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)

  - [設定-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)

  - [-CsNetworkRegion の削除](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)

<div>

## <a name="create-a-network-region"></a>ネットワーク地域の作成

通話受付管理、E9-1-1、またはメディア バイパスで使用できるネットワーク地域を作成します。

<div>

## <a name="to-create-a-network-region-using-lync-server-management-shell"></a>Lync Server 管理シェルを使用してネットワーク地域を作成するには

1.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

2.  New-CsNetworkRegion コマンドレットを実行してネットワーク地域を作成します。
    
        New-CsNetworkRegion -Identity <String> -CentralSite <String>
    
    次にその例を示します。
    
        New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"
    
    この例では、サイト ID が CHICAGO の中央サイトと関連付けられた "NorthAmerica" というネットワーク地域を作成しました。

3.  トポロジでのネットワーク地域の作成を完了するには、ネットワーク地域ごとの設定値を使用してステップ 2 を繰り返します。

</div>

<div>

## <a name="to-create-a-network-region-using-lync-server-control-panel"></a>Lync Server コントロールパネルを使用してネットワーク地域を作成するには

1.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

2.  左側のナビゲーション バーで [**ネットワーク構成**] をクリックします。

3.  [**地域**] をクリックします。

4.  [**新規**] をクリックします。

5.  [**新しい地域**] ページで、[**名前**] をクリックしてネットワーク地域の名前を入力します。

6.  [**中央サイト**] をクリックし、リストにある中央サイトを 1 つクリックします。

7.  オプションで、[**説明**] をクリックして、このネットワーク サイトを説明する追加情報を入力します。

8.  [**確定**] をクリックします。

9.  トポロジでのネットワーク地域の作成を完了するには、その他の地域の設定値を使用してステップ 4 ～ 8 を繰り返します。

</div>

</div>

<div>

## <a name="modify-a-network-region"></a>ネットワーク地域の変更

既存のネットワーク地域の設定を変更して、基本地域情報に対する変更、または新しい機能で必要な変更に対応します。

<div>

## <a name="to-modify-a-network-region-using-lync-server-management-shell"></a>Lync Server 管理シェルを使用してネットワーク地域を変更するには

1.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

2.  Set-CsNetworkRegion コマンドレットを実行して、既存のネットワーク地域を変更します。
    
        Set-CsNetworkRegion -Identity <String> -CentralSite <String>
    
    次にその例を示します。
    
        Set-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "North American Region"
    
    この例では、説明を変更することにより、(このトピックの前半で説明した手順を使用して作成した) "NorthAmerica" という既存のネットワーク地域に変更を加えました。 "NorthAmerica" 地域の説明があった場合、このコマンドはここでの値で地域の説明を上書きします。説明が設定されていない場合、このコマンドは説明を設定します。

3.  その他のネットワーク地域を変更するには、その他の地域の設定値を使用してステップ 2 を繰り返します。

</div>

<div>

## <a name="to-modify-a-network-region-using-lync-server-control-panel"></a>Lync Server コントロールパネルを使用してネットワーク地域を変更するには

1.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

2.  左側のナビゲーション バーで [**ネットワーク構成**] をクリックします。

3.  [**地域**] ナビゲーション ボタンをクリックします。

4.  表で、変更するネットワーク地域をクリックします。

5.  [**編集**] をクリックして、[**詳細の表示...**] をクリックします。

6.  [**地域の編集**] ページで、このネットワーク地域の設定の値を必要に応じて変更します。

7.  [**確定**] をクリックします。

8.  ネットワーク地域の変更を完了するには、他の地域の設定値を使用してステップ 4 ～ 7 を繰り返します。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

