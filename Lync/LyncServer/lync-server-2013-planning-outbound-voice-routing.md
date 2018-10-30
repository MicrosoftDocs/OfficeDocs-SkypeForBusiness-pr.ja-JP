---
title: 'Lync Server 2013: 発信音声ルーティングの計画'
TOCTitle: 発信音声ルーティングの計画
ms:assetid: 37c55fa4-175a-4190-b9e4-c2e5ac7b9261
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg425853(v=OCS.15)
ms:contentKeyID: 48271766
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での発信音声ルーティングの計画

 

_**トピックの最終更新日:** 2015-03-09_

発信通話ルーティングは、公衆交換電話網 (PSTN) ゲートウェイ、トランク、または構内交換機 (PBX) に対して発信される通話に適用されます。ユーザーが電話をかけると、サーバーは、電話番号を E.164 形式に正規化し、必要に応じて、一致する SIP URI があるかどうかを調べます。一致する SIP URI が見つからない場合は、指定されたダイヤル文字列に基づいて発信通話ルーティング ロジックが適用されます。ユーザーは、次の表で説明するサーバー設定を構成することで、そのロジックを定義します。

### Lync Server 発信通話ルーティング設定

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


## このセクション中

ここでは、次の発信通話ルーティング サーバー設定の構成ガイドラインを提供します。

  - [Lync Server 2013 のダイヤル プランと正規化ルール](lync-server-2013-dial-plans-and-normalization-rules.md)

  - [Lync Server 2013 の音声ポリシー](lync-server-2013-voice-policies.md)

  - [Lync Server 2013 の PSTN 使用法レコード](lync-server-2013-pstn-usage-records.md)

  - [Lync Server 2013 の音声ルート](lync-server-2013-voice-routes.md)

## 関連項目

#### 概念

[Lync Server 2013 の SIP トランキング](lync-server-2013-sip-trunking.md)  
[Lync Server 2013 での直接 SIP 接続](lync-server-2013-direct-sip-connections.md)

