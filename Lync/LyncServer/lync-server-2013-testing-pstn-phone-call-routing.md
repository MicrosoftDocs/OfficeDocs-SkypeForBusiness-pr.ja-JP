---
title: 'Lync Server 2013: PSTN 通話のルーティングのテスト'
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
ms.openlocfilehash: abdb6796139ddc4be2b8ea24aa9bfeb19f745373
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193927"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-pstn-phone-call-routing-in-lync-server-2013"></a>Lync Server 2013 での PSTN 通話のルーティングのテスト

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-11-01_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>検証スケジュール</p></td>
<td><p>毎日</p></td>
</tr>
<tr class="even">
<td><p>テストツール</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>必要なアクセス許可</p></td>
<td><p>Lync Server 管理シェルを使用してローカルに実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</p>
<p>Windows PowerShell のリモートインスタンスを使用して実行する場合は、 <strong>test-csintertrunkrouting</strong>コマンドレットを実行するためのアクセス許可を持つ RBAC の役割がユーザーに割り当てられている必要があります。 このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsInterTrunkRouting&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

**Test-csintertrunkrouting**コマンドレットは、呼び出しがある SIP から別の SIP にルーティングできることを検証します。 これを行うために、コマンドレットには電話番号とトランク構成が与えられます。 **Test-csintertrunkrouting**は、指定された番号について、一致するルートと一致する PSTN 使用法を報告します。 トランクには、指定された電話番号に一致する番号パターンがあり、トランクが少なくとも1つの PSTN 使用法を共有している場合にのみ、トランク間で通話をルーティングできることに注意してください。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

次に示すコマンドは、ユーザーが Redmond サイトのトランク構成設定を使用して電話番号1-206-555-1219 を呼び出せるようにする、一致するルートと一致する電話使用法を返します。

    $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
    
    Test-CsInterTrunkRouting -TargetNumber "tel:+12065551219" -TrunkConfiguration $trunk

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を判断する

通話がある SIP から別の SIP にルーティングできる場合は、次のような出力が得られます。

FirstMatchingRoute MatchingUsage MatchingRoutes

\------------------ ------------- --------------

RedmondRoute LocalUsage {RedmondRoute}

テストが成功しなかった場合は、次のような出力が得られます。

Test-csintertrunkrouting: パラメーターの引数変換を処理できません

' Microsoft.rtc.management.writableconfig.settings.trunkconfiguration.trunkconfiguration 型 '。 TrunkConfigurationsetting (パラメーター) が正しくありません。 を指定する

有効な設定 (パラメーター) を指定してから、もう一度実行してください。

行: 1 文字:79

\+Test-csintertrunkrouting-TargetNumber "tel: + 12065551219 など"

\-Microsoft.rtc.management.writableconfig.settings.trunkconfiguration.trunkconfiguration 型 $t

\+

~~

\+カテゴリ情報: InvalidData: (:)\[Test-csintertrunkrouting\]、Par

Ameterbindingargumentの例外

\+FullyQualifiedErrorId: Parameterargumentトランスエラー、Microsoft R

c.TestOcsInterTrunkRoutingCmdlet の管理

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストが失敗した理由

**Test-csintertrunkrouting**が失敗する可能性のある一般的な原因を次に示します。

  - 無効なパラメーターを指定しました。 トランクが正しく構成されていない可能性があり、指定されたターゲット番号が正しくないか、無効である可能性があります。

</div>

<div>

## <a name="see-also"></a>関連項目


[取得-CsTrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk)  
[Get-cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

