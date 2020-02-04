---
title: 'Lync Server 2013: 位置情報に基づくルーティングを有効にする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling Location-Based Routing
ms:assetid: 029ede7e-0c4e-4ad2-af99-909ae674d6fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994014(v=OCS.15)
ms:contentKeyID: 51803920
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e21e1a285fa5b2129d4d0ed0b5d75e8dcee42f2f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735807"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-location-based-routing-in-lync-server-2013"></a>Lync Server 2013 で位置情報に基づくルーティングを有効にする

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-04-26_

エンタープライズ Voip を展開し、ネットワーク領域、サイト、サブネットを定義したら、位置ベースのルーティングを有効にすることができます。 次のエンタープライズボイス要素については、位置情報に基づくルーティングを有効にする必要があります。

  - ネットワークサイト

  - トランク構成

  - 音声ポリシー

  - ルーティング構成

<div>

## <a name="enable-location-based-routing-to-network-sites"></a>ネットワークサイトへの位置情報に基づくルーティングを有効にする

エンタープライズ Voip を展開し、ネットワークサイトを構成したら、位置ベースのルーティングを構成することができます。 まず、音声ルーティングポリシーを作成して、ネットワークサイトを適切な PSTN 使用法に関連付けます。 ボイスルーティングポリシーに PSTN の使用を割り当てる場合は、サイトに対するローカルの PSTN ゲートウェイを使用しているボイスルーティングに関連付けられている PSTN の使用のみを使用するようにしてください。また、位置情報に基づくルーティング制限が不要な地域にある PSTN ゲートウェイにも使用してください。Lync Server Windows PowerShell コマンド、新規-CsVoiceRoutingPolicy、または Lync Server コントロールパネルを使用して、ボイスルーティングポリシーを作成します。

    New-CsVoiceRoutingPolicy -Identity <voice routing policy ID> -Name <voice routing policy name> -PstnUsages <usages>

詳細については、「[New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoiceRoutingPolicy)」を参照してください。

この例では、次の表と Windows PowerShell コマンドは、このシナリオで定義された2つのボイスルーティングポリシーと関連する PSTN 使用法を示しています。 この表には、場所に基づくルーティングに固有の設定のみが含まれています。

    New-CsVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Name "Delhi voice routing policy" -PstnUsages @{add="Delhi usage", "PBX Del usage", "PBX Hyd usage"}
    New-CsVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Name " Hyderabad voice routing policy" -PstnUsages @{add="Hyderabad usage", "PBX Del usage", "PBX Hyd usage"}


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>ボイスルーティングポリシー1</th>
<th>ボイスルーティングポリシー2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ボイスポリシー ID</p></td>
<td><p>ニューデリーボイスルーティングポリシー</p></td>
<td><p>Hyderabad ボイスルーティングポリシー</p></td>
</tr>
<tr class="even">
<td><p>PSTN の使用状況</p></td>
<td><p>ニューデリー使用量, PBX Del usage, PBX Hyd usage</p></td>
<td><p>Hyderabad usage、PBX Hyd usage、PBX Del usage</p></td>
</tr>
</tbody>
</table>

  

次に、該当するネットワークサイトの位置情報に基づくルーティングを構成し、ボイスルーティングポリシーを関連付けます。 Lync Server Windows PowerShell コマンドの新しい CsNetworkSite を使って、位置情報に基づくルーティングを有効にし、ルーティングの制限を適用する必要があるネットワークサイトにボイスルーティングポリシーを関連付けます。

    Set-CsNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false> -VoiceRoutingPolicy <voice routing policy ID>

この例では、次の表は、Lync Server Windows PowerShell を使用して、このシナリオで定義される2つの異なるネットワークサイト、ニューデリー、Hyderabad の位置に基づくルーティングを示しています。 この表には、場所に基づくルーティングに固有の設定のみが含まれています。

    Set-CsNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true -VoiceRoutingPolicy "DelhiVoiceRoutingPolicy"
    Set-CsNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true -VoiceRoutingPolicy "HyderabadVoiceRoutingPolicy"


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>サイト 1 (ニューデリー)</th>
<th>サイト 2 (Hyderabad)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>サイト名</p></td>
<td><p>サイト 1 (ニューデリー)</p></td>
<td><p>サイト 2 (Hyderabad)</p></td>
</tr>
<tr class="even">
<td><p>Enablelocationrouting ルーティング</p></td>
<td><p>True</p></td>
<td><p>True</p></td>
</tr>
<tr class="odd">
<td><p>ボイスルーティングポリシー</p></td>
<td><p>ニューデリーボイスルーティングポリシー</p></td>
<td><p>Hyderabad ボイスルーティングポリシー</p></td>
</tr>
<tr class="even">
<td><p>サブネット</p></td>
<td><p>Subnet 1 (ニューデリー)</p></td>
<td><p>Subnet 2 (Hyderabad)</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-trunks"></a>Trunks への位置に基づくルーティングを有効にする

位置情報に基づくルーティングでトランク構成を有効にするには、各トランクまたは各ネットワークサイトのトランク構成を作成する必要があります。 Lync Server Windows PowerShell コマンドの New-Set-cstrunkconfiguration を使用して、トランク構成を作成します。 特定のシステム (ゲートウェイまたは PBX など) に複数の trunks が関連付けられている場合は、各トランク構成を変更して、位置ベースのルーティング制限を有効にする必要があります。

    New-CsTrunkConfiguration -Identity < trunk configuration ID>

詳細については、「 [New-set-cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration)」を参照してください。

この例では、次の Windows PowerShell コマンドを使用して、このシナリオで定義されている展開の各トランクに対してトランク構成を1つ作成しています。

    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 1 DEL-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 2 HYD-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 3 DEL-PBX>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 4 HYD-PBX>"

トランク構成がトランクごとに構成されると、Lync Server Windows PowerShell コマンドである Set-cstrunkconfiguration を使用して、ルーティングの制限を適用する必要がある trunks への位置情報に基づくルーティングを有効にすることができます。 PSTN への通話をルーティングする PSTN ゲートウェイへの通話をルーティングし、ゲートウェイが配置されているネットワークサイトを関連付ける trunks に、位置情報に基づくルーティングを有効にします。

    Set-CsTrunkConfiguration -Identity <trunk configuration ID> -EnableLocationRestriction $true -NetworkSiteID <site ID>

詳細については、「 [New-set-cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration)」を参照してください。

この例では、ニューデリーと Hyderabad の PSTN ゲートウェイに関連付けられている各トランクで位置情報に基づくルーティングが有効になっています。

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 1 DEL-GW -EnableLocationRestriction $true -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 2 HYD-GW -EnableLocationRestriction $true -NetworkSiteID "Hyderabad"

  

PSTN への通話をルーティングしない trunks の位置情報に基づくルーティングを有効にしないでください。ただし、このトランク経由で接続されているエンドポイントに対応する PSTN 通話には、場所に基づくルーティング制限が適用されている必要があります。 この例では、ニューデリーと Hyderabad の PBX システムに関連付けられている各トランクの位置情報に基づくルーティングが有効になっていません。

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 3 DEL-PBX -EnableLocationRestriction $false -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 4 HYD-PBX -EnableLocationRestriction $false -NetworkSiteID "Hyderabad"

  
PSTN (つまり PBX) への通話をルーティングしないシステムに接続されているエンドポイントは、場所に基づくルーティングが有効になっているユーザーの Lync エンドポイントと同様の制限があります。 これは、ユーザーの場所に関係なく、ユーザーが Lync ユーザーとの間で通話を発信および受信できることを意味します。 また、システムが関連付けられているネットワークサイトに関係なく、PSTN ネットワーク (つまり、別の PBX に接続されているエンドポイント) との間で着信を転送することができます。 PSTN エンドポイントを含むすべての着信通話、発信通話、通話転送、通話転送には、位置ベースのルーティング enforcements が適用されます。 このような呼び出しでは、そのようなシステムのローカルとして定義されている PSTN ゲートウェイのみを使用する必要があります。

次の表は、2つの異なるネットワークサイトでの4つの trunks のトランク構成を示しています。2つは PSTN ゲートウェイに接続され、2つは PBX システムに接続されています。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>名前</th>
<th>EnableLocationRestriction</th>
<th>NetworkSiteID</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PstnGateway: トランク1の DEL-GW</p></td>
<td><p>True</p></td>
<td><p>サイト 1 (ニューデリー)</p></td>
</tr>
<tr class="even">
<td><p>PstnGateway: トランク 2 HYD</p></td>
<td><p>True</p></td>
<td><p>サイト 2 (Hyderabad)</p></td>
</tr>
<tr class="odd">
<td><p>PstnGateway: トランク 3 DEL-PBX</p></td>
<td><p>False</p></td>
<td><p>サイト 1 (ニューデリー)</p></td>
</tr>
<tr class="even">
<td><p>PstnGateway: トランク 4 HYD</p></td>
<td><p>False</p></td>
<td><p>サイト 2 (Hyderabad)</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-voice-policies"></a>ボイスポリシーへの位置に基づくルーティングを有効にする

特定のユーザーに対して位置情報に基づくルーティングを適用するには、これらのユーザーの音声ポリシーを構成して、PSTN の有料通話を回避します。 Lync Server Windows PowerShell コマンドの CsVoicePolicy を使用して、新しい音声ポリシーを作成するか、既存のポリシーを使用する場合は CsVoicePolicy を使って、PSTN の有料電話のバイパスを防ぐことで位置情報に基づくルーティングを有効にします。

    Set-CsVoicePolicy -Identity <voice policy ID> -PreventPSTNTollBypass <$true|$false>

詳細については、「 [New-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoicePolicy)」を参照してください。

この例では、次の表と Windows PowerShell コマンドを使用して、このシナリオで定義された、ニューデリーと Hyderabad のボイスポリシーに PSTN 有料電話のバイパスを防ぐことを示します。 この表には、場所に基づくルーティングに固有の設定のみが含まれています。

    Set-CsVoicePolicy -Identity "Delhi voice policy" -PreventPSTNTollBypass $true
    Set-CsVoicePolicy -Identity "Hyderabad voice policy" -PreventPSTNTollBypass $true


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>ボイスポリシー1</th>
<th>ボイスポリシー2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ボイスポリシー ID</p></td>
<td><p>ニューデリーのボイスポリシー</p></td>
<td><p>Hyderabad ボイスポリシー</p></td>
</tr>
<tr class="even">
<td><p>PSTN の使用状況</p></td>
<td><p>ニューデリー使用量, PBX Del usage, PBX Hyd usage</p></td>
<td><p>Hyderabad usage、PBX Hyd usage、PBX Del usage</p></td>
</tr>
<tr class="odd">
<td><p>PreventPSTNTollBypass</p></td>
<td><p>True</p></td>
<td><p>True</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-in-the-routing-configuration"></a>ルーティング構成で位置情報に基づくルーティングを有効にする

最後に、ルーティング構成への位置に基づくルーティングをグローバルに有効にします。 Lync Server Windows PowerShell コマンドである [新しい-CsRoutingConfiguration] を使って、位置情報に基づくルーティングを有効にします。

    Set-CsRoutingConfiguration -EnableLocationBasedRouting $true

詳細については、「 [CsRoutingConfiguration を設定](https://docs.microsoft.com/powershell/module/skype/Set-CsRoutingConfiguration)する」を参照してください。

<div>


> [!NOTE]  
> 位置情報に基づくルーティングはグローバル構成を使用して有効にする必要がありますが、適用されるルールのセットは、このドキュメントで指定されているように構成されているサイト、ユーザー、および trunks に対してのみ適用されます。



</div>

<div>


</div>

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 の場所に基づくルーティングの構成](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

