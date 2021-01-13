---
title: Skype for Business Server での管理者アクセス許可のテスト
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Skype for Business Server で管理者のアクセス許可をテストする方法
ms.openlocfilehash: 27ae50cca0018985ad59dbc4487dd3630cb5cf87
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800097"
---
# <a name="testing-admin-permissions-in-skype-for-business-server"></a>Skype for Business Server での管理者アクセス許可のテスト

| | |
|--|--|
|検証スケジュール|Skype for Business Server の初期展開後。 必要に応じて、アクセス許可関連の問題が発生した場合。|
|テスト ツール|Windows PowerShell|
|必要なアクセス許可|Skype for Business Server 管理シェルを使用してローカルで実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティ グループのメンバーである必要があります。<br><br/>Windows PowerShell のリモート インスタンスを使用して実行する場合、ユーザーには、Test-CsOUPermission コマンドレットを実行するアクセス許可を持つ RBAC の役割が割り当てられている必要があります。 このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、コマンド プロンプトから次のコマンドWindows PowerShellします。<br/><br/>Get-CsAdminRoleWhere-Object \| {$_.Cmdlets -match "Test-CsOUPermission"}|
|||

## <a name="description"></a>説明

Skype for Business Server をインストールすると、セットアップ プログラムによって実行されたタスクの 1 つが、RTCUniversalUserAdmins グループに、ユーザー、コンピューター、連絡先、アプリケーション連絡先、および InetOrg ユーザーを管理するために必要な Active Directory アクセス許可を与えます。 Active Directory でアクセス許可の継承を無効にした場合、セットアップはそれらのアクセス許可を割り当てできません。 その結果、RTCUniversalUserAdmins グループのメンバーは Skype for Business Server エンティティを管理できません。 これらの管理特権は、ドメイン管理者だけが使用できます。 

このTest-CsOUPermissionコマンドレットは、ユーザー、コンピューター、および他のオブジェクトを管理するために必要なアクセス許可が Active Directory コンテナーに設定されているのを確認します。 これらのアクセス許可が設定されていない場合は [、Grant-CsOUPermission コマンドレットを実行してこの問題を解決できます](https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission)。 

アクセス許可Grant-CsOUPermission RTCUniversalUserAdmins グループのメンバーにのみ割り当て可能です。 このコマンドレットを使用して、任意のユーザーまたはグループにアクセス許可を付与することはできません。 別のユーザーまたはグループにユーザー管理アクセス許可を付与する場合は、そのユーザー (またはグループ) を RTCUniversalUserAdmins グループに追加する必要があります。 


## <a name="running-the-test"></a>テストの実行

管理アクセス許可がコンテナーに設定されているのを確認するには、Test-CsOUPermission コマンドレットの後にコンテナーの識別名と、確認するアクセス許可の種類を指定して実行します。 たとえば、次のコマンドは、OU ou=Redmond,dc=litwareinc,dc=com にユーザーのアクセス許可が設定されているかどうかを確認します。

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"`

1 つのコマンドを使用して複数のアクセス許可を確認するには、引用符で囲まれた各アクセス許可の種類を囲み、コンマを使用してそれらの種類を区切ります。 たとえば、次の 1 つのコマンドは、ユーザー、コンピューター、および連絡先のアクセス許可を確認します。

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"`

詳細については、このコマンドレットの [ヘルプ トピックTest-CsOUPermissionしてください](https://docs.microsoft.com/powershell/module/skype/test-csoupermission)。

## <a name="determining-success-or-failure"></a>成功または失敗を判断する

必要なアクセス許可が既に設定されている場合、Test-CsOUPermission 1 単語の応答を返します。

正

必要なアクセス許可が設定されていない場合、Test-CsOUPermission False が返されます。 この値を検索するには、しばらく検索する必要がある場合があります。 通常は、いくつかの付随する警告の中に埋め込む必要があります。 例:

警告: アクセス制御エントリ (ACE) atl-cs-001\RTCUniversalUserReadOnlyGroup;allow;ReadProperty;ContainerInherit;子孫;bf967aba-0de6-11d0-00aa003049e2;d819615a-3b9b-4738-b47e-f1bd8ee3aea4 

警告: オブジェクト "OU=NorthAmerica,DC=atl-cs-001\DC=litwareinc,DC=com" のアクセス制御エントリ (ACEs) は準備ができていない。 

False 

警告: "Test-CsOUPermission" 処理が完了し、警告が表示されました。 この実行時に"2" という警告が記録されました。 

警告: 詳細な結果については、「C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html」を参照してください。 

## <a name="reasons-why-the-test-might-have-failed"></a>テストが失敗した可能性がある理由

このTest-CsOUPermission、通常、指定されたアクセス許可が RTCUniversalUserAdmins グループに割り当てられていないという意味です。 この問題を解決し、必要なアクセス許可を割り当てるには、次のコマンドレットGrant-CsOUPermissionします。 たとえば、次のコマンドは、ユーザー、連絡先、および inetOrgPersons の OU アクセス許可を RTCUniversalUserAdmins グループに付与します。

`Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"`

詳細については、このコマンドレットの [ヘルプ トピックTest-CsOUPermissionしてください](https://docs.microsoft.com/powershell/module/skype/test-csoupermission)。
