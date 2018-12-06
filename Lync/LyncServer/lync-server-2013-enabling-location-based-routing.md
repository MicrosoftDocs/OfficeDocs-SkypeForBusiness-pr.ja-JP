---
title: Lync Server 2013 での場所に基づくルーティングの有効化
TOCTitle: Lync Server 2013 での場所に基づくルーティングの有効化
ms:assetid: 029ede7e-0c4e-4ad2-af99-909ae674d6fe
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ994014(v=OCS.15)
ms:contentKeyID: 52056527
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での場所に基づくルーティングの有効化

 

_**トピックの最終更新日:** 2015-03-09_

エンタープライズ VoIP を展開し、ネットワーク地域、サイト、サブネットを定義すると、場所に基づくルーティングを有効にすることができます。場所に基づくルーティングは、次のエンタープライズ VoIP 要素に対して有効にする必要があります。

  - ネットワーク サイト

  - トランク構成

  - 音声ポリシー

  - ルーティング構成

## ネットワーク サイトに対する場所に基づくルーティングの有効化

エンタープライズ VoIP を展開し、ネットワーク サイトを構成すると、場所に基づくルーティングを構成できるようになります。最初に、音声ルーティング ポリシーを作成して、ネットワーク サイトを適切な PSTN 使用法に関連付けます。音声ルーティング ポリシーに PSTN 使用法を割り当てる場合は、サイトに対してローカルである PSTN ゲートウェイまたは場所に基づくルーティングの制限が不要な地域にある PSTN ゲートウェイを使用する音声ルートに関連付けられている PSTN 使用法だけを使用してください。音声ルーティング ポリシーを作成するには、Lync ServerWindows PowerShell コマンドである New-CsVoiceRoutingPolicy または Lync Server コントロール パネルを使用します。

    New-CsVoiceRoutingPolicy -Identity <voice routing policy ID> -Name <voice routing policy name> -PstnUsages <usages>

詳細については、「[New-CsVoiceRoutingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsVoiceRoutingPolicy)」を参照してください。

この例では、このシナリオで定義されている 2 つの音声ルーティング ポリシーとそれらに関連付けられている PSTN 使用法を、次の表および Windows PowerShell コマンドに示します。わかりやすく説明するために、表に含まれているのは場所に基づくルーティングに固有の設定のみです。

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
<th>音声ルーティング ポリシー 1</th>
<th>音声ルーティング ポリシー 2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>音声ポリシー ID</p></td>
<td><p>Delhi の音声ルーティング ポリシー</p></td>
<td><p>Hyderabad の音声ルーティング ポリシー</p></td>
</tr>
<tr class="even">
<td><p>PSTN 使用法</p></td>
<td><p>Delhi の使用法、PBX Del の使用法、PBX Hyd の使用法</p></td>
<td><p>Hyderabad の使用法、PBX Hyd の使用法、PBX Del の使用法</p></td>
</tr>
</tbody>
</table>

  

次に、該当するネットワーク サイトに対して場所に基づくルーティングを構成し、音声ルーティング ポリシーを関連付けます。Lync ServerWindows PowerShell コマンドである New-CsNetworkSite を使用して場所に基づくルーティングを有効にし、ルーティングの制限を適用する必要のあるネットワーク サイトに音声ルーティング ポリシーを関連付けます。

    Set-CsNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false> -VoiceRoutingPolicy <voice routing policy ID>

この例では、Lync ServerWindows PowerShell を使用して、このシナリオで定義されている 2 つの異なるネットワーク サイト (Delhi および Hyderabad) に対する場所に基づくルーティングを次の表に示します。わかりやすく説明するために、表に含まれているのは場所に基づくルーティングに固有の設定のみです。

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
<th>サイト 1 (Delhi)</th>
<th>サイト 2 (Hyderabad)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>サイト名</p></td>
<td><p>サイト 1 (Delhi)</p></td>
<td><p>サイト 2 (Hyderabad)</p></td>
</tr>
<tr class="even">
<td><p>EnableLocationBasedRouting</p></td>
<td><p>True</p></td>
<td><p>True</p></td>
</tr>
<tr class="odd">
<td><p>音声ルーティング ポリシー</p></td>
<td><p>Delhi の音声ルーティング ポリシー</p></td>
<td><p>Hyderabad の音声ルーティング ポリシー</p></td>
</tr>
<tr class="even">
<td><p>サブネット</p></td>
<td><p>サブネット 1 (Delhi)</p></td>
<td><p>サブネット 2 (Hyderabad)</p></td>
</tr>
</tbody>
</table>



## トランクに対する場所に基づくルーティングの有効化

トランク構成に対して場所に基づくルーティングを有効にするには、トランクごと、またはネットワーク サイトごとにトランク構成を作成する必要があります。トランク構成を作成するには、Lync ServerWindows PowerShell コマンドである New-CsTrunkConfiguration を使用します。複数のトランクが特定のシステム (ゲートウェイまたは PBX) に関連付けられている場合は、場所に基づくルーティングの制限を有効にするように各トランク構成を変更する必要があります。

    New-CsTrunkConfiguration -Identity < trunk configuration ID>

詳細については、「[New-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsTrunkConfiguration)」を参照してください。

この例では、このシナリオで定義されている展開内のトランクごとに 1 つのトランク構成を作成する方法を次の Windows PowerShell コマンドに示します。

    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 1 DEL-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 2 HYD-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 3 DEL-PBX>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 4 HYD-PBX>"

トランクごとのトランク構成が作成されたら、Lync ServerWindows PowerShell コマンドである Set-CsTrunkConfiguration を使用して、ルーティングの制限を適用する必要のあるトランクに対して場所に基づくルーティングを有効にすることができます。PSTN ゲートウェイに通話をルーティングするトランクに対して場所に基づくルーティングを有効にし、ゲートウェイが配置されているネットワーク サイトを関連付けます。

    Set-CsTrunkConfiguration -Identity <trunk configuration ID> -EnableLocationRestriction $true -NetworkSiteID <site ID>

詳細については、「[New-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsTrunkConfiguration)」を参照してください。

この例では、Delhi および Hyderabad の PSTN ゲートウェイに関連付けられているトランクごとに場所に基づくルーティングが有効になります。

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 1 DEL-GW -EnableLocationRestriction $true -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 2 HYD-GW -EnableLocationRestriction $true -NetworkSiteID "Hyderabad"

  

PSTN に通話をルーティングしないトランクに対しては、場所に基づくルーティングを有効にしないでください。ただし、システムが配置されているネットワーク サイトにはトランクを関連付ける必要があります。これは、このトランクを使用して接続されるエンドポイントに到達する PSTN 通話に、場所に基づくルーティングの制限を適用する必要があるためです。この例では、Delhi および Hyderabad の PBX システムに関連付けられている各トランクに対しては、場所に基づくルーティングが有効になりません。

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 3 DEL-PBX -EnableLocationRestriction $false -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 4 HYD-PBX -EnableLocationRestriction $false -NetworkSiteID "Hyderabad"

  
PSTN (PBX) に通話をルーティングしないシステムに接続されるエンドポイントにおける制限は、場所に基づくルーティングが有効なユーザーの Lync エンドポイントと同様です。つまり、これらのユーザーは場所に関係なく、Lync ユーザーとの通話を発信および着信できます。また、システムが関連付けられているネットワーク サイトに関係なく、PSTN ネットワーク (別の PBX に接続されるエンドポイント) に通話をルーティングしない他のシステムとの通話を発信および着信することもできます。着信通話、発信通話、通話の転送、PSTN エンドポイントが関係する着信の転送にはすべて、場所に基づくルーティングが適用されます。このような通話では、該当するシステムに対してローカルであると定義されている PSTN ゲートウェイだけを使用する必要があります。

次の表は、2 つの異なるネットワーク サイトにおける 4 つのトランクのトランク構成を示しています。これらのトランクのうちの 2 つは PSTN ゲートウェイに、残りの 2 つは PBX システムに接続されています。


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
<td><p>PstnGateway:Trunk 1 DEL-GW</p></td>
<td><p>True</p></td>
<td><p>サイト 1 (Delhi)</p></td>
</tr>
<tr class="even">
<td><p>PstnGateway:Trunk 2 HYD-GW</p></td>
<td><p>True</p></td>
<td><p>サイト 2 (Hyderabad)</p></td>
</tr>
<tr class="odd">
<td><p>PstnGateway:Trunk 3 DEL-PBX</p></td>
<td><p>False</p></td>
<td><p>サイト 1 (Delhi)</p></td>
</tr>
<tr class="even">
<td><p>PstnGateway:Trunk 4 HYD-PBX</p></td>
<td><p>False</p></td>
<td><p>サイト 2 (Hyderabad)</p></td>
</tr>
</tbody>
</table>



## 音声ポリシーに対する場所に基づくルーティングの有効化

特定のユーザーに対して場所に基づくルーティングを適用するには、PSTN 料が適切に課金されるようにそれらのユーザーの音声ポリシーを構成します。新しい音声ポリシーを作成するには、Lync ServerWindows PowerShell コマンドである New-CsVoicePolicy を使用します。既存のポリシーを使用する場合は、Set-CsVoicePolicy を使用して場所に基づくルーティングを有効にします。

    Set-CsVoicePolicy -Identity <voice policy ID> -PreventPSTNTollBypass <$true|$false>

詳細については、「[New-CsVoicePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsVoicePolicy)」を参照してください。

この例では、このシナリオで定義されている Delhi と Hyderabad の音声ポリシーにおいて PSTN 料が適切に課金されるようにする方法を次の表および Windows PowerShell コマンドに示します。わかりやすく説明するために、表に含まれているのは場所に基づくルーティングに固有の設定のみです。

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
<th>音声ポリシー 1</th>
<th>音声ポリシー 2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>音声ポリシー ID</p></td>
<td><p>Delhi の音声ポリシー</p></td>
<td><p>Hyderabad の音声ポリシー</p></td>
</tr>
<tr class="even">
<td><p>PSTN 使用法</p></td>
<td><p>Delhi の使用法、PBX Del の使用法、PBX Hyd の使用法</p></td>
<td><p>Hyderabad の使用法、PBX Hyd の使用法、PBX Del の使用法</p></td>
</tr>
<tr class="odd">
<td><p>PreventPSTNTollBypass</p></td>
<td><p>True</p></td>
<td><p>True</p></td>
</tr>
</tbody>
</table>



## ルーティング構成に対する場所に基づくルーティングの有効化

最後に、ルーティング構成に対して場所に基づくルーティングをグローバルに有効にします。場所に基づくルーティングを有効にするには、Lync ServerWindows PowerShell コマンドである New-CsRoutingConfiguration を使用します。

    Set-CsRoutingConfiguration -EnableLocationBasedRouting $true

詳細については、「[Set-CsRoutingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsRoutingConfiguration)」を参照してください。

> [!NOTE]
> 場所に基づくルーティングはグローバル構成を使用して有効にする必要がありますが、ルール セットが適用されるのは、(このドキュメントで説明した) ルール セットを構成する対象となったサイト、ユーザー、トランクに対してのみです。



## 関連項目

#### その他のリソース

[Lync Server 2013 の場所に基づくルーティングの構成](lync-server-2013-configuring-location-based-routing.md)

