---
title: Skype のビジネス サーバーの管理者のアクセス許可をテスト
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype のビジネス サーバーの管理者のアクセス許可をテストする方法
ms.openlocfilehash: 3f3f649ea01f974cf0462cabb7784bedc7a6df4f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214716"
---
# <a name="testing-admin-permissions-in-skype-for-business-server"></a>Skype のビジネス サーバーの管理者のアクセス許可をテスト

| | |
|--|--|
|検証スケジュール|後ビジネス サーバーの展開の初期の Skype です。 必要に応じてアクセス許可に関連する問題が発生した場合。|
|テスト ツール|Windows PowerShell|
|必要なアクセス許可|ビジネス サーバー管理シェルには、Skype を使用してローカルで実行するとユーザーは RTCUniversalServerAdmins のセキュリティ グループのメンバーである必要があります。<br><br/>実行すると、Windows PowerShell のリモート インスタンスを使用してユーザーがテスト CsOUPermission コマンドレットを実行する権限を持っている RBAC の役割を割り当てられる必要があります。 このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。<br/><br/>Get CsAdminRole \| Where-object {$_ です。コマンドレットの「テスト CsOUPermission」に一致。|
|||

## <a name="description"></a>説明

RTCUniversalUserAdmins グループ ユーザー、コンピューター、連絡先、アプリケーションの連絡先、および InetOrg を管理するために必要な Active Directory アクセス許可は、セットアップ プログラムによって実行されたタスクのいずれかのビジネス サーバーの Skype をインストールするとき担当者です。 Active Directory のアクセス許可の継承を無効にした場合、セットアップはこれらのアクセス許可を割り当てることができません。 その結果、RTCUniversalUserAdmins グループのメンバーは、サーバーのビジネス エンティティの Skype を管理するためにはできません。 管理権限はドメイン管理者にのみできます。 

テスト CsOUPermission コマンドレットでは、Active Directory コンテナーにユーザー、コンピューター、およびその他のオブジェクトを管理するために必要なパーミッションが設定されているを確認します。 これらのアクセス許可が設定されていない場合は、[補助金 CsOUPermission コマンドレット](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsOUPermission)を実行してこの問題を解決できます。 

許可 CsOUPermission のみを割り当てることがアクセス許可、RTCUniversalUserAdmins グループのメンバーに注意してください。 このコマンドレットを使用して、任意のユーザーまたはグループにアクセス許可を付与できません。 ユーザー管理権限を持っている別のユーザーまたはグループを選択する場合は、RTCUniversalUserAdmins グループにそのユーザー (またはグループ) を追加する必要があります。 


## <a name="running-the-test"></a>テストを実行しています。

コンテナーの管理アクセス許可が設定されていることを確認するには、コンテナーの識別名、および確認の対象とするアクセス許可の種類の後にテスト CsOUPermission コマンドレットを実行します。 たとえば、このコマンドは、OU の ou にユーザーのアクセス許可を設定するかどうかをチェック = 東京都, dc = litwareinc、dc = com。

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"`

1 つのコマンドを使用して複数のアクセス許可を確認するには、引用符、二重引用符で囲まれている各アクセス許可の種類し、コンマを使用して、これらの種類を区別します。 ユーザー、コンピューター、および取引先担当者に、この 1 つのコマンドを確認するなどのアクセス許可。

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"`

詳細については、[テスト CsOUPermission コマンドレットのヘルプ トピック](https://docs.microsoft.com/en-us/powershell/module/skype/test-csoupermission)を参照してください。

## <a name="determining-success-or-failure"></a>成功または失敗を決定します。

場合は既に設定されている必要なアクセス許可には、テスト CsOUPermission には、1 つの word の応答が返されます。

True

必要なアクセス許可が設定されていない場合、テスト CsOUPermission は値 False を返します。 この値を検索するのには少しの間を検索する必要があります。 付随するいくつかの警告の中に通常埋め込まれます。 次に例を示します。

警告: アクセス制御エントリ (ACE) atl の cs-001\RTCUniversalUserReadOnlyGroup です。許可します。ReadProperty です。ContainerInherit です。サブフォルダーが存在します。-00aa003049e2 bf967aba-0de6-11 d 0 です。d819615a-3b9b-4738-b47e-f1bd8ee3aea4 

警告: アクセス制御エントリ (Ace) オブジェクトの"OU = NorthAmerica、DC = atl の cs-001\DC = litwareinc、DC = com"準備ができていません。 

False 

警告: 警告「テスト CsOUPermission」の処理が完了しました。 この実行中に「2」の警告が記録されています。 

警告:"C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html"の結果の詳細を参照しています。 

## <a name="reasons-why-the-test-might-have-failed"></a>なぜテストが失敗した理由

CsOUPermission のテストが失敗した場合は、通常、RTCUniversalUserAdmins グループに指定したアクセス許可が割り当てられていないことを意味します。 この問題を解決し、与える CsOUPermission コマンドレットを使用して、必要なアクセス許可を割り当てることがことができます。 など、このコマンドは、RTCUniversalUserAdmins グループにユーザー、連絡先、および Inetorgperson の OU のアクセス許可を使用します。

`Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"`

詳細については、[テスト CsOUPermission コマンドレットのヘルプ トピック](https://docs.microsoft.com/en-us/powershell/module/skype/test-csoupermission)を参照してください。
