---
title: 'Lync Server 2013: PSTN 電話の通話ルーティングのテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing PSTN phone call routing
ms:assetid: 301dd44d-03e9-41cd-9722-54e00365aa45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727302(v=OCS.15)
ms:contentKeyID: 63969598
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2dabe54fb2ba4df864d172015efb62ef161c77cb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745597"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-pstn-phone-call-routing-in-lync-server-2013"></a>Lync Server 2013 での PSTN 電話による通話ルーティングのテスト

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-11-01_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>確認のスケジュール</p></td>
<td><p>[毎日]</p></td>
</tr>
<tr class="even">
<td><p>テストツール</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>必要なアクセス許可</p></td>
<td><p>Lync Server 管理シェルを使用してローカルで実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</p>
<p>Windows PowerShell のリモートインスタンスを使って実行する場合は、 <strong>CsInterTrunkRouting</strong>コマンドレットを実行するためのアクセス許可が与えられている RBAC の役割をユーザーに割り当てる必要があります。 このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsInterTrunkRouting&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

**CsInterTrunkRouting**コマンドレットは、通話がある SIP から別の SIP にルーティングできることを確認します。 これを行うには、コマンドレットに電話番号とトランク構成を指定します。 **CsInterTrunkRouting**は、指定された番号について、一致するルートと一致する PSTN の使用状況を報告します。 Trunks には、指定した電話番号と一致する番号パターンがあり、trunks が少なくとも1つの PSTN 使用を共有している場合のみ、trunks 間で通話をルーティングできます。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

次に示すコマンドは、ユーザーが Redmond サイトのトランク構成設定を使用して電話番号1-206-555-1219 に発信できるように、一致するルートと一致する電話の使用状況を返します。

    $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
    
    Test-CsInterTrunkRouting -TargetNumber "tel:+12065551219" -TrunkConfiguration $trunk

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を確認する

通話を別の SIP にルーティングできる場合は、次のような出力が表示されます。

FirstMatchingRoute MatchingUsage MatchingRoutes

\------------------ ------------- --------------

RedmondRoute LocalUsage {RedmondRoute}

テストが成功しなかった場合は、次のような出力が表示されます。

CsInterTrunkRouting: パラメーターでの引数変換を処理できません

'TrunkConfiguration'. TrunkConfigurationsetting (パラメーター) が無効です。 を指定する

有効な設定 (パラメーター) を入力してからやり直してください。

行: 1 char:79

\+CsInterTrunkRouting-TargetNumber "tel: + 12065551219"

\-TrunkConfiguration $t...

\+

~~

\+カテゴリ情報: InvalidData: (:)\[CsInterTrunkRouting\]、Par

Ameterbindingargumentの例外

\+FullyQualifiedErrorId: Parameterargumentトランスエラー、Microsoft R

tc.TestOcsInterTrunkRoutingCmdlet を管理します。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストに失敗した可能性がある理由

次に **、テスト-CsInterTrunkRouting**が失敗する可能性がある一般的な理由を示します。

  - 無効なパラメーターが指定されました。 トランクがまだ正しく構成されておらず、指定されたターゲット番号が間違っているか、無効である可能性があります。

</div>

<div>

## <a name="see-also"></a>関連項目


[Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk)  
[Get-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

