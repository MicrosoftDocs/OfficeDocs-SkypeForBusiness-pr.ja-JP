---
title: 'Lync Server 2013: 場所に基づくルーティングを有効にする'
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
ms.openlocfilehash: 4f36d28ca41bb12aa98bab5add471e102ed282b0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42155039"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enabling-location-based-routing-in-lync-server-2013"></a>Lync Server 2013 での場所に基づくルーティングの有効化

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-04-26_

エンタープライズ Voip を展開し、ネットワーク地域、サイト、およびサブネットを定義すると、場所に基づくルーティングを有効にすることができます。 次のエンタープライズ Voip 要素に対して、場所に基づくルーティングを有効にする必要があります。

  - ネットワークサイト

  - トランク構成

  - 音声ポリシー

  - ルーティング構成

<div>

## <a name="enable-location-based-routing-to-network-sites"></a>ネットワークサイトへの場所に基づくルーティングを有効にする

エンタープライズ Voip を展開し、ネットワークサイトを構成したら、場所に基づくルーティングを構成できます。 最初に、音声ルーティングポリシーを作成して、ネットワークサイトを適切な PSTN 使用法に関連付けます。 音声ルーティングポリシーに PSTN 使用法を割り当てる場合は、サイトのローカルにある PSTN ゲートウェイ、または場所に基づくルーティング制限が不要な地域内の PSTN ゲートウェイを使用する音声ルートに関連付けられている PSTN 使用法のみを使用してください。音声ルーティングポリシーを作成するには、Lync Server の Windows PowerShell コマンド、Grant-csvoiceroutingpolicy、または Lync Server コントロールパネルを使用します。

    New-CsVoiceRoutingPolicy -Identity <voice routing policy ID> -Name <voice routing policy name> -PstnUsages <usages>

詳細については、「 [grant-csvoiceroutingpolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoiceRoutingPolicy)」を参照してください。

この例では、次の表および Windows PowerShell コマンドは、このシナリオで定義されている2つの音声ルーティングポリシーと、それらに関連付けられた PSTN 使用法を示しています。 説明のため、表には場所に基づいたルーティングに固有の設定のみが含まれています。

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
<th>音声ルーティングポリシー1</th>
<th>音声ルーティングポリシー2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>音声ポリシー ID</p></td>
<td><p>ニューデリー音声ルーティングポリシー</p></td>
<td><p>Hyderabad 音声ルーティングポリシー</p></td>
</tr>
<tr class="even">
<td><p>PSTN 使用法</p></td>
<td><p>ニューデリー使用法、PBX Del usage、PBX Hyd usage</p></td>
<td><p>Hyderabad usage、PBX Hyd usage、PBX Del usage</p></td>
</tr>
</tbody>
</table>

  

次に、該当するネットワークサイトの場所に基づくルーティングを構成し、音声ルーティングポリシーを関連付けます。 Lync Server Windows PowerShell コマンドの New-CsNetworkSite を使用して、場所に基づくルーティングを有効にし、ルーティングの制限を適用する必要があるネットワークサイトに音声ルーティングポリシーを関連付けます。

    Set-CsNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false> -VoiceRoutingPolicy <voice routing policy ID>

この例では、次の表に、Lync Server Windows PowerShell を使用して、このシナリオで定義されている2つの異なるネットワークサイト、ニューデリー、Hyderabad の場所に基づくルーティングを示します。 説明のため、表には場所に基づいたルーティングに固有の設定のみが含まれています。

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
<td><p>Site Name</p></td>
<td><p>サイト 1 (ニューデリー)</p></td>
<td><p>サイト 2 (Hyderabad)</p></td>
</tr>
<tr class="even">
<td><p>Enablelocationのルーティング</p></td>
<td><p>True</p></td>
<td><p>True</p></td>
</tr>
<tr class="odd">
<td><p>音声ルーティングポリシー</p></td>
<td><p>ニューデリー音声ルーティングポリシー</p></td>
<td><p>Hyderabad 音声ルーティングポリシー</p></td>
</tr>
<tr class="even">
<td><p>サブネット</p></td>
<td><p>サブネット 1 (ニューデリー)</p></td>
<td><p>サブネット 2 (Hyderabad)</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-trunks"></a>トランクへの場所に基づくルーティングを有効にする

場所に基づくルーティングに対してトランク構成を有効にするには、トランクまたはネットワークサイトごとにトランク構成を作成する必要があります。 Lync Server Windows PowerShell コマンド Get-cstrunkconfiguration を使用して、トランク構成を作成します。 特定のシステム (ゲートウェイまたは PBX) に複数のトランクが関連付けられている場合は、場所に基づいたルーティング制限を有効にするために、各トランク構成を変更する必要があります。

    New-CsTrunkConfiguration -Identity < trunk configuration ID>

詳細については、「 [get-cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration)」を参照してください。

この例では、次の Windows PowerShell コマンドは、このシナリオで定義された展開内の各トランクに対して1つのトランク構成を作成する方法を示しています。

    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 1 DEL-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 2 HYD-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 3 DEL-PBX>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 4 HYD-PBX>"

トランクごとにトランク構成を構成したら、Lync Server Windows PowerShell コマンド Get-cstrunkconfiguration を使用して、ルーティング制限を強制する必要があるトランクへの場所ベースのルーティングを有効にすることができます。 PSTN への通話をルーティングする PSTN ゲートウェイへの通話をルーティングするトランクへの場所ベースのルーティングを有効にし、ゲートウェイが配置されているネットワークサイトを関連付けます。

    Set-CsTrunkConfiguration -Identity <trunk configuration ID> -EnableLocationRestriction $true -NetworkSiteID <site ID>

詳細については、「 [get-cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration)」を参照してください。

この例では、Hyderabad の PSTN ゲートウェイに関連付けられている各トランクに対して、場所に基づくルーティングが有効になっています。

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 1 DEL-GW -EnableLocationRestriction $true -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 2 HYD-GW -EnableLocationRestriction $true -NetworkSiteID "Hyderabad"

  

PSTN に通話をルーティングしないトランクの場所に基づくルーティングを有効にしないでください。ただし、このトランクを介して接続されたエンドポイントに到着する PSTN 通話には、場所に基づいたルーティング制限として、システムが配置されているネットワークサイトにトランクを関連付ける必要があります。 この例では、Hyderabad の PBX システムに関連付けられている各トランクに対して、場所に基づくルーティングが有効になっていません。

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 3 DEL-PBX -EnableLocationRestriction $false -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 4 HYD-PBX -EnableLocationRestriction $false -NetworkSiteID "Hyderabad"

  
PSTN (つまり PBX) への通話をルーティングしないシステムに接続されているエンドポイントは、場所に基づくルーティングが有効になっているユーザーの Lync エンドポイントと同様の制限を持ちます。 これは、ユーザーの場所に関係なく、Lync ユーザーとの間で通話を発信および受信できることを意味します。 また、システムが関連付けられているネットワークサイトに関係なく、PSTN ネットワークへの通話のルーティングを行わない他のシステム (つまり、別の PBX に接続されているエンドポイント) との間で受信通話を行うことができます。 PSTN エンドポイントを使用した着信呼び出し、発信通話、着信転送、および通話転送は、場所に基づいたルーティング強制の対象となります。 このような呼び出しでは、そのようなシステムのローカルとして定義されている PSTN ゲートウェイのみを使用する必要があります。

次の表は、2つの異なるネットワークサイトにある4つのトランクのトランク構成を示しています。2つは PSTN ゲートウェイに接続され、2台は PBX システムに接続されています。


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
<td><p>PstnGateway: トランク 1 DEL-GW</p></td>
<td><p>はい</p></td>
<td><p>サイト 1 (ニューデリー)</p></td>
</tr>
<tr class="even">
<td><p>PstnGateway: トランク 2 HYD</p></td>
<td><p>はい</p></td>
<td><p>サイト 2 (Hyderabad)</p></td>
</tr>
<tr class="odd">
<td><p>PstnGateway: トランク 3 DEL-PBX</p></td>
<td><p>False</p></td>
<td><p>サイト 1 (ニューデリー)</p></td>
</tr>
<tr class="even">
<td><p>PstnGateway: トランク 4 HYD-PBX</p></td>
<td><p>False</p></td>
<td><p>サイト 2 (Hyderabad)</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-voice-policies"></a>音声ポリシーへの場所に基づくルーティングを有効にする

特定のユーザーに対する場所ベースのルーティングを強制するには、そのユーザーの音声ポリシーを構成して PSTN の有料電話をバイパスします。 Lync Server Windows PowerShell コマンド Set-csvoicepolicy を使用して、新しい音声ポリシーを作成するか、既存のポリシーを使用している場合は Set-csvoicepolicy を使用して、PSTN の有料電話のバイパスを防ぐことで、場所に基づくルーティングを有効にします。

    Set-CsVoicePolicy -Identity <voice policy ID> -PreventPSTNTollBypass <$true|$false>

詳細については、「 [set-csvoicepolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoicePolicy)」を参照してください。

この例では、次の表および Windows PowerShell コマンドを使用して、このシナリオで定義されている、ニューデリーおよび Hyderabad の音声ポリシーに対する PSTN 通話のバイパスの防止を有効にしています。 説明のため、表には場所に基づいたルーティングに固有の設定のみが含まれています。

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
<th>音声ポリシー1</th>
<th>音声ポリシー2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>音声ポリシー ID</p></td>
<td><p>ニューデリー音声ポリシー</p></td>
<td><p>Hyderabad 音声ポリシー</p></td>
</tr>
<tr class="even">
<td><p>PSTN 使用法</p></td>
<td><p>ニューデリー使用法、PBX Del usage、PBX Hyd usage</p></td>
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

## <a name="enable-location-based-routing-in-the-routing-configuration"></a>ルーティング構成での場所に基づくルーティングを有効にする

最後に、ルーティング構成への場所ベースのルーティングをグローバルに有効にします。 Lync Server Windows PowerShell コマンドの [新規-CsRoutingConfiguration] を使用して、場所に基づくルーティングを有効にします。

    Set-CsRoutingConfiguration -EnableLocationBasedRouting $true

詳細については、「 [Set-CsRoutingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsRoutingConfiguration)」を参照してください。

<div>


> [!NOTE]  
> 場所に基づくルーティングはグローバル構成を使用して有効にする必要がありますが、適用されるルールのセットは、このドキュメントで指定されたとおりに構成されているサイト、ユーザー、およびトランクに対してのみ適用されます。



</div>

<div>


</div>

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での場所に基づくルーティングの構成](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

