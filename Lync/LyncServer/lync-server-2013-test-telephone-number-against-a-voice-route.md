---
title: 'Lync Server 2013: ボイスルートに対して電話番号をテストする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test telephone number against a voice route
ms:assetid: 9a77ed6d-9394-4bef-9344-3d91b6959b97
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725211(v=OCS.15)
ms:contentKeyID: 63969631
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ed50971c9656d454a44eeee627de95c187ef008f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848478"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-telephone-number-against-a-voice-route-in-lync-server-2013"></a>Lync Server 2013 でボイスルートに対して電話番号をテストする

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
<p>Windows PowerShell のリモートインスタンスを使って実行する場合は、CsVoiceRoute コマンドレットを実行するためのアクセス許可が与えられている RBAC の役割をユーザーに割り当てる必要があります。 このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceRoute&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

ボイスルーティングはボイスポリシーと共に機能し、PSTN ネットワークへのエンタープライズ音声通話をルーティングするのに役立ちます。 各ボイスルートには、特定のボイスルートを経由してルーティングされる電話番号を識別する正規表現 (番号パターン) が含まれています。ルートは、この正規表現に一致する電話番号を処理することができます。 たとえば、ボイスルートには、10桁の数値を処理できる正規表現が含まれている場合があります。 つまり、このルートは、次のような電話番号を処理できることを意味します。

  - 2065551219

このルートでは、次の2つの番号のいずれも処理できません。どちらの場合も、10桁の数字は使用できません。

  - 5551219

  - 12065551219

CsVoiceRoute コマンドレットは、指定された電話番号が特定のボイスルートでルーティングできるかどうかを確認します。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

指定した電話番号をルーティングするためのボイスルートの機能を確認するのは、2段階のプロセスです。 最初に、CsVoiceRoute コマンドレットを使用してそのボイスルートのインスタンスを返す必要があります。その後、CsVoiceRoute コマンドレットを使用して、対象の電話番号を処理するルートの機能を確認する必要があります。 たとえば、次のコマンドは、RedmondVoiceRoute ボイスルートが電話番号2065551219をルーティングできるかどうかを確認します。

`Get-CsVoiceRoute -Identity "RedmondVoiceRoute" | Test-CsVoiceRoute -TargetNumber "2065551219"`

電話番号は、ユーザーがその番号をダイヤルすることが期待される場合に入力する必要があることに注意してください。 たとえば、ダイヤルするときに、ユーザーが国コードと市外局番を含めないようにする場合は、次のような構文を使用します。

`-TargetNumber "5551219"`

この場合、ターゲット番号は国コードと市外局番の両方を残します。

1つのコマンドを使用して、指定したターゲット番号に対するすべての音声ルートをテストするには、次のような構文を使用します。

`Get-CsVoiceRoute | Test-CsVoiceRoute -TargetNumber "2065551219"`

詳細については、「CsVoiceRoute コマンドレットのヘルプドキュメント」を参照してください。

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を確認する

ボイスルートがターゲットの電話番号をルーティングできる場合は、CsVoiceRoute コマンドレットでは値 True が返されます。

MatchesPattern

\--------------

True

つまり、ルートではターゲット番号と同様の数値を処理できることを意味します。 ボイスルートがターゲット番号を処理できない場合、CsVoiceRoute は値 False を返します。

MatchesPattern

\--------------

False

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストに失敗した可能性がある理由

ボイスルートをテストするとき、"failure" は相対的な用語です。 この場合は、ルートが何らかの "壊れている" ということではなく、ルートがターゲット番号を処理できないことを意味します。 これは、ボイスルートが正しく構成されていないことが原因である可能性があります。 このパターンを使って番号を処理することを意図していないルートの場合もあります。 たとえば、特定のルート経由で他の国への通話をルーティングしたくない場合は、国コードを含むすべての電話番号を拒否するようにルーティングが構成されている可能性があります。 CsVoiceRoute が True を返すことが予想される場合は、正しい値を入力したことを確認します。 使用した場合は、次のようなコマンドを使用して、ルートに構成されている番号パターンを表示します。

`Get-CsVoiceRoute -Identity "RedmondVoiceRoute" | Select-Object NumberPattern`

</div>

<div>

## <a name="see-also"></a>関連項目


[テスト-CsVoiceRoute](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceRoute)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

