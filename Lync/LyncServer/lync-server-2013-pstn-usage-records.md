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
ms.openlocfilehash: 60700070c5426d4df4d1957367ccfd743a5ba44b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042034"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-usage-records-in-lync-server-2013"></a>Lync Server 2013 の PSTN 使用法レコード

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-23_

PSTN 使用法レコードの計画では、主に、CEO から派遣社員、コンサルタント、および臨時スタッフに至る組織内のすべてのユーザーに現在適用されているすべての通話許可の一覧を作成します。 この作業を行うと、既存の通話許可を再度検証し、それらを修正することができます。 エンタープライズ VoIP の見込みユーザーに適用する通話許可のみに対応した PSTN 使用法レコードを作成することもできますが、現時点で通話許可がエンタープライズ VoIP で有効なユーザー グループのメンバーに適用されるかどうかに関係なく、すべての通話許可に対応した PSTN 使用法レコードを作成する方が、長期的には優れたソリューションになる場合があります。 通話許可の変更や、異なる通話許可を持つ新規ユーザーを追加する場合でも、必要な電話 PSTN 使用法レコードは既に作成済みであるため、新しく作成する必要がありません。

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
<td><p>ローカル</p></td>
<td><p>市内通話</p></td>
</tr>
<tr class="even">
<td><p>長距離</p></td>
<td><p>長距離通話</p></td>
</tr>
<tr class="odd">
<td><p>International</p></td>
<td><p>国際通話</p></td>
</tr>
<tr class="even">
<td><p>デリー</p></td>
<td><p>Delhi のフルタイム社員</p></td>
</tr>
<tr class="odd">
<td><p>レッドモンド</p></td>
<td><p>Redmond のフルタイム社員</p></td>
</tr>
<tr class="even">
<td><p>RedmondTemps</p></td>
<td><p>Redmond の派遣社員</p></td>
</tr>
<tr class="odd">
<td><p>Zurich フルタ</p></td>
<td><p>Zurich のフルタイム社員</p></td>
</tr>
</tbody>
</table>


PSTN 使用法レコードは単独では機能しません。 PSTN 使用法レコードは、以下と組み合わせて使用する必要があります。

  - 音声ポリシー (ユーザーに割り当てる)

  - ルート (電話番号に割り当てる)

音声ポリシーとルートの詳細については、「lync server [2013 の音声ポリシー](lync-server-2013-voice-policies.md) 」および「 [lync server 2013 の音声ルート](lync-server-2013-voice-routes.md)」を参照してください。 これらを作成して構成する方法の詳細については、「 [Lync Server 2013 で送信呼び出しの音声ルートを構成](lync-server-2013-configuring-voice-routes-for-outbound-calls.md)する」を参照してください。

</div>

<span> </span>

</div>

</div>

</div>

