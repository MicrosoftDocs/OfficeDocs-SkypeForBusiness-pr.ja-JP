---
title: 結果を解釈する
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Interpreting the Results
ms:assetid: dd7f199f-7075-4d88-bb84-49a7e05eb593
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945608(v=OCS.15)
ms:contentKeyID: 51541433
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0a3dc473765a67db2e09f5a56db14b1ea8a41a4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841046"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="interpreting-the-results"></a>結果を解釈する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-24_

Lync Server 2013 応力/パフォーマンスツール (LyncPerfTool) には、クライアントが何を実行しているのか、問題が発生しているかを理解するために使用できる多くのカウンターがあります。

<div>

## <a name="client-counters"></a>クライアントカウンター

実行されている LyncPerfTool の各インスタンスには、カウンターの個別のインスタンスがあります。 各インスタンスには、プロセス ID で名前が付けられます。

クライアントが過負荷になっていると、問題が発生する可能性があります。 これらの問題を回避するには、次の操作を行います。

1.  クライアントコンピューターの CPU とメモリ使用量を監視します。 CPU が常に 90% を超えている場合は、ユーザーの数を減らします。

2.  メモリフットプリントが高すぎる場合は、ページファイルが十分でない場合に問題が発生する可能性があります。 コミットチャージがコンピューターの制限に達していないことを確認します。 メモリの制限を使用している場合は、ページファイルのサイズを大きくするか、ユーザーの数を減らすことを検討してください。

次の表では、LyncPerfTool のパフォーマンスカウンターの主要な一覧を示します。

**一般的な情報**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>パフォーマンスカウンター</strong></th>
<th><strong>説明</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>分数で費やした時間</p></td>
<td><p>プロセスが開始されてから経過した時間。</p></td>
</tr>
<tr class="even">
<td><p>アクティブなエンドポイント</p></td>
<td><p>現在サーバーに接続されているエンドポイントの数です。</p></td>
</tr>
<tr class="odd">
<td><p>失敗したログオン</p></td>
<td><p>エンドポイントのサインインエラーの合計数です。</p></td>
</tr>
<tr class="even">
<td><p>ログオン試行</p></td>
<td><p>エンドポイントのサインイン試行の合計数です。</p></td>
</tr>
<tr class="odd">
<td><p>エンドポイントが切断されました</p></td>
<td><p>切断されたエンドポイントの合計数です。</p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


**プレゼンス情報**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>パフォーマンスカウンター</strong></th>
<th><strong>説明</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>SetPresence 通話</p></td>
<td><p>プレゼンス変更の試行回数の合計です。 さまざまな種類のプレゼンス変更については、「SetPresence (プレゼンスの種類) 呼び出しのパフォーマンスカウンター」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p>SetPresence の NNN 応答</p></td>
<td><p>サーバーから受信した nnn 応答コードの合計数です。</p></td>
</tr>
<tr class="odd">
<td><p>GetPresence 通話</p></td>
<td><p>プレゼンス要求の取得試行の合計数です。</p></td>
</tr>
<tr class="even">
<td><p>GetPresence に対する NNN の応答</p></td>
<td><p>サーバーから受信した nnn 応答コードの合計数です。</p></td>
</tr>
</tbody>
</table>


**アドレス帳サービス情報**

このカテゴリには、アドレス帳サービス (ABS) ファイルのダウンロードとアドレス帳の Web クエリサービス要求を監視するために使用されるカウンターが含まれています。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>パフォーマンスカウンター</strong></th>
<th><strong>説明</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>完全なフル/差分ファイルのダウンロードが試行される</p></td>
<td><p>試行されたフルまたは差分ファイルのダウンロード要求の合計数です。</p></td>
</tr>
<tr class="even">
<td><p>ABS フル/差分ファイルのダウンロードに成功しました</p></td>
<td><p>試行されたフルまたは差分ファイルのダウンロード要求の合計数です。</p></td>
</tr>
<tr class="odd">
<td><p>アドレス帳 Web クエリサービスに関連するカウンター</p></td>
<td><p>アドレス帳ファイルのダウンロードに関連するカウンター。</p></td>
</tr>
<tr class="even">
<td><p>ABS 呼び出しを実行しました</p></td>
<td><p>試行されたアドレス帳 Web クエリサービス要求の合計数です。</p></td>
</tr>
<tr class="odd">
<td><p>ABS 呼び出しに成功しました</p></td>
<td><p>成功応答コードを返した、アドレス帳 Web クエリサービス要求の合計数です。</p></td>
</tr>
<tr class="even">
<td><p>ABS 呼び出しに失敗しました</p></td>
<td><p>エラー応答コードを返した、アドレス帳 Web クエリサービス要求の合計数です。</p></td>
</tr>
</tbody>
</table>


**配布リスト (DL) 情報**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>パフォーマンスカウンター</strong></th>
<th><strong>説明</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>通話を発信しました</p></td>
<td><p>試みた配布リスト展開 (DLX) web サービス要求の合計数。</p></td>
</tr>
<tr class="even">
<td><p>通話成功</p></td>
<td><p>成功した応答コードを返した DLX web サービス要求の合計数です。</p></td>
</tr>
<tr class="odd">
<td><p>通話失敗</p></td>
<td><p>エラー応答コードを返した DLX web サービス要求の合計数です。</p></td>
</tr>
</tbody>
</table>


**VoIP の基本情報**

以下のパフォーマンスカウンターには、これらのシナリオが有効な場合に、仲介サーバー、A/V 会議サーバー、エッジサーバー、応答グループアプリケーション、会議の自動応答など、すべてのボイスオーバー IP (VoIP) 通話の番号が報告されます。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>パフォーマンスカウンター</strong></th>
<th><strong>説明</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>アクティブな通話</p></td>
<td><p>現在進行中の着信/発信音声通話の合計数です。</p></td>
</tr>
<tr class="even">
<td><p>通話終了</p></td>
<td><p>着信/発信の音声通話の合計数は既に終了しています。</p></td>
</tr>
<tr class="odd">
<td><p>通話拒否</p></td>
<td><p>拒否された音声通話の合計数です。</p></td>
</tr>
<tr class="even">
<td><p>着信/発信通話を発信しました</p></td>
<td><p>発信した音声通話の合計数。</p></td>
</tr>
<tr class="odd">
<td><p>確立された着信/発信通話</p></td>
<td><p>送受信された音声通話の合計数が設定されました。</p></td>
</tr>
<tr class="even">
<td><p>通話受信 NNN</p></td>
<td><p>サーバーから受信した nnn 応答コードの合計数です。</p></td>
</tr>
<tr class="odd">
<td><p>VoIP パスレート (%)</p></td>
<td><p>発信された通話合計発信/合計通話が完了しました。</p></td>
</tr>
</tbody>
</table>


**応答グループサービスの通話情報**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>パフォーマンスカウンター</strong></th>
<th><strong>説明</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>アクティブな通話</p></td>
<td><p>応答グループアプリケーションへのアクティブな通話の合計数です。</p></td>
</tr>
<tr class="even">
<td><p>通話を発信しました</p></td>
<td><p>試行された通話の合計数です。</p></td>
</tr>
</tbody>
</table>


**インスタントメッセージング (IM) 通話情報**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>パフォーマンスカウンター</strong></th>
<th><strong>説明</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>アクティブな通話</p></td>
<td><p>進行中の着信/発信インスタントメッセージ通話の合計数です。</p></td>
</tr>
<tr class="even">
<td><p>通話終了</p></td>
<td><p>受信/送信されたインスタントメッセージの通話の合計数が既に終了しています。</p></td>
</tr>
<tr class="odd">
<td><p>通話受信 NNN</p></td>
<td><p>サーバーから受信した nnn 応答コードの合計数です。</p></td>
</tr>
<tr class="even">
<td><p>受信/送信された IM メッセージ</p></td>
<td><p>すべてのセッションで受信または送信されたメッセージの合計数です。</p></td>
</tr>
<tr class="odd">
<td><p>着信/発信通話を発信しました</p></td>
<td><p>発信したインスタントメッセージ通話の合計数。</p></td>
</tr>
<tr class="even">
<td><p>確立された着信/発信通話</p></td>
<td><p>確立された受信/送信インスタントメッセージの合計数です。</p></td>
</tr>
</tbody>
</table>


**アプリ共有の通話情報**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>パフォーマンスカウンター</strong></th>
<th><strong>説明</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>アクティブな通話</p></td>
<td><p>進行中の着信/送信アプリケーション共有通話の合計数です。</p></td>
</tr>
<tr class="even">
<td><p>通話終了</p></td>
<td><p>受信/送信アプリケーション共有通話の合計数が既に終了しています。</p></td>
</tr>
<tr class="odd">
<td><p>通話受信 NNN</p></td>
<td><p>サーバーから受信した nnn 応答コードの合計数です。</p></td>
</tr>
<tr class="even">
<td><p>着信/発信通話を発信しました</p></td>
<td><p>試行された受信/送信アプリケーション共有通話の合計数。</p></td>
</tr>
<tr class="odd">
<td><p>確立された着信/発信通話</p></td>
<td><p>確立された受信/送信アプリケーション共有通話の合計数です。</p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


**CAA を通話情報**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>パフォーマンスカウンター</strong></th>
<th><strong>説明</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>アクティブな通話</p></td>
<td><p>現在進行中の着信/発信公衆交換電話網 (PSTN) 通話の合計数です。</p></td>
</tr>
<tr class="even">
<td><p>通話終了</p></td>
<td><p>着信/発信された PSTN 通話の合計数は既に終了しています。</p></td>
</tr>
<tr class="odd">
<td><p>着信/発信通話を発信しました</p></td>
<td><p>試行された着信/発信の PSTN 通話の合計数。</p></td>
</tr>
<tr class="even">
<td><p>確立された着信/発信通話</p></td>
<td><p>確立された着信/発信 PSTN 通話の合計数です。</p></td>
</tr>
</tbody>
</table>


**会議情報**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>パフォーマンスカウンター</strong></th>
<th><strong>説明</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>アクティブなインスタントメッセージ会議</p></td>
<td><p>進行中のインスタントメッセージ会議の合計数です。</p></td>
</tr>
<tr class="even">
<td><p>アクティブな音声/ビデオ会議</p></td>
<td><p>進行中の音声/ビデオ (A/V) 会議の合計数です。</p></td>
</tr>
<tr class="odd">
<td><p>アクティブなアプリケーション共有会議</p></td>
<td><p>進行中のアプリケーション共有会議の合計数です。</p></td>
</tr>
<tr class="even">
<td><p>参加者の数</p></td>
<td><p>現在会議に接続されている参加者の合計数です。</p></td>
</tr>
<tr class="odd">
<td><p>会議のスケジュールエラー</p></td>
<td><p>会議をスケジュールしようとしたときに発生したエラーの合計数です。</p></td>
</tr>
<tr class="even">
<td><p>電話会議に参加できない</p></td>
<td><p>会議に接続しようとしているときに発生したエラーの合計数です。</p></td>
</tr>
</tbody>
</table>


**UCWA クライアントカウンター**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>パフォーマンスカウンター</strong></th>
<th><strong>説明</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>成功した IMMCU の結合の合計数</p></td>
<td><p>参加したインスタントメッセージ会議の合計数です。</p></td>
</tr>
<tr class="even">
<td><p>成功した DMCU 結合の合計数</p></td>
<td><p>参加した A/V 会議の合計数です。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

