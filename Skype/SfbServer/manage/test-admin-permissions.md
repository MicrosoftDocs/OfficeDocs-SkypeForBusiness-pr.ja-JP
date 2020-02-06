---
title: Skype for Business Server で管理者権限をテストする
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Skype for Business Server で管理権限をテストする方法
ms.openlocfilehash: 97db574803b575d484240e7339d56603ae5432da
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817188"
---
# <a name="testing-admin-permissions-in-skype-for-business-server"></a>Skype for Business Server で管理者権限をテストする

| | |
|--|--|
|確認のスケジュール|初めての Skype for Business Server の展開後。 必要に応じて、アクセス許可に関連する問題が発生します。|
|テストツール|Windows PowerShell|
|必要なアクセス許可|Skype for Business Server 管理シェルを使用してローカルで実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。<br><br/>Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには、CsOUPermission コマンドレットを実行するためのアクセス許可が与えられた RBAC の役割を割り当てる必要があります。 このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。<br/><br/>を\|取得します。-オブジェクト {$ _コマンドレット-match "Test-CsOUPermission"}|
|||

## <a name="description"></a>説明

Skype for Business Server をインストールすると、セットアッププログラムによって実行されたタスクの1つに、RTCUniversalUserAdmins グループにユーザー、コンピューター、連絡先、アプリケーションの連絡先、および InetOrg を管理するために必要な Active Directory アクセス許可が付与されます。連絡. Active Directory でアクセス許可の継承を無効にしている場合、セットアップでは、これらのアクセス許可を割り当てることはできません。 この結果、RTCUniversalUserAdmins グループのメンバーは、Skype for Business Server のエンティティを管理することができなくなります。 これらの管理権限は、ドメイン管理者のみが利用できます。 

ユーザー、コンピューター、その他のオブジェクトを管理するために必要なアクセス許可が Active Directory コンテナーで設定されていることを確認するために、CsOUPermission のテストコマンドレットを確認します。 これらのアクセス許可が設定されていない場合は、 [Grant-CsOUPermission コマンドレット](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsOUPermission)を実行することで、この問題を解決できます。 

ただし、権限の付与は、RTCUniversalUserAdmins グループのメンバーに対してのみ権限を割り当てることができます。 このコマンドレットを使用して、任意のユーザーまたはグループにアクセス許可を付与することはできません。 別のユーザーまたはグループにユーザー管理のアクセス許可を与える必要がある場合は、そのユーザー (またはグループ) を RTCUniversalUserAdmins グループに追加する必要があります。 


## <a name="running-the-test"></a>テストの実行

コンテナーに管理権限が設定されていることを確認するには、CsOUPermission コマンドレットを実行し、その後に、コンテナーの識別名と確認するアクセス許可の種類を指定します。 たとえば、次のコマンドは、ユーザー権限が OU ou で設定されているかどうかを確認します。 Redmond、dc = litwareinc、dc = com:

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"`

1つのコマンドを使用して複数のアクセス許可を確認するには、それぞれのアクセス許可の種類を引用符で囲んで囲み、コンマを使用してそれらの型を区切ります。 たとえば、次のコマンドは、ユーザー、コンピューター、および連絡先のアクセス許可を確認します。

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"`

詳細については、「 [CsOUPermission のテスト」コマンドレットのヘルプトピック](https://docs.microsoft.com/en-us/powershell/module/skype/test-csoupermission)を参照してください。

## <a name="determining-success-or-failure"></a>成功または失敗を確認する

必要なアクセス許可が既に設定されている場合、テスト用の CsOUPermission は1単語の応答を返します。

True

必要なアクセス許可が設定されていない場合は、"False" という値が返されます。 この値を検索するには、少し時間がかかる場合があります。 通常は、いくつかの関連する警告内に埋め込まれます。 次に例を示します。

警告: アクセス制御エントリ (ACE) atl-cs-001\RTCUniversalUserReadOnlyGroup許可ReadProperty;ContainerInherit;フォルダーbf967aba-11d0-00aa003049e2;d819615a-3b9b-4738-b47e-f1bd8ee3aea4 

警告: オブジェクト "OU = NorthAmerica, DC = atl-cs-001\DC = litwareinc, DC = com" のアクセス制御エントリ (Ace) の準備ができていません。 

False 

警告: "Test-CsOUPermission" 処理は警告で完了しています。 この実行中に警告が記録されました。 

警告: 詳細な結果は "C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html" に記載されています。 

## <a name="reasons-why-the-test-might-have-failed"></a>テストに失敗した可能性がある理由

RTCUniversalUserAdmins のテストに失敗した場合、通常は、指定したアクセス許可がグループに割り当てられていないことを意味します。 この問題を解決して、必要なアクセス許可を割り当てるには、アクセス許可の付与コマンドレットを使用します。 たとえば、次のコマンドを実行すると、ユーザー、連絡先、inetOrgPersons に対して、RTCUniversalUserAdmins グループに OU 権限が付与されます。

`Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"`

詳細については、「 [CsOUPermission のテスト」コマンドレットのヘルプトピック](https://docs.microsoft.com/en-us/powershell/module/skype/test-csoupermission)を参照してください。
