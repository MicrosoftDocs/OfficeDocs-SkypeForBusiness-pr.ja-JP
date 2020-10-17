---
title: 'Lync Server 2013: 発信音声ルーティングの計画'
description: 'Lync Server 2013: 発信音声ルーティングの計画。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning outbound voice routing
ms:assetid: 37c55fa4-175a-4190-b9e4-c2e5ac7b9261
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425853(v=OCS.15)
ms:contentKeyID: 48183835
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 057f81b995e231c2025a9fcb07e675086a662efe
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563983"
---
# <a name="planning-outbound-voice-routing-in-lync-server-2013"></a>Lync Server 2013 での発信音声ルーティングの計画

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-21_

発信通話ルーティングは、公衆交換電話網 (PSTN) ゲートウェイ、トランク、または構内交換機 (PBX) に対して発信される通話に適用されます。ユーザーが電話をかけると、サーバーは、電話番号を E.164 形式に正規化し、必要に応じて、一致する SIP URI があるかどうかを調べます。一致する SIP URI が見つからない場合は、指定されたダイヤル文字列に基づいて発信通話ルーティング ロジックが適用されます。ユーザーは、次の表で説明するサーバー設定を構成することで、そのロジックを定義します。

### <a name="lync-server-outbound-call-routing-settings"></a>Lync Server 発信通話ルーティング設定

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>オブジェクト</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ダイヤル プラン</p></td>
<td><p>ダイヤル プランとは、電話番号の承認と通話のルーティングを目的として、特定の場所、個々のユーザー、または連絡先オブジェクトの電話番号を 1 つの標準形式 (E.164) に変換する正規化ルールのセットに名前を付けたものです。</p></td>
</tr>
<tr class="even">
<td><p>正規化ルール</p></td>
<td><p>正規化ルールは、さまざまな形式で表現された電話番号を指定された各場所、ユーザー、または連絡先オブジェクトにルーティングする方法を定義します。ダイヤル元の場所および電話をかける人や連絡先オブジェクトによって、同じダイヤル文字列が異なる方法で解釈および変換される場合があります。特定の位置に関連付けられた正規化ルールをまとめたものが、ダイヤル プランです。</p></td>
</tr>
<tr class="odd">
<td><p>音声ポリシー</p></td>
<td><p>音声ポリシーでは、1 つ以上の PSTN 使用法レコードを 1 人のユーザーまたはユーザーのグループに関連付けます。 音声ポリシーも、ユーザーが有効と無効を切り替えできる通話機能のリストを提供します。</p></td>
</tr>
<tr class="even">
<td><p>PSTN 使用法レコード</p></td>
<td><p>PSTN 使用法レコードは、組織内のさまざまなユーザーまたはグループが利用できる通話のクラス (内部、市内、長距離など) を指定します。</p></td>
</tr>
<tr class="odd">
<td><p>通話ルート</p></td>
<td><p>通話ルートでは、通話先の電話番号を特定のトランクおよび PSTN 使用法レコードに関連付けます。 PSTN ゲートウェイはトランクとみなされます。</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a>このセクションの内容

ここでは、次の発信通話ルーティング サーバー設定の構成ガイドラインを提供します。

  - <span></span>  
    [Lync Server 2013 のダイヤルプランと正規化ルール](lync-server-2013-dial-plans-and-normalization-rules.md)

  - <span></span>  
    [Lync Server 2013 の音声ポリシー](lync-server-2013-voice-policies.md)

  - <span></span>  
    [Lync Server 2013 の PSTN 使用法レコード](lync-server-2013-pstn-usage-records.md)

  - <span></span>  
    [Lync Server 2013 の音声ルート](lync-server-2013-voice-routes.md)

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での SIP トランキング](lync-server-2013-sip-trunking.md)  
[Lync Server 2013 の直接 SIP 接続](lync-server-2013-direct-sip-connections.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

