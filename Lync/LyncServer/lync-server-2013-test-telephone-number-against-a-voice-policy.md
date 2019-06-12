---
title: 'Lync Server 2013: ボイスポリシーに対して電話番号をテストする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test telephone number against a voice policy
ms:assetid: 30c51700-17c6-4c57-891a-8d5ec30b50ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725207(v=OCS.15)
ms:contentKeyID: 63969596
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a7a1e24a07a0f6e1e985c9fc42f7468838074d3a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848489"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-telephone-number-against-a-voice-policy-in-lync-server-2013"></a>Lync Server 2013 でボイスポリシーに対して電話番号をテストする

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-05-20_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>確認のスケジュール</p></td>
<td><p>毎月</p></td>
</tr>
<tr class="even">
<td><p>テストツール</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>必要なアクセス許可</p></td>
<td><p>Lync Server 管理シェルを使用してローカルで実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</p>
<p>Windows PowerShell のリモートインスタンスを使って実行する場合は、CsVoicePolicy コマンドレットを実行するためのアクセス許可が与えられている RBAC の役割をユーザーに割り当てる必要があります。 このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoicePolicy&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

エンタープライズボイスユーザーが公衆交換電話網 (PSTN) のヒンジを介して発信電話を発信する機能 (大きな部分) は、次の3つの点です。

  - ユーザーに割り当てられている音声ポリシー。

  - Lync Server から PSTN ネットワークへの通話をルーティングするために使用される音声ルート。

  - PSTN の使用状況。ボイスポリシーをボイスルートに接続する Lync Server プロパティ。

PSTN の使用は特に重要です。ボイスポリシーをボイスルートに接続するプロパティです。 (音声ポリシーと音声ルートは、少なくとも1つの PSTN が一般的に使用されている場合、接続されていると言われます)。ボイスポリシーは、PSTN の使用を指定せずに構成できます。 その場合、そのポリシーを割り当てられたユーザーは、PSTN ネットワーク経由での発信通話を行うことができません。 同様に、少なくとも1つの PSTN 使用量が指定されていないボイスルーティングでは、通話を PSTN ネットワークにルーティングすることはできません。

CsVoicePolicy コマンドレットは、指定された音声ポリシーの使用状況が PSTN であり、少なくとも1つのボイスルートによって使用が共有されていることを確認します。 テスト CsVoicePolicy によって検証が正常に実行された場合、コマンドレットは、最初に見つかった有効なボイスルートの名前を報告し、そのルートにポリシーを接続する PSTN 使用の名前も返します。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

CsVoicePolicy コマンドレットを実行するには、まず CsVoicePolicy コマンドレットを使用して、テストする音声ポリシーのインスタンスを取得する必要があります。その後、そのインスタンスを CsVoicePolicy にパイプする必要があります。 次に例を示します。

`Get-CsVoicePolicy -Identity "Global" | Test-CsVoicePolicy -TargetNumber "+12065551219"`

このコマンドは、CsVoicePolicy を使って音声ポリシーインスタンスを取得しないため、失敗します。

`Test-CsVoicePolicy -TargetNumber "+12065551219" -VoicePolicy "Global"`

すべての音声ポリシーを指定の電話番号に対して確認する場合は、次のようなコマンドを使用します。

`Get-CsVoicePolicy | Test-CsVoicePolicy -TargetNumber "+12065551219"`

TargetNumber は、E.i 形式で指定する必要があることに注意してください。 CsVoicePolicy は、電話番号を * 164 形式で正規化または翻訳しようとしません。

詳細については、「CsVoicePolicy コマンドレットのヘルプドキュメント」を参照してください。

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を確認する

ボイスポリシーが一致する音声ルートと、一致する PSTN 使用の両方を見つけることができる場合は、ルートと利用状況の両方が画面に表示されます。

FirstMatchingRoute MatchingUsage

\------------------ -------------

RedmondVoiceRoute RedmondPstnUsage

適切な音声ルートまたは適切な PSTN 使用が見つからない場合は、空白のプロパティ値が画面に表示されます。

FirstMatchingRoute MatchingUsage

\------------------ -------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストに失敗した可能性がある理由

CsVoicePolicy によって検索結果が返されない場合は、ボイスポリシーがボイスルートで PSTN 使用状況を共有していない可能性があります。 これを確認するには、次のようなコマンドレットを使用して、ボイスポリシーに割り当てられている PSTN の使用状況を確認します。

`Get-CsVoicePolicy -Identity "Global" | Select-Object PstnUsages | Format-List`

次に、このコマンドを実行して、PSTN 使用状況が各ボイスルートに割り当てられていることを確認します。

`Get-CsVoiceRoute | Select-Object Identity, PstnUsages`

一致するものが見つかった場合 (つまり、音声ポリシーで1つ以上の PSTN 使用を共有する1つ以上の音声ルートが表示されている場合) は、CsVoiceRoute コマンドレットを実行して、ボイスルートが指定した電話番号をダイヤルできることを確認します。

</div>

<div>

## <a name="see-also"></a>関連項目


[テスト-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/Test-CsVoicePolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

