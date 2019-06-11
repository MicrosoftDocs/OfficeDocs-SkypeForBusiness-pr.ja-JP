---
title: 'Lync Server 2013: 管理者トポロジの権限をテストする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test admin topology rights
ms:assetid: 0c03b7fd-449a-47ad-8263-ce811164cbce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767943(v=OCS.15)
ms:contentKeyID: 63969575
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 365c879678ff3fd51dcaaf89d4b2593eccf645f3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848522"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-admin-topology-rights-in-lync-server-2013"></a>Lync Server 2013 で管理者トポロジのテスト権限をテストする

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2016-12-08_


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
<p>Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには、CsSetupPermission コマンドレットを実行するためのアクセス許可が与えられた RBAC の役割を割り当てる必要があります。 このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsSetupPermission&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

既定では、ドメイン管理者のみが Lync Server トポロジを有効にして、Lync Server インフラストラクチャに大きな変更を加えることができます。 この問題は、ドメイン管理者と Lync Server の管理者が同じものである限り、問題になりません。多くの組織では、Lync Server の管理者は、ドメイン全体の管理権限を保持していません。 既定では、これらの管理者 (RTCUniversalServerAdmins グループのメンバーとして定義されます) は、Lync Server のトポロジを変更できません。 トポロジを変更する権利を RTCUniversalServerAdmins グループのメンバーに付与するには、[グラント Setuppermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission)コマンドレットを使用して、必要な Active Directory アクセス許可を割り当てる必要があります。

"CsSetupPermission テスト" コマンドレットは、Lync Server またはそのいずれかのコンポーネントのインストールに必要なアクセス許可が、指定された Active Directory コンテナーで構成されていることを確認します。 アクセス許可が割り当てられていない場合は、グラント Setuppermissions コマンドレットを実行して、Lync Server をインストールして有効にする権利を RTCUniversalServerAdmins グループのメンバーに付与することができます。

<div>


> [!NOTE]  
> Grant (CsSetupPermission アクセス許可によって割り当てられたアクセス許可の詳細<A href="https://blogs.technet.com/b/jenstr/archive/2011/02/07/grant-cssetuppermission-and-grant-csoupermission.aspx"></A>な一覧については、「ブログ投稿のアクセス許可」を参照してください。



</div>

</div>

<div>

## <a name="running-the-test"></a>テストの実行

Active Directory コンテナーにセットアップのアクセス許可が割り当てられているかどうかを判断するには、CsSetupPermission コマンドレットを呼び出します。 確認するコンテナーの識別名を指定します。 たとえば、次のコマンドは、コンテナー ou = CsServers、dc = litwareinc、dc = com のセットアップアクセス許可を確認します。

    Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"

詳細については、「 [CsSetupPermission のテスト](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission)」コマンドレットのヘルプトピックを参照してください。

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を確認する

Active Directory コンテナーで必要なアクセス許可が既に設定されていることを確認した場合、コマンドレットは値 True を返します。

True

権限が設定されていない場合は、CsSetupPermission は値 False を返します。 通常、この値は多くの警告メッセージで囲まれることに注意してください。 次に例を示します。

警告: アクセス制御エントリ (ACE) atl-cs-001\\RTCUniversalServerAdmins;許可ExtendedRight;--1131f6aa-9c07-11d1-f79f-00c04fc2dcd2

警告: オブジェクト "CN = Computers, DC = litwareinc, DC = com" のアクセス制御エントリ (Ace) の準備ができていません。

False

警告: "Test-CsSetupPermission" 処理は、警告と共に完了します。 この実行中に警告が記録されました。

警告: 詳細な結果は、"C\\: Users\\管理者\\向け\\AppData\\ローカル\\一時テスト-cssetuppermission-1da99ba6-abe2-45e4-8b16-dfd244763118" にあります。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストに失敗した可能性がある理由

例外はまれにありますが、通常は、指定した Active Directory コンテナーに対するセットアップアクセス許可が割り当てられていないことを意味します。 これらのアクセス許可を割り当てるには、グラント Setuppermission コマンドレットを使用します。 たとえば、次のコマンドを実行すると、domain litwareinc.com の Computers コンテナーのセットアップ権限が付与されます。

    Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"

詳細については、「 [CsSetupPermission のテスト](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission)」コマンドレットのヘルプトピックを参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

