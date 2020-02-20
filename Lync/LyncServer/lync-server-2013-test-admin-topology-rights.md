---
title: 'Lync Server 2013: 管理者トポロジのテスト権限'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test admin topology rights
ms:assetid: 0c03b7fd-449a-47ad-8263-ce811164cbce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767943(v=OCS.15)
ms:contentKeyID: 63969575
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5aaeef1799ee2e35746f659ce451160854a25d89
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141743"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-admin-topology-rights-in-lync-server-2013"></a>Lync Server 2013 での管理者トポロジのテスト権限

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2016-12-08_


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
<p>Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには、テスト用の CsSetupPermission コマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。 このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsSetupPermission&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

既定では、ドメイン管理者のみが Lync Server トポロジを有効にし、Lync Server インフラストラクチャに大きな変更を加えることができます。 ドメイン管理者と Lync Server 管理者が同一である限り、これは問題になりません。多くの組織では、Lync Server 管理者はドメイン全体に対する管理権限を保持していません。 既定では、これらの管理者 (RTCUniversalServerAdmins グループのメンバーとして定義されている) が Lync Server トポロジを変更することはできません。 RTCUniversalServerAdmins グループのメンバーがトポロジを変更できるようにするには、必要な Active Directory アクセス許可を付与するために、 [Grant-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission)コマンドレットを使用する必要があります。

Test-CsSetupPermission コマンドレットは、Lync Server またはそのコンポーネントのいずれかをインストールするために必要なアクセス許可が、指定した Active Directory コンテナーに対して構成されているかどうかを確認します。 アクセス許可が割り当てられていない場合は、Grant-CsSetupPermission コマンドレットを実行して、RTCUniversalServerAdmins グループのメンバーに Lync Server をインストールして有効にする権限を与えることができます。

<div>


> [!NOTE]  
> Grant-CsSetupPermission によって割り当てられるアクセス許可の詳細な一覧については、ブログ投稿<A href="https://blogs.technet.com/b/jenstr/archive/2011/02/07/grant-cssetuppermission-and-grant-csoupermission.aspx">付与-cssetuppermission および grant-Cssetuppermission</A>を参照してください。



</div>

</div>

<div>

## <a name="running-the-test"></a>テストの実行

Active Directory コンテナーにセットアップのアクセス許可が割り当てられているかどうかを判断するには、Test-CsSetupPermission コマンドレットを呼び出します。 確認するコンテナーの識別名を指定します。 たとえば、次のコマンドは、コンテナー ou = CsServers, dc = litwareinc, dc = com: に対するセットアップのアクセス許可を確認します。

    Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"

詳細については、 [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission)コマンドレットのヘルプトピックを参照してください。

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を判断する

必要なアクセス許可が Active Directory コンテナーに既に設定されている場合、このコマンドレットは True という値を返します。

はい

権限が設定されていない場合、Test-CsSetupPermission は値 False を返します。 この値は通常、多くの警告メッセージで囲まれていることに注意してください。 次に例を示します。

警告: アクセス制御エントリ (ACE) atl-fs-01\\RTCUniversalServerAdmins;使うExtendedRight;該当該当1131f6aa-9c07-11d1-f79f-00c04fc2dcd2

警告: オブジェクト "CN = Computers, DC = litwareinc, DC = com" のアクセス制御エントリ (Ace) の準備ができていません。

False

警告: "Test-CsSetupPermission" 処理は完了しましたが、警告があります。 この実行中に警告が記録されました。

警告: 詳細な結果は、「C\\: Users\\Admin\\AppData\\Local\\Temp\\Test-cssetuppermission-1da99ba6-abe2-45e4-8b16-dfd244763118」に記載されています。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストが失敗した理由

例外はまれですが、通常は、指定された Active Directory コンテナーにセットアップのアクセス許可が割り当てられていないことを意味します。 これらのアクセス許可は、Grant-CsSetupPermission コマンドレットを使用して割り当てることができます。 たとえば、次のコマンドは、ドメイン litwareinc.com の Computers コンテナーに対するセットアップのアクセス許可を付与します。

    Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"

詳細については、 [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission)コマンドレットのヘルプトピックを参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

