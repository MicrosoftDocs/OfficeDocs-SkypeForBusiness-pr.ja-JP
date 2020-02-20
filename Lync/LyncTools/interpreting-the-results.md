---
title: 結果の解釈
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Interpreting the Results
ms:assetid: dd7f199f-7075-4d88-bb84-49a7e05eb593
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945608(v=OCS.15)
ms:contentKeyID: 51541433
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 484f10757dcbd1463b54cf70ac8d725402decb44
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147750"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="interpreting-the-results"></a>結果の解釈

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-24_

Lync Server 2013 のストレスおよびパフォーマンスツール (LyncPerfTool) には、クライアントの動作と問題が発生しているかどうかを理解するために使用できるカウンターが多数あります。

<div>

## <a name="client-counters"></a>クライアントカウンター

実行されている LyncPerfTool の各インスタンスには、カウンターの個別のインスタンスがあります。 各インスタンスには、プロセス ID で名前が付けられます。

クライアントが過負荷になっている場合は、問題が発生する可能性があります。 これらの問題を回避するには、次の操作を行います。

1.  クライアントコンピューター上の CPU とメモリの使用状況を監視します。 CPU が90% を超えている場合は、ユーザーの数を減らします。

2.  メモリフットプリントが高い場合は、ページファイルのサイズが十分でないと、問題が発生する可能性があります。 コミットチャージがコンピューターの制限に達していないことを確認します。 メモリの制限を使用している場合は、ページファイルのサイズを大きくするか、ユーザーの数を減らすことを検討してください。

次の表に、LyncPerfTool の主要なパフォーマンスカウンターの一覧を示します。

**一般的な情報**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>パフォーマンス カウンター</strong></th>
<th><strong>説明</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>所要時間 (分単位)</p></td>
<td><p>プロセスが開始されてからの経過時間。</p></td>
</tr>
<tr class="even">
<td><p>アクティブなエンドポイント</p></td>
<td><p>サーバーに現在接続されているエンドポイントの数。</p></td>
</tr>
<tr class="odd">
<td><p>失敗したログオン</p></td>
<td><p>エンドポイントのサインインの失敗の合計数です。</p></td>
</tr>
<tr class="even">
<td><p>ログオン試行</p></td>
<td><p>エンドポイントのサインイン試行の合計数です。</p></td>
</tr>
<tr class="odd">
<td><p>エンドポイント切断</p></td>
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
<th><strong>パフォーマンス カウンター</strong></th>
<th><strong>説明</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>SetPresence 呼び出し</p></td>
<td><p>プレゼンス変更の試行回数の合計。 プレゼンス変更の種類が異なる場合は、SetPresence (プレゼンスの種類) Calls Performance Counter を参照してください。</p></td>
</tr>
<tr class="even">
<td><p>SetPresence に対する NNN 応答</p></td>
<td><p>サーバーから受信した nnn 応答コードの合計数です。</p></td>
</tr>
<tr class="odd">
<td><p>GetPresence 呼び出し</p></td>
<td><p>プレゼンス要求の取得の試行回数の合計。</p></td>
</tr>
<tr class="even">
<td><p>GetPresence に対する NNN 応答</p></td>
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
<th><strong>パフォーマンス カウンター</strong></th>
<th><strong>説明</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ABS フル/差分ファイルのダウンロードの試行</p></td>
<td><p>試行された完全または差分ファイルのダウンロード要求の総数。</p></td>
</tr>
<tr class="even">
<td><p>ABS 完全または差分ファイルのダウンロードに成功しました</p></td>
<td><p>試行された完全または差分ファイルのダウンロード要求の総数。</p></td>
</tr>
<tr class="odd">
<td><p>アドレス帳 Web クエリサービス関連カウンター</p></td>
<td><p>アドレス帳ファイルのダウンロード関連カウンター。</p></td>
</tr>
<tr class="even">
<td><p>ABS 呼び出しが試行されました</p></td>
<td><p>試行されたアドレス帳 Web クエリサービス要求の合計数。</p></td>
</tr>
<tr class="odd">
<td><p>ABS 呼び出しが成功しました</p></td>
<td><p>成功した応答コードを返したアドレス帳 Web クエリサービス要求の合計数です。</p></td>
</tr>
<tr class="even">
<td><p>ABS 呼び出しに失敗しました</p></td>
<td><p>エラー応答コードを返したアドレス帳 Web クエリサービス要求の合計数です。</p></td>
</tr>
</tbody>
</table>


**配布リスト (DL) の情報**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>パフォーマンス カウンター</strong></th>
<th><strong>説明</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>呼び出しの試行</p></td>
<td><p>試行された配布リスト展開 (DLX) web サービス要求の合計数。</p></td>
</tr>
<tr class="even">
<td><p>成功した通話</p></td>
<td><p>成功した応答コードを返した DLX web サービス要求の合計数です。</p></td>
</tr>
<tr class="odd">
<td><p>失敗した通話</p></td>
<td><p>エラー応答コードを返した DLX web サービス要求の合計数です。</p></td>
</tr>
</tbody>
</table>


**VoIP の基本情報**

以下のパフォーマンスカウンターは、これらのシナリオが有効になっている場合に、仲介サーバー、音声ビデオ会議サーバー、エッジサーバー、応答グループアプリケーション、および会議の自動応答の呼び出しを含む、すべてのボイスオーバー IP (VoIP) 呼び出しの番号を報告します。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>パフォーマンス カウンター</strong></th>
<th><strong>説明</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>アクティブな通話</p></td>
<td><p>現在実行中の着信/発信音声通話の合計数。</p></td>
</tr>
<tr class="even">
<td><p>通話の終了</p></td>
<td><p>着信/発信音声呼び出しの合計数が既に終了しています。</p></td>
</tr>
<tr class="odd">
<td><p>拒否した通話</p></td>
<td><p>辞退した着信音声通話の合計数です。</p></td>
</tr>
<tr class="even">
<td><p>着信/発信呼び出しの試行</p></td>
<td><p>試行された着信/発信音声通話の合計数。</p></td>
</tr>
<tr class="odd">
<td><p>確立された着信/発信呼び出し</p></td>
<td><p>確立された着信/発信音声通話の合計数。</p></td>
</tr>
<tr class="even">
<td><p>着信受信 NNN</p></td>
<td><p>サーバーから受信した nnn 応答コードの合計数です。</p></td>
</tr>
<tr class="odd">
<td><p>VoIP パススルー率 (%)</p></td>
<td><p>試行された合計通話数/合計試行回数。</p></td>
</tr>
</tbody>
</table>


**応答グループサービスの呼び出し情報**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>パフォーマンス カウンター</strong></th>
<th><strong>説明</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>アクティブな通話</p></td>
<td><p>応答グループアプリケーションへのアクティブな呼び出しの合計数。</p></td>
</tr>
<tr class="even">
<td><p>呼び出しの試行</p></td>
<td><p>試行された通話の合計数。</p></td>
</tr>
</tbody>
</table>


**インスタントメッセージング (IM) の呼び出し情報**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>パフォーマンス カウンター</strong></th>
<th><strong>説明</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>アクティブな通話</p></td>
<td><p>進行中の着信/発信インスタントメッセージング呼び出しの総数です。</p></td>
</tr>
<tr class="even">
<td><p>通話の終了</p></td>
<td><p>受信/送信されたインスタントメッセージング呼び出しの合計数が既に終了しています。</p></td>
</tr>
<tr class="odd">
<td><p>着信受信 NNN</p></td>
<td><p>サーバーから受信した nnn 応答コードの合計数です。</p></td>
</tr>
<tr class="even">
<td><p>受信/送信された IM メッセージ</p></td>
<td><p>すべてのセッションで受信または送信されたメッセージの合計数。</p></td>
</tr>
<tr class="odd">
<td><p>着信/発信呼び出しの試行</p></td>
<td><p>試行された着信/発信インスタントメッセージ呼び出しの合計数です。</p></td>
</tr>
<tr class="even">
<td><p>確立された着信/発信呼び出し</p></td>
<td><p>確立された着信/発信インスタントメッセージ呼び出しの合計数です。</p></td>
</tr>
</tbody>
</table>


**アプリ共有の呼び出し情報**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>パフォーマンス カウンター</strong></th>
<th><strong>説明</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>アクティブな通話</p></td>
<td><p>進行中または送信中のアプリケーション共有通話の合計数。</p></td>
</tr>
<tr class="even">
<td><p>通話の終了</p></td>
<td><p>受信/送信アプリケーション共有呼び出しの合計数が既に終了しています。</p></td>
</tr>
<tr class="odd">
<td><p>着信受信 NNN</p></td>
<td><p>サーバーから受信した nnn 応答コードの合計数です。</p></td>
</tr>
<tr class="even">
<td><p>着信/発信呼び出しの試行</p></td>
<td><p>試行された着信/送信アプリケーション共有の通話の合計数。</p></td>
</tr>
<tr class="odd">
<td><p>確立された着信/発信呼び出し</p></td>
<td><p>確立された着信/送信アプリケーション共有の呼び出しの合計数です。</p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


**CAA の呼び出し情報**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>パフォーマンス カウンター</strong></th>
<th><strong>説明</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>アクティブな通話</p></td>
<td><p>現在進行中の着信/発信公衆交換電話網 (PSTN) 通話の合計数。</p></td>
</tr>
<tr class="even">
<td><p>通話の終了</p></td>
<td><p>既に終了した着信/発信 PSTN 通話の合計数。</p></td>
</tr>
<tr class="odd">
<td><p>着信/発信呼び出しの試行</p></td>
<td><p>試行された着信/発信 PSTN 通話の合計数。</p></td>
</tr>
<tr class="even">
<td><p>確立された着信/発信呼び出し</p></td>
<td><p>確立された着信/発信 PSTN 呼び出しの合計数です。</p></td>
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
<th><strong>パフォーマンス カウンター</strong></th>
<th><strong>説明</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>アクティブなインスタントメッセージング会議</p></td>
<td><p>進行中のインスタントメッセージ会議の合計数。</p></td>
</tr>
<tr class="even">
<td><p>アクティブな音声ビデオ会議</p></td>
<td><p>進行中の音声ビデオ (A/V) 会議の合計数。</p></td>
</tr>
<tr class="odd">
<td><p>アクティブなアプリケーション共有会議</p></td>
<td><p>進行中のアプリケーション共有会議の合計数。</p></td>
</tr>
<tr class="even">
<td><p>参加者数</p></td>
<td><p>現在、電話会議に接続している参加者の総数です。</p></td>
</tr>
<tr class="odd">
<td><p>会議のスケジュールエラー</p></td>
<td><p>会議を計画しているときに失敗した回数の合計。</p></td>
</tr>
<tr class="even">
<td><p>会議の参加エラー</p></td>
<td><p>電話会議に接続しようとしたときに発生したエラーの合計数です。</p></td>
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
<th><strong>パフォーマンス カウンター</strong></th>
<th><strong>説明</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>成功した IMMCU の結合の合計数</p></td>
<td><p>参加したインスタントメッセージ会議の合計数。</p></td>
</tr>
<tr class="even">
<td><p>成功した DMCU 結合の合計数</p></td>
<td><p>参加した音声ビデオ会議の合計数。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

