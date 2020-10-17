---
title: 'Lync Server 2013: 管理者のアクセス許可のテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test admin permissions
ms:assetid: 5dda3efd-0f84-4848-819e-87b1551066b1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767945(v=OCS.15)
ms:contentKeyID: 63969607
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1653f2287e06db71f6e971a0a4f483b810734f2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519384"
---
# <a name="test-admin-permissions-in-lync-server-2013"></a>Lync Server 2013 での管理者権限のテスト

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-08-18_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>検証スケジュール</p></td>
<td><p>最初の Lync Server の展開後。 必要に応じて、アクセス許可に関連する問題が発生します。</p></td>
</tr>
<tr class="even">
<td><p>テストツール</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>必要なアクセス許可</p></td>
<td><p>Lync Server 管理シェルを使用してローカルに実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</p>
<p>Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには Test-CsOUPermission コマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。 このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsOUPermission&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

セットアッププログラムによって実行されたタスクの Lync Server 2013 1 をインストールすると、RTCUniversalUserAdmins グループに、ユーザー、コンピューター、連絡先、アプリケーションの連絡先、および InetOrg ユーザーを管理するために必要な Active Directory のアクセス許可が付与されます。 Active Directory セットアップでアクセス許可の継承を無効にした場合は、これらのアクセス許可を割り当てることができません。 その結果、RTCUniversalUserAdmins グループのメンバーは Lync Server エンティティを管理できなくなります。 これらの管理権限は、ドメイン管理者のみが使用できます。

Test-CsOUPermission コマンドレットは、Active Directory コンテナーに対して、ユーザー、コンピューター、およびその他のオブジェクトの管理に必要なアクセス許可が設定されているかどうかを確認します。 これらのアクセス許可が設定されていない場合は、 [Grant-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission) コマンドレットを実行することによって、この問題を解決できます。

Grant-CsOUPermission は、RTCUniversalUserAdmins グループのメンバーにのみアクセス許可を割り当てることに注意してください。 このコマンドレットを使用して、任意のユーザーまたはグループにアクセス許可を付与することはできません。 別のユーザーまたはグループにユーザー管理アクセス許可を付与する場合は、そのユーザーまたはグループを RTCUniversalUserAdmins グループに追加する必要があります。

OU アクセス許可の詳細については、「 [Lync Server 2013 のコンピューター、ユーザー、または InetOrgPerson コンテナーでのアクセス許可の継承が無効になっ](lync-server-2013-permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers.md)ています。」を参照してください。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

コンテナーに対して管理アクセス許可が設定されていることを確認するには、Test-CsOUPermission コマンドレットを実行し、その後にコンテナーの識別名、および検証するアクセス許可の種類を指定します。 たとえば、次のコマンドは、ユーザーのアクセス許可が OU ou = Redmond, dc = litwareinc, dc = com で設定されているかどうかを確認します。

    Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"

単一のコマンドを使用して複数のアクセス許可を確認するには、各アクセス許可の種類を二重引用符で囲み、コンマを使用してそれらの種類を区切ります。 たとえば、次のコマンドは、ユーザー、コンピューター、および連絡先のアクセス許可を確認します。

    Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"

詳細については、 [Test-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsOUPermission) コマンドレットのヘルプトピックを参照してください。

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を判断する

必要なアクセス許可が既に設定されている場合、Test-CsOUPermission は1単語の応答を返します。

正

必要なアクセス許可が設定されていない場合 Test-CsOUPermission は値 False を返します。 この値を見つけるには、少し時間を置いて検索する必要があるかもしれません。 通常は、いくつかの付随する警告に埋め込まれます。 以下に例を示します。

警告: アクセス制御エントリ (ACE) atl-fs-01 \\ RTCUniversalUserReadOnlyGroup; allow;ReadPropertyContainerInherit;子孫bf967aba-0de6-11d0-00aa003049e2;d819615a-4738 3b9b-b47e-f1bd8ee3aea4

警告: オブジェクト "OU = NorthAmerica, DC = litwareinc, DC = com" のアクセス制御エントリ (Ace) の \\ 準備ができていません。

False

警告: "Test-CsOUPermission" 処理は完了しましたが、警告があります。 この実行中に警告が記録されました。

警告: 詳細な結果は、「C: \\ Users \\ Admin \\ AppData \\ Local \\ Temp \\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html」にあります。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストが失敗した理由

Test-CsOUPermission が失敗した場合、通常は、指定されたアクセス許可が RTCUniversalUserAdmins グループに割り当てられていないことを意味します。 この問題を解決して、Grant-CsOUPermission コマンドレットを使用して必要なアクセス許可を割り当てることができます。 たとえば、次のコマンドを実行すると、ユーザー、連絡先、および inetOrgPersons の OU 権限が RTCUniversalUserAdmins グループに付与されます。

    Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"

詳細については、Grant-CsOUPermission コマンドレットのヘルプトピックを参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

