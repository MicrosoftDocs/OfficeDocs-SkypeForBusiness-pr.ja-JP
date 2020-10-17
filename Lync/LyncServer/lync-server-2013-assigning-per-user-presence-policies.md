---
title: 'Lync Server 2013: ユーザーごとのプレゼンスポリシーの割り当て'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assigning per-user presence policies
ms:assetid: fd1097b7-248d-4b78-8c43-456b03257c18
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182614(v=OCS.15)
ms:contentKeyID: 48185955
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c4f561189b72cf19fad28879711e3a1da0da8fb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527124"
---
# <a name="assigning-per-user-presence-policies-in-lync-server-2013"></a>Lync Server 2013 でユーザーごとのプレゼンスポリシーを割り当てる

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-11_

プレゼンス ポリシーは、プレゼンスに影響する一連の制限および制約事項です。 次の表では、Lync Server 2013 で利用できるプレゼンスポリシーの設定について説明します。

### <a name="presence-policy-settings"></a>プレゼンス ポリシー設定

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
<th>XML 名</th>
<th>表示名</th>
<th>説明</th>
<th>型</th>
<th>値</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>カテゴリのサブスクリプション</p></td>
<td><p>サブスクライバー カテゴリ サブスクリプションの最大数</p></td>
<td><p>サブスクライバー カテゴリ サブスクリプションの数を制限します。 たとえば Communicator は、ユーザーのプレゼンスに加入するとき、連絡先カード、予定表データ、メモ、サービス、および状態カテゴリごとにカテゴリ サブスクリプションを取得します。</p>
<p>設定が 0 の場合は、そのユーザーまたは連絡先オブジェクトに他のユーザーが加入することはできないことを意味します。</p>
<div>

> [!NOTE]  
> この設定が高い値に設定されているとパフォーマンスに著しい影響を与える可能性があり、平均的なユーザーには、そのユーザーのプレゼンスに多くのユーザーが加入しています。


</div></td>
<td><p>整数</p></td>
<td><p>0-3000</p></td>
</tr>
<tr class="even">
<td><p>PromptedSubscribers</p></td>
<td><p>キューに入れられるプレゼンス サブスクリプション通知の最大数</p></td>
<td><p>要求されたサブスクライバー テーブルのエントリ数を制限します。 この設定により、指定されたユーザーの場合にキューに入れることができるプロンプトの最大数が決まります。 たとえば、ユーザー A がユーザー B のプレゼンスに加入すると、ユーザー B は、ユーザー A が現在ユーザー B に加入したことを示すプロンプトを受信し、ユーザー B の要求されたサブスクライバー テーブルで受信確認プロンプトが作成されます。 ユーザー B がサブスクリプションを受け入れる、つまり確認すると、その受信確認プロンプトはユーザー B の要求されたサブスクライバー テーブルから削除されます。</p>
<p>設定が 0 の場合は、そのユーザーのプレゼンスに他のユーザーが加入しても、そのユーザーにプロンプトが送信されることはないことを意味します。</p></td>
<td><p>整数またはトークン</p></td>
<td><p>0-500</p></td>
</tr>
</tbody>
</table>


既定では、Lync Server を展開すると、 **既定のポリシー** と **サービス: 中** プレゼンスポリシーがインストールされます。 次の表に、この 2 つのプレゼンス ポリシーの具体的な設定の説明を示します。

### <a name="presence-policies"></a>プレゼンス ポリシー

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>[ポリシー名]</th>
<th>説明</th>
<th>カテゴリのサブスクリプション</th>
<th>PromptedSubscribers</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>[既定のポリシー]</p></td>
<td><p>標準的なユーザーを対象とするポリシー。 これは既定のプレゼンス ポリシーです。</p></td>
<td><p>1000</p></td>
<td><p>200</p></td>
</tr>
<tr class="even">
<td><p>サービス: 中</p></td>
<td><p>より多くのユーザーがオブジェクトのプレゼンスに加入する必要があるアプリケーションを対象とするポリシー。</p></td>
<td><p>1000</p></td>
<td><p>.0</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

