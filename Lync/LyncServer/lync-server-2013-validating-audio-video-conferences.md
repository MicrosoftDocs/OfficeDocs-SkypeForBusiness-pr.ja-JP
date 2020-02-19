---
title: 'Lync Server 2013: 音声ビデオ会議の検証'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating audio/video conferences
ms:assetid: 6c8c422a-d501-42cb-820b-b002f9b2250b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720915(v=OCS.15)
ms:contentKeyID: 63969615
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: babd9ce23a9d7e80875fc455e92c51ea9bd47493
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42113430"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="validating-audiovideo-conferences-in-lync-server-2013"></a>Lync Server 2013 での音声ビデオ会議の検証

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-06-05_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>検証スケジュール</p></td>
<td><p>毎日</p></td>
</tr>
<tr class="odd">
<td><p>テストツール</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="even">
<td><p>必要なアクセス許可</p></td>
<td><p>Lync Server 管理シェルを使用してローカルに実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</p>
<p>Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには、テスト-CsAVConference コマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。 このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAVConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

テスト CsAVConference コマンドレットは、2つのテストユーザーが音声ビデオ (A/V) 会議に参加できるかどうかをチェックします。 コマンドレットを実行すると、2人のユーザーがシステムにログオンします。 正常にログオンした後、最初のユーザーが音声ビデオ会議を作成し、2番目のユーザーがその会議に参加するのを待ちます。 データを簡単に交換した後、会議が削除され、2つのテストユーザーがログオフします。

テスト-CsAVConference 会議では、2つのテストユーザー間で実際の音声ビデオ会議が行われないことに注意してください。 代わりに、このコマンドレットは、2人のユーザーがそのような会議を行うために必要なすべての接続を確立できることを確認します。

このコマンドのその他の例については[、「テスト-CsAVConference 会議](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference)」を参照してください。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

テスト CsAVConference コマンドレットは、事前に構成されたテストアカウントのペア (「Lync Server テストを実行するためのテストアカウントの設定」を参照)、または Lync Server が有効になっている任意の2人のアカウントのいずれかを使用して実行できます。 このチェックをテストアカウントを使用して実行するには、テストする Lync Server プールの FQDN を指定するだけで済みます。 次に例を示します。

    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com"

実際のユーザーアカウントを使用してこのチェックを実行するには、2つの Windows PowerShell credentials オブジェクト (アカウント名とパスワードを含むオブジェクト) を各アカウントに作成する必要があります。 次に、これらの資格情報オブジェクトと、2つのアカウントの SIP アドレスを指定する必要があります。

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

詳細については、「 [Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference)コマンドレットのヘルプドキュメント」を参照してください。

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を判断する

指定したユーザーが音声ビデオ会議を正常に完了できた場合は、次のような出力が得られます。 Result プロパティは Success としてマークされてい**ます。**

TargetFqdn: atl-cs-001.litwareinc.com

結果: 成功

待機時間:00:00: 02.6841765

エラー

分析

ユーザーが会議を完了できない場合、結果は失敗として表示され、エラーと診断のプロパティに追加情報が記録されます。

TargetFqdn: atl-cs-001.litwareinc.com

結果: エラー

待機時間: 00:00:00

エラー: 404、見つかりません

診断: ErrorCode = 4005, Source = 001.litwareinc.com,

Reason = 宛先 URI が SIP に対して有効になっていないか、または使用されていません

ない.

DiagnosticHeader ()

たとえば、1つ以上のユーザーアカウントが存在しないため、またはアカウントが Lync Server に対して有効になっていないために、このテストが失敗したことが示されています。 次のようなコマンドを実行することによって、2つのテストアカウントが存在するかどうか、および Lync Server が有効になっているかどうかを確認できます。

    "sip:kenmyer@litwareinc.com","sip:davidlongmire@litwareinc.com" | Get-CsUser | Select-Object SipAddress, enabled

テスト-CsAVConference が失敗した場合は、次のように詳細なパラメーターを含めて、テストを再実行することをお勧めします。

    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Verbose パラメーターが Test に含まれている場合、指定されたユーザーが AV 電話会議に参加できるかどうかを確認したときに試行された各アクションのステップバイステップのアカウントが返されます。 たとえば、テストが失敗し、次の診断が表示されるとします。

ErrorCode = 1008, Source = accessproxy, Reason = DNS SRV レコードを解決できません

Verbose パラメーターを使用してテストを再実行すると、次のような出力が返されます。

VERBOSE: ' Register ' アクティビティが開始されました。

登録要求の送信:

ターゲット Fqdn = atl-cs-001.litwareinc.com

ユーザー Sip アドレス = sip:davidlongmire@litwareinc.com

レジストラーポート = 5061。

認証の種類 ' Trusted ' が選択されています。

' Register ' アクティビティが開始されました。

登録要求の送信:

ターゲット Fqdn = atl-cs-001.litwareinc.com

ユーザー Sip アドレス = sip:kenmyer@litwareinc.com

レジストラーポート = 5061。

認証の種類 ' Trusted ' が選択されています。

例外 ' エンドポイントを登録できませんでした。 具体的な理由については、「エラーコード」を参照してください。 ' ワークフロー中に発生した

その出力の最後の行は、ユーザー sip:kenmyer@litwareinc.com が Lync Server に登録できなかったことを示しています。 これは、SIP アドレス sip:kenmyer@litwareinc.com が有効であることと、関連付けられたユーザーが Lync Server に対して有効になっていることを確認する必要があることを意味します。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストが失敗した理由

次に、テスト-CsAVConference が失敗する主な理由を示します。

  - 無効なユーザーアカウントが指定されました。 ユーザーアカウントが存在することを確認するには、次のようなコマンドを実行します。
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - ユーザーアカウントは有効ですが、アカウントは現在 Lync Server に対して有効になっていません。 ユーザーアカウントが Lync Server に対して有効になっていることを確認するには、次のようなコマンドを実行します。
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Enabled プロパティが False に設定されている場合は、ユーザーが Lync Server に対して有効になっていないことを意味します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

