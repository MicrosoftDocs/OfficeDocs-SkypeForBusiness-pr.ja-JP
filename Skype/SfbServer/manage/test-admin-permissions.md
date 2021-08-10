---
title: 管理者のアクセス許可をテストSkype for Business Server
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
description: 管理者のアクセス許可をテストするSkype for Business Server
ms.openlocfilehash: 1c828eeb965ee98aae72b00c7da9fa65016d2ed90e56c7cc982a59763c2703ae
ms.sourcegitcommit: 0e9516c51105e4d89c550d2ea2bd8e7649a1163b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2021
ms.locfileid: "54590771"
---
# <a name="testing-admin-permissions-in-skype-for-business-server"></a>管理者のアクセス許可をテストSkype for Business Server

|&nbsp; |&nbsp; |
|--|--|
|検証スケジュール|最初の展開Skype for Business Server後。 必要に応じて、アクセス許可に関連する問題が発生した場合。|
|テスト ツール|Windows PowerShell|
|必要なアクセス許可|管理シェルを使用してローカルSkype for Business Server実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティ グループのメンバーである必要があります。<br><br/>サーバーのリモート インスタンスを使用して実行Windows PowerShell、ユーザーには、管理者コマンドレットを実行するアクセス許可を持つ RBAC ロールを割りTest-CsOUPermissionがあります。 このコマンドレットを使用できるすべての RBAC 役割の一覧を表示するには、次のコマンドをプロンプトからWindows PowerShellします。<br/><br/>Get-CsAdminRoleWhere-Object \| {$_.コマンドレット -match "Test-CsOUPermission"}|
|||

## <a name="description"></a>説明

Skype for Business Server をインストールすると、セットアップ プログラムによって実行されたタスクの 1 つが、ユーザー、コンピューター、連絡先、アプリケーション連絡先、および InetOrg ユーザーを管理するために必要な Active Directory アクセス許可を RTCUniversalUserAdmins グループに付与します。 Active Directory でアクセス許可の継承を無効にしている場合、セットアップではこれらのアクセス許可を割り当てできません。 その結果、RTCUniversalUserAdmins グループのメンバーは、エンティティを管理Skype for Business Serverされます。 これらの管理特権は、ドメイン管理者だけが利用できます。 

このTest-CsOUPermissionコマンドレットは、ユーザー、コンピューター、その他のオブジェクトを管理するために必要なアクセス許可が Active Directory コンテナーに設定されているのを確認します。 これらのアクセス許可が設定されていない場合は [、Grant-CsOUPermission](/powershell/module/skype/Grant-CsOUPermission)コマンドレットを実行して、この問題を解決できます。 

RTCUniversalUserAdmins グループのメンバーにのみアクセス許可を割り当てGrant-CsOUPermissionに注意してください。 このコマンドレットを使用して、任意のユーザーまたはグループにアクセス許可を付与することはできません。 別のユーザーまたはグループにユーザー管理アクセス許可を付与する場合は、そのユーザー (またはグループ) を RTCUniversalUserAdmins グループに追加する必要があります。 


## <a name="running-the-test"></a>テストの実行

管理アクセス許可がコンテナーに設定されているのを確認するには、Test-CsOUPermission コマンドレットの後にコンテナーの識別名と、確認するアクセス許可の種類を指定して実行します。 たとえば、次のコマンドは、OU ou=Redmond、dc=litwareinc、dc=com でユーザーアクセス許可が設定されているかどうかを確認します。

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"`

1 つのコマンドを使用して複数のアクセス許可を確認するには、引用符で囲まれた各アクセス許可の種類を囲み、コンマを使用してそれらの種類を区切ります。 たとえば、次の 1 つのコマンドは、ユーザー、コンピューター、および連絡先のアクセス許可を確認します。

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"`

詳細については、このコマンドレットの [ヘルプ トピックをTest-CsOUPermissionしてください](/powershell/module/skype/test-csoupermission)。

## <a name="determining-success-or-failure"></a>成功または失敗を判断する

必要なアクセス許可が既に設定されている場合、Test-CsOUPermission応答が返されます。

正しい

必要なアクセス許可が設定されていない場合、Test-CsOUPermission False が返されます。 この値を見つけるには、しばらく検索する必要がある場合があります。 通常、いくつかの付随する警告の内部に埋め込む必要があります。 例:

警告: アクセス制御エントリ (ACE) atl-cs-001\RTCUniversalUserReadOnlyGroup;allow;ReadProperty;ContainerInherit;Descendents;bf967aba-0de6-11d0-00aa003049e2;d819615a-3b9b-4738-b47e-f1bd8ee3aea4 

警告: オブジェクト "OU=NorthAmerica,DC=atl-cs-001\DC=litwareinc,DC=com" のアクセス制御エントリ (ACEs) は準備ができていません。 

正しくない 

警告: "Test-CsOUPermission" 処理が完了し、警告が表示されました。 "2" 警告は、この実行時に記録されました。 

警告: 詳細な結果は"C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html" で確認できます。 

## <a name="reasons-why-the-test-might-have-failed"></a>テストが失敗した可能性がある理由

エラーTest-CsOUPermission場合は、通常、指定されたアクセス許可が RTCUniversalUserAdmins グループに割り当てられていないという意味です。 この問題を解決し、必要なアクセス許可を割り当てるには、このコマンドレットを使用Grant-CsOUPermissionできます。 たとえば、このコマンドは、ユーザー、連絡先、および inetOrgPersons に対する OU アクセス許可を RTCUniversalUserAdmins グループに付与します。

`Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"`

詳細については、このコマンドレットの [ヘルプ トピックをTest-CsOUPermissionしてください](/powershell/module/skype/test-csoupermission)。