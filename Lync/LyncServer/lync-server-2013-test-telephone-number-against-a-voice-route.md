---
title: 'Lync Server 2013: ボイスルートに対して電話番号をテストする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test telephone number against a voice route
ms:assetid: 9a77ed6d-9394-4bef-9344-3d91b6959b97
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725211(v=OCS.15)
ms:contentKeyID: 63969631
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5476d47d0aac550d048e35e617d6d342084ccd75
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194540"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-telephone-number-against-a-voice-route-in-lync-server-2013"></a>Lync Server 2013 でのボイスルートに対して電話番号をテストする

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-05-20_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>検証スケジュール</p></td>
<td><p>毎月</p></td>
</tr>
<tr class="even">
<td><p>テストツール</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>必要なアクセス許可</p></td>
<td><p>Lync Server 管理シェルを使用してローカルに実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</p>
<p>Windows PowerShell のリモートインスタンスを使用して実行する場合は、Get-csvoiceroute コマンドレットを実行するためのアクセス許可を持つ RBAC の役割がユーザーに割り当てられている必要があります。 このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceRoute&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

音声ルートは音声ポリシーと連携して、PSTN ネットワークへのエンタープライズ Voip 通話のルーティングを支援します。 各ボイスルートには、特定のボイスルートを経由してルーティングされる電話番号を識別する正規表現 (番号パターン) が含まれています。この正規表現に一致するすべての電話番号は、ルートによって処理できます。 たとえば、ボイスルートには、10桁の番号を処理できる正規表現があります。 つまり、ルートは次のような電話番号を処理することができます。

  - 2065551219

このルートは、次の2つの番号のどちらかを処理することはできません。これは、10桁の数字です。

  - 5551219

  - 12065551219

Get-csvoiceroute コマンドレットでは、指定したボイスルートが指定した電話番号をルーティングできるかどうかを確認します。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

指定した電話番号をルーティングするための音声ルートの機能を確認することは、2つの手順で行います。 最初に、Get-csvoiceroute コマンドレットを使用してその音声ルートのインスタンスを取得した後、Get-csvoiceroute コマンドレットを使用して、対象の電話番号を処理するためにそのルートが機能していることを確認する必要があります。 たとえば、次のコマンドは、RedmondVoiceRoute ボイスルートが電話番号2065551219をルーティングできるかどうかを確認します。

`Get-CsVoiceRoute -Identity "RedmondVoiceRoute" | Test-CsVoiceRoute -TargetNumber "2065551219"`

電話番号は、ユーザーがその番号をダイヤルすることが予想されるとおりに入力する必要があることに注意してください。 たとえば、ユーザーがダイヤルするときに国コードと市外局番を含めないようにするには、次のような構文を使用します。

`-TargetNumber "5551219"`

この場合、ターゲット番号は、国コードと市外局番の両方を残します。

単一のコマンドを使用して、指定したターゲット番号に対するすべての音声ルートをテストするには、次のような構文を使用します。

`Get-CsVoiceRoute | Test-CsVoiceRoute -TargetNumber "2065551219"`

詳細については、Get-csvoiceroute コマンドレットのヘルプドキュメントを参照してください。

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を判断する

音声ルートが対象の電話番号をルーティングできる場合は、Get-csvoiceroute コマンドレットでは、値 True が返されます。

MatchesPattern

\--------------

はい

これは、ルートがターゲット番号と同様の番号を処理できることを意味します。 音声ルートがターゲット番号を処理できない場合、Get-csvoiceroute は値 False を返します。

MatchesPattern

\--------------

False

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストが失敗した理由

音声ルートをテストする場合、"failure" は相対用語です。 この場合、ルートがなんらかの "壊れている" ということではなく、ルートがターゲット番号を処理できないことを意味します。 音声ルートが正しく構成されていない可能性があります。 また、このパターンを使用して、ルートが数値を処理することを意図したものではないことも考えられます。 たとえば、特定のルートを介して他の国への通話をルーティングしない場合は、国コードを含むすべての電話番号を拒否するように構成されている可能性があります。 Get-csvoiceroute が True を返すことが予想されるときに False が返された場合は、ターゲット番号を正しく入力したかどうかを確認します。 実行した場合は、次のようなコマンドを使用して、ルートに対して構成されている番号パターンを表示します。

`Get-CsVoiceRoute -Identity "RedmondVoiceRoute" | Select-Object NumberPattern`

</div>

<div>

## <a name="see-also"></a>関連項目


[Get-csvoiceroute](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceRoute)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

