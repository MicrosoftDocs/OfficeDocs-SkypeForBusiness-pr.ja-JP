---
title: 'Lync Server 2013: PSTN 使用法レコード'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN usage records
ms:assetid: b5f624aa-abe8-455b-a8e3-c228be230463
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412878(v=OCS.15)
ms:contentKeyID: 48185188
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5909494b4e4b6901964a7642481302ca221fe086
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724677"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-usage-records-in-lync-server-2013"></a>Lync Server 2013 の PSTN 使用法レコード

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-23_

PSTN 使用法レコードの計画では、主に、CEO から派遣社員、コンサルタント、および臨時スタッフに至る組織内のすべてのユーザーに現在適用されているすべての通話許可の一覧を作成します。 この作業を行うと、既存の通話許可を再度検証し、それらを修正することができます。 予想されるエンタープライズ Voip ユーザーに適用される通話のアクセス許可に対してのみ、PSTN 使用状況レコードを作成できますが、現在のところ一部ではない可能性があるかどうかにかかわらず、すべての通話アクセス許可について PSTN 使用状況レコードを作成することがあります。エンタープライズ Voip を有効にするユーザーのグループに適用します。 通話許可の変更や、異なる通話許可を持つ新規ユーザーを追加する場合でも、必要な電話 PSTN 使用法レコードは既に作成済みであるため、新しく作成する必要がありません。

次の表に、一般的な PSTN 使用法テーブルを示します。

### <a name="pstn-usage-records"></a>PSTN 使用法レコード

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>電話属性</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Local</p></td>
<td><p>市内通話</p></td>
</tr>
<tr class="even">
<td><p>Long-Distance</p></td>
<td><p>長距離通話</p></td>
</tr>
<tr class="odd">
<td><p>International</p></td>
<td><p>国際通話</p></td>
</tr>
<tr class="even">
<td><p>Delhi</p></td>
<td><p>Delhi のフルタイム社員</p></td>
</tr>
<tr class="odd">
<td><p>Redmond</p></td>
<td><p>Redmond のフルタイム社員</p></td>
</tr>
<tr class="even">
<td><p>RedmondTemps</p></td>
<td><p>Redmond の派遣社員</p></td>
</tr>
<tr class="odd">
<td><p>Zurich</p></td>
<td><p>Zurich のフルタイム社員</p></td>
</tr>
</tbody>
</table>


PSTN 使用法レコードは単独では機能しません。PSTN 使用法レコードは、以下と組み合わせて使用する必要があります。

  - 音声ポリシー (ユーザーに割り当てる)

  - ルート (電話番号に割り当てる)

音声ポリシーとルートの詳細については、「lync [server 2013 のボイスポリシー](lync-server-2013-voice-policies.md) 」および「 [lync Server 2013 の音声ルート](lync-server-2013-voice-routes.md)」を参照してください。 それらの作成と構成の詳細については、「 [Lync Server 2013 で送信通話の音声ルートを構成](lync-server-2013-configuring-voice-routes-for-outbound-calls.md)する」を参照してください。

</div>

<span> </span>

</div>

</div>

</div>

