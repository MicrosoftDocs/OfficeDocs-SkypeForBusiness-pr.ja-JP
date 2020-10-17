---
title: 主要住所の住所ガイドに対して都市の住所をテストする
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing civic addresses against the master street address guide
ms:assetid: dc680de9-2a0f-4fd3-a99e-9bab0bc30ae5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690132(v=OCS.15)
ms:contentKeyID: 63969657
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2d03647df3752860c114a16967a3bea5271a89d4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527814"
---
# <a name="testing-civic-addresses-against-the-master-street-address-guide-in-lync-server-2013"></a>Lync Server 2013 の主要な住所の住所ガイドに対して都市の住所をテストする

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



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
<p>Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには Test-CsRegistration コマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。 このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLisCivicAddress &quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

Test-CsLisCivicAddress コマンドレットは、場所情報サービス (LIS) データベースに追加された場所を確認するために使用されます。 このコマンドレットは、E9-1-1 ネットワークルーティングプロバイダーに属している主要な住所の住所ガイド (MSAG) にある場所を比較することで機能します。 ネットワークルーティングプロバイダーがない場合、またはプロバイダーに到達できない場合、テストは失敗します。

コマンドにオプションのスイッチパラメーター UpdateValidationStatus を追加すると、テストを渡すアドレスごとに、対応する MSAGValid database プロパティが True に設定されます。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

Test-CsLisCivicAddress コマンドレットを使用して、個々のアドレスをテストしたり、複数のアドレスをテストしたりできます。 たとえば、次のコマンドは、Redmond、ワシントンにある1つのアドレスをテストします。

    Test-CsLisCivicAddress -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName Main -StreetSuffix St -PostDirectional "" -City Redmond -State WA -PostalCode 98052 -Country US -UpdateValidationStatus

次のコマンドは、LIS データベースに現在含まれているすべてのアドレスをテストします。

    Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus

詳細については、「 [Test-CsRegistration](https://technet.microsoft.com/library/Gg412737(v=OCS.15)) コマンドレットのヘルプドキュメント」を参照してください。

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を判断する

Test-CsLisCivicAddress は、指定されたアドレスに対して、成功または失敗の報告を返します。 アドレスが見つからない場合、またはサービスプロバイダーに接続できない場合、アドレステストは失敗します。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストが失敗した理由

Test-CsLisCivicAddress が失敗する可能性のある一般的な理由を次に示します。

  - LIS サービスプロバイダーを使用できない可能性があります。 Get-CsLisConfiguration コマンドレットを実行して、LIS サービスプロバイダーの URL を取得できます。
    
        Get-CsLisConfiguration 
    
    その URL に ping を実行して、サービスプロバイダーが利用可能であることを確認できます。

</div>

</div>

<span> </span>

</div>

</div>

</div>

