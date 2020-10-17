---
title: 'Lync Server 2013: エンタープライズ Voip の構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Enterprise Voice
ms:assetid: 7df179fa-d3a2-4b23-a433-b750aedf980b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994041(v=OCS.15)
ms:contentKeyID: 51803952
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca998a723e4ef84fc1c203d6eddc5f9016f28739
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532554"
---
# <a name="configuring-enterprise-voice-in-lync-server-2013"></a>Lync Server 2013 でのエンタープライズ Voip の構成

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-03-12_

エンタープライズ Voip を展開するには、次のものを構成する必要があります。

  - トランクを作成する

  - 音声ポリシーを定義する

  - 音声ルートを定義する

  - エンタープライズ VoIP に対するユーザーの有効化

<div>

## <a name="create-a-trunk"></a>トランクを作成する

エンタープライズ Voip 展開でトランクを定義する必要があります。 Location-Based ルーティングでは、トランクごとにトランク構成を作成する必要があります。 Lync Server トポロジビルダーを使用してトランクを定義し、Lync Server Windows PowerShell コマンド、Get-cstrunkconfiguration、または Lync Server コントロールパネルを使用して、対応するトランク構成を定義します。 トランク構成での Location-Based ルーティングを有効にする方法の詳細については、「Enable Location-Based Routing to トランク」を参照してください。このトピックでは、「Enable [Location-Based routing In Lync Server 2013](lync-server-2013-enabling-location-based-routing.md)」を参照してください。 この例では、次の表は、このシナリオで使用されているトランクを示しています。

詳細については、「 [Define more トランク In Topology Builder In Lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md)」を参照してください。


<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>トランク名</th>
<th>システムの種類</th>
<th>名前</th>
<th>場所</th>
<th>仲介サーバー</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>トランク 1 DEL-GW</p></td>
<td><p>PSTN ゲートウェイ</p></td>
<td><p>DEL-GW</p></td>
<td><p>デリー</p></td>
<td><p>MS1</p></td>
</tr>
<tr class="even">
<td><p>トランク 2 HYD</p></td>
<td><p>PSTN ゲートウェイ</p></td>
<td><p>HYD-GW</p></td>
<td><p>Hyderabad</p></td>
<td><p>MS1</p></td>
</tr>
<tr class="odd">
<td><p>トランク 3 DEL-PBX</p></td>
<td><p>PBX</p></td>
<td><p>DEL-PBX</p></td>
<td><p>デリー</p></td>
<td><p>MS1</p></td>
</tr>
<tr class="even">
<td><p>トランク 4 HYD</p></td>
<td><p>PBX</p></td>
<td><p>HYD</p></td>
<td><p>Hyderabad</p></td>
<td><p>MS1</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="defines-voice-policies"></a>音声ポリシーを定義します。

エンタープライズ Voip 展開の音声ポリシーを定義する必要があります。 音声ポリシーを定義して、Location-Based ルーティングを使用するために必要なサブセットだけがある場合は、ユーザーのサブセットに Location-Based ルーティング制限を適用します。 この例では、次の表に、このシナリオで使用されている音声ポリシーを示します。 説明のために、Location-Based ルーティングに固有の設定のみが表に含まれています。

詳細については、「 [Lync Server 2013 で通話機能および権限を承認するための音声ポリシーと PSTN 使用法レコードの構成](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)」を参照してください。


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
<td><p>False</p></td>
<td><p>False</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-voice-routes"></a>音声ルートを定義する

エンタープライズ Voip 展開の音声ルートを定義する必要があります。 この例では、次の表に、このシナリオで使用されている音声ルートを示します。 説明のために、Location-Based ルーティングに固有の設定のみが表に含まれています。

詳細については、「 [Lync Server 2013 で送信呼び出しの音声ルートを構成する](lync-server-2013-configuring-voice-routes-for-outbound-calls.md)」を参照してください。


<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>音声ルート1</th>
<th>音声ルート2</th>
<th>音声ルート3</th>
<th>ボイスルート4</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>名前</p></td>
<td><p>ニューデリー</p></td>
<td><p>Hyderabad ルート</p></td>
<td><p>PBX の Del ルート</p></td>
<td><p>PBX Hyd ルート</p></td>
</tr>
<tr class="even">
<td><p>PSTN 使用法</p></td>
<td><p>ニューデリーの使用法</p></td>
<td><p>Hyderabad の使用状況</p></td>
<td><p>PBX の Del の使用</p></td>
<td><p>PBX Hyd の使用状況</p></td>
</tr>
<tr class="odd">
<td><p>樹幹</p></td>
<td><p>トランク 1 DEL-GW</p></td>
<td><p>トランク 2 HYD</p></td>
<td><p>トランク 3 DEL-PBX</p></td>
<td><p>トランク 4 HYD</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-users-for-enterprise-voice"></a>エンタープライズ VoIP に対するユーザーの有効化

エンタープライズ Voip に対してユーザーを有効にし、以前に定義した音声ポリシーを割り当てます。 この例では、次の表は、このシナリオで使用されている割り当てを示しています。 説明のために、Location-Based ルーティングに固有の設定のみが表に含まれています。

詳細については、「 [Lync Server 2013 のエンタープライズ voip でユーザーを有効にする](lync-server-2013-enable-users-for-enterprise-voice.md)」を参照してください。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>ニューデリーにあるユーザー</th>
<th>Hyderabad にあるユーザー</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>関連付けられた音声ポリシー</p></td>
<td><p>ニューデリー音声ポリシー</p></td>
<td><p>Hyderabad 音声ポリシー</p></td>
</tr>
<tr class="even">
<td><p>サンプルユーザー</p></td>
<td><p>「DEL-LYNC-1, DEL-LYNC-2, DEL-3」</p></td>
<td><p>HYD-1、HYD、HYD (LYNC-3)</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での Location-Based ルーティングの構成](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

