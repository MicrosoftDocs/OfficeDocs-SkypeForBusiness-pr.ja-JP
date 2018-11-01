---
title: 'Lync Server 2013: 常設チャット サーバーのコンプライアンス テーブルのリスト'
TOCTitle: 常設チャット サーバーのコンプライアンス テーブルのリスト
ms:assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ215878(v=OCS.15)
ms:contentKeyID: 48272715
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の常設チャット サーバーのコンプライアンス テーブルのリスト

 

_**トピックの最終更新日:** 2015-03-09_

常設チャット コンプライアンス データベース スキーマは、次のテーブルで構成されます。

## 常設チャット サーバー コンプライアンス テーブルの一覧


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>テーブル</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tblcompliancedata.md">Lync Server 2013 の tblComplianceData</a></p></td>
<td><p>構成済みのアダプターによってまだ処理されていないコンプライアンス イベントが格納されます。</p>
<p>このテーブルには、チャット メッセージやファイル ダウンロードなどの、常設チャット関連のイベントが含まれます (参加者イベントは tblComplianceParticipant テーブルで追跡されます)。</p>
<p>(このテーブルのイベントを処理したサーバーは、tblComplianceFanout テーブルに含まれます)</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblcompliancefanout.md">Lync Server 2013 内の tblComplianceFanout</a></p></td>
<td><p>コンプライアンス イベントを処理したサーバーが格納されます。このテーブルは tblComplianceData テーブルと緊密に結び付けられています。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblcomplianceparticipant.md">Lync Server 2013 内の tblComplianceParticipant</a></p></td>
<td><p>チャット サービス別およびサーバー別に現在の参加者が格納されます。参加および 常設チャット サービスから受信した部分コンプライアンス イベントに基づいて維持されます。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblcompliancestate.md">Lync Server 2013 の tblComplianceState</a></p></td>
<td><p>プール全体のコンプライアンス状態情報が含まれます。</p></td>
</tr>
</tbody>
</table>

