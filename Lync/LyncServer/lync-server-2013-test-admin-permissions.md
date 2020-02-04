---
title: 'Lync Server 2013: 管理者権限をテストする'
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
ms.openlocfilehash: d4543501d668b61bbb90073c80c4e85373341d93
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746477"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-admin-permissions-in-lync-server-2013"></a>Lync Server 2013 で管理者権限をテストする

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-08-18_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>確認のスケジュール</p></td>
<td><p>最初の Lync Server の展開後。 必要に応じて、アクセス許可に関連する問題が発生します。</p></td>
</tr>
<tr class="even">
<td><p>テストツール</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>必要なアクセス許可</p></td>
<td><p>Lync Server 管理シェルを使用してローカルで実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</p>
<p>Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには、CsOUPermission コマンドレットを実行するためのアクセス許可が与えられた RBAC の役割を割り当てる必要があります。 このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsOUPermission&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

セットアッププログラムによって実行されたタスクの Lync Server 2013 1 をインストールすると、RTCUniversalUserAdmins グループにユーザー、コンピューター、連絡先、アプリケーションの連絡先、および InetOrg の管理に必要な Active Directory のアクセス許可が与えられます。 Active Directory で権限の継承を無効にしている場合は、セットアップでそれらのアクセス許可を割り当てることはできません。 この結果、RTCUniversalUserAdmins グループのメンバーは Lync Server のエンティティを管理することはできません。 これらの管理権限は、ドメイン管理者のみが利用できます。

ユーザー、コンピューター、その他のオブジェクトを管理するために必要な権限が Active Directory コンテナーに設定されているかどうかを確認するため、CsOUPermission のテストコマンドレットを確認します。 これらのアクセス許可が設定されていない場合は、 [Grant-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission)コマンドレットを実行することで、この問題を解決できます。

ただし、権限の付与は、RTCUniversalUserAdmins グループのメンバーに対してのみ権限を割り当てることができます。 このコマンドレットを使用して、任意のユーザーまたはグループにアクセス許可を付与することはできません。 別のユーザーまたはグループにユーザー管理のアクセス許可を与える必要がある場合は、そのユーザー (またはグループ) を RTCUniversalUserAdmins グループに追加する必要があります。

OU のアクセス許可の詳細については、「 [Lync Server 2013 のコンピューター、ユーザー、または InetOrgPerson コンテナーでアクセス許可の継承が無効になっている](lync-server-2013-permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers.md)」を参照してください。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

コンテナーに管理権限が設定されていることを確認するには、CsOUPermission コマンドレットを実行し、その後に、コンテナーの識別名と確認するアクセス許可の種類を指定します。 たとえば、次のコマンドは、ユーザー権限が OU ou で設定されているかどうかを確認します。 Redmond、dc = litwareinc、dc = com:

    Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"

1つのコマンドを使用して複数のアクセス許可を確認するには、それぞれのアクセス許可の種類を引用符で囲んで囲み、コンマを使用してそれらの型を区切ります。 たとえば、次のコマンドは、ユーザー、コンピューター、および連絡先のアクセス許可を確認します。

    Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"

詳細については、「 [CsOUPermission のテスト](https://docs.microsoft.com/powershell/module/skype/Test-CsOUPermission)」コマンドレットのヘルプトピックを参照してください。

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を確認する

必要な権限が既に設定されている場合は、次のようにして、Test-CsOUPermission は1単語の応答を返します。

True

必要なアクセス許可が設定されていない場合は、"False" という値が返されます。 この値を検索するには、少し時間がかかる場合があります。 通常は、いくつかの関連する警告内に埋め込まれます。 次に例を示します。

警告: アクセス制御エントリ (ACE) atl-cs-001\\RTCUniversalUserReadOnlyGroup;許可ReadProperty;ContainerInherit;フォルダーbf967aba-11d0-00aa003049e2;d819615a-3b9b-4738-b47e-f1bd8ee3aea4

警告: オブジェクト "OU = NorthAmerica, DC = atl-\\litwareinc, dc = com" のアクセス制御エントリ (Ace) の準備ができていません。

False

警告: "Test-CsOUPermission" 処理は警告で完了しています。 この実行中に警告が記録されました。

警告: 詳細\\な結果は "C: Users\\管理者\\向け AppData\\Local\\Temp\\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de" にあります。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストに失敗した可能性がある理由

RTCUniversalUserAdmins のテストに失敗した場合、通常は、指定したアクセス許可がグループに割り当てられていないことを意味します。 この問題を解決して、必要なアクセス許可を割り当てるには、アクセス許可の付与コマンドレットを使用します。 たとえば、次のコマンドを実行すると、ユーザー、連絡先、inetOrgPersons に対して、RTCUniversalUserAdmins グループに OU 権限が付与されます。

    Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"

詳細については、「Grant-CsOUPermission」コマンドレットのヘルプトピックを参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

