---
title: 'Lync Server 2013: ネットワークの領域を作成または変更する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a network region
ms:assetid: bf7a3dc4-71a2-4559-a547-d90305d4f904
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412933(v=OCS.15)
ms:contentKeyID: 48185281
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21a9b7a8adbb4ca4c0853aa7013662433701201d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833795"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-network-region-in-lync-server-2013"></a>Lync Server 2013 でネットワークの領域を作成または変更する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-19_

*ネットワーク領域*とは、通話受付制御、E9-1、メディアバイパスの構成で使用されるネットワークハブまたはバックボーンのことです。 ネットワーク領域を作成または変更するには、次の手順を使用します。 たとえば、1つの音声機能のネットワーク領域を既に作成している場合は、新しいネットワークの領域を作成する必要はありません。その他の高度なエンタープライズ Voip 機能でも、同じネットワーク領域が使用されます。 ただし、機能固有の設定を適用するために、ネットワーク地域に関する既存の定義に変更を加える必要が生じることがあります。 たとえば、E9-1-1 用のネットワーク地域を作成し (この場合は関連付けられた中央サイトは必要ありません)、次に通話受付管理を展開する場合は、中央サイトを指定するためにネットワーク地域の定義を変更する必要があります。 詳細については、「 [Lync Server 2013 で CAC のネットワーク領域を構成する](lync-server-2013-configure-network-regions-for-cac.md)」を参照してください。

<div>


> [!NOTE]  
> ネットワーク領域定義の機能固有の要件については、この機能の展開に関するトピックで説明されています。



</div>

ネットワーク領域の操作の詳細については、次のコマンドレットの Lync Server 管理シェルに関するドキュメントを参照してください。

  - [新しい CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)

  - [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)

  - [Set-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)

  - [CsNetworkRegion の削除](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)

<div>

## <a name="create-a-network-region"></a>ネットワークの領域を作成する

通話受付制御、E9、またはメディアバイパスで使用できるネットワーク領域を作成します。

<div>

## <a name="to-create-a-network-region-using-lync-server-management-shell"></a>Lync Server Management Shell を使用してネットワークの領域を作成するには

1.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

2.  New-CsNetworkRegion コマンドレットを実行してネットワーク地域を作成します。
    
        New-CsNetworkRegion -Identity <String> -CentralSite <String>
    
    次に例を示します。
    
        New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"
    
    この例では、サイト ID が CHICAGO の中央サイトに関連付けられた "NorthAmerica" というネットワーク地域を作成しました。

3.  トポロジでのネットワーク地域の作成を完了するには、ネットワーク地域ごとの設定値を使用してステップ 2 を繰り返します。

</div>

<div>

## <a name="to-create-a-network-region-using-lync-server-control-panel"></a>Lync Server コントロールパネルを使ってネットワークの領域を作成するには

1.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

2.  左側のナビゲーション バーで [**ネットワーク構成**] をクリックします。

3.  [**地域**] をクリックします。

4.  [**新規**] をクリックします。

5.  [**新しい地域**] ページで、[**名前**] をクリックしてネットワーク地域の名前を入力します。

6.  [**中央サイト**] をクリックし、リストにある中央サイトを 1 つクリックします。

7.  オプションで、[**説明**] をクリックして、このネットワーク サイトを説明する追加情報を入力します。

8.  [**コミット**] をクリックします。

9.  トポロジでのネットワーク地域の作成を完了するには、その他の地域の設定値を使用してステップ 4 ～ 8 を繰り返します。

</div>

</div>

<div>

## <a name="modify-a-network-region"></a>ネットワークの領域を変更する

既存のネットワーク領域の設定を変更して、新しい機能によって必要とされる基本領域の情報や変更に対応します。

<div>

## <a name="to-modify-a-network-region-using-lync-server-management-shell"></a>Lync Server 管理シェルを使用してネットワークの領域を変更するには

1.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

2.  Set-CsNetworkRegion コマンドレットを実行して、既存のネットワーク地域を変更します。
    
        Set-CsNetworkRegion -Identity <String> -CentralSite <String>
    
    例:
    
        Set-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "North American Region"
    
    この例では、説明を変更することにより、(このトピックの前半で説明した手順を使用して作成した) "NorthAmerica" という既存のネットワーク地域に変更を加えました。"NorthAmerica" 地域の説明があった場合、このコマンドはここでの値で地域の説明を上書きします。説明が設定されていない場合、このコマンドは説明を設定します。

3.  その他のネットワーク地域を変更するには、その他の地域の設定値を使用してステップ 2 を繰り返します。

</div>

<div>

## <a name="to-modify-a-network-region-using-lync-server-control-panel"></a>Lync Server コントロールパネルを使用してネットワークの領域を変更するには

1.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

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

