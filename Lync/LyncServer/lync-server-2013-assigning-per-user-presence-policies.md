---
title: Lync Server 2013 でのユーザー単位のプレゼンス ポリシーの割り当て
TOCTitle: Lync Server 2013 でのユーザー単位のプレゼンス ポリシーの割り当て
ms:assetid: fd1097b7-248d-4b78-8c43-456b03257c18
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg182614(v=OCS.15)
ms:contentKeyID: 48274203
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのユーザー単位のプレゼンス ポリシーの割り当て

 

_**トピックの最終更新日:** 2015-03-09_

プレゼンス ポリシーは、プレゼンスに影響する一連の制限および制約事項です。次の表に、Lync Server 2013 で使用可能なプレゼンス ポリシー設定の説明を示します。

### プレゼンス ポリシー設定

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
<td><p>CategorySubscriptions</p></td>
<td><p>サブスクライバー カテゴリ サブスクリプションの最大数</p></td>
<td><p>サブスクライバー カテゴリ サブスクリプションの数を制限します。 たとえば Communicator は、ユーザーのプレゼンスに加入するとき、連絡先カード、予定表データ、メモ、サービス、および状態カテゴリごとにカテゴリ サブスクリプションを取得します。</p>
<p>設定が 0 の場合は、そのユーザーまたは連絡先オブジェクトに他のユーザーが加入することはできないことを意味します。</p>

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


既定では、Lync Server を展開するときに、**既定のポリシー**と**サービス: 中**のプレゼンス ポリシーがインストールされます。次の表に、この 2 つのプレゼンス ポリシーの具体的な設定の説明を示します。

### プレゼンス ポリシー

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
<th>CategorySubscriptions</th>
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
<td><p>0</p></td>
</tr>
</tbody>
</table>

