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
ms.openlocfilehash: 4ec15b826614afcca970989b6436d3ad94d7941f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722837"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assigning-per-user-presence-policies-in-lync-server-2013"></a>Lync Server 2013 でのユーザーごとのプレゼンスポリシーの割り当て

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-11_

プレゼンスポリシーは、プレゼンスに影響する制限と制限のセットです。 次の表では、Lync Server 2013 で使用できるプレゼンスポリシーの設定について説明します。

### <a name="presence-policy-settings"></a>プレゼンスポリシーの設定

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
<td><p>サブスクライバーカテゴリのサブスクリプションの最大数</p></td>
<td><p>サブスクライバーカテゴリのサブスクリプションの数を制限します。 たとえば、ユーザーのプレゼンスをサブスクライブしている場合は、連絡先カード、予定表データ、メモ、サービス、状態カテゴリごとに、カテゴリサブスクリプションが取得されます。</p>
<p>0に設定すると、ユーザーまたは連絡先オブジェクトは、他のユーザーが購読できないことを意味します。</p>
<div>

> [!NOTE]  
> この設定は、高い数値に設定されている場合に、パフォーマンスに大きな影響を与える可能性があります。また、平均的なユーザーが多数のユーザーに対して自分のプレゼンスをサブスクライブしている場合があります。


</div></td>
<td><p>整数型</p></td>
<td><p>0-3000</p></td>
</tr>
<tr class="even">
<td><p>PromptedSubscribers</p></td>
<td><p>キューに登録されているプレゼンス情報の通知の最大数</p></td>
<td><p>プロンプトを表示するサブスクライバーテーブルのエントリ数を制限します。 この設定では、特定のユーザーに対してキューに入れることができるプロンプトの最大数を決定します。 たとえば、ユーザー A がユーザー B のプレゼンスをサブスクライブしている場合、ユーザー B はユーザー A がユーザー B に登録されていることを知らせるメッセージを受け取り、ユーザー b の [プロンプトを表示するサブスクライバー] テーブルに確認メッセージが表示されます。 ユーザー B がサブスクリプションを承認するか、承認すると、確認メッセージがユーザー B のプロンプトのサブスクライバーテーブルから削除されます。</p>
<p>0に設定すると、他のユーザーが自分のプレゼンスをサブスクライブしているときに、ユーザーにメッセージが表示されなくなります。</p></td>
<td><p>Integer または Token</p></td>
<td><p>0-500</p></td>
</tr>
</tbody>
</table>


既定では、Lync Server を展開すると、既定の**ポリシー**と**サービス: Medium**プレゼンスポリシーがインストールされます。 次の表では、2つのプレゼンスポリシーの固有の設定について説明します。

### <a name="presence-policies"></a>プレゼンスポリシー

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>ポリシー名</th>
<th>説明</th>
<th>カテゴリのサブスクリプション</th>
<th>PromptedSubscribers</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>既定のポリシー</p></td>
<td><p>一般的なユーザー向けのポリシー。 これは既定のプレゼンスポリシーです。</p></td>
<td><p>1000</p></td>
<td><p>200</p></td>
</tr>
<tr class="even">
<td><p>サービス: 媒体</p></td>
<td><p>他のユーザーがオブジェクトのプレゼンスをサブスクライブする必要があるアプリケーションのポリシー。</p></td>
<td><p>1000</p></td>
<td><p>0</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

