---
title: Skype for Business Server での管理者権限のテスト
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
description: Skype for Business Server で管理者権限をテストする方法
ms.openlocfilehash: 1e06c87dcf0e436d72c510a2bc8d9f2aa2051620
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030160"
---
# <a name="testing-admin-permissions-in-skype-for-business-server"></a>Skype for Business Server での管理者権限のテスト

| | |
|--|--|
|検証スケジュール|最初の Skype for business Server の展開後。 必要に応じて、アクセス許可に関連する問題が発生します。|
|テストツール|Windows PowerShell|
|必要なアクセス許可|Skype for Business Server 管理シェルを使用してローカルに実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。<br><br/>Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには、テスト用の CsOUPermission コマンドレットを実行する権限を持つ RBAC の役割が割り当てられている必要があります。 このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。<br/><br/>-オブジェクト {$ _ \|の場所で-CsAdminRole を取得します。コマンドレット-一致 "Test-CsOUPermission"}|
|||

## <a name="description"></a>説明

Skype for Business Server をインストールすると、セットアッププログラムによって実行されたタスクの1つによって、ユーザー、コンピューター、連絡先、アプリケーションの連絡先、および InetOrg を管理するために必要な Active Directory のアクセス許可が RTCUniversalUserAdmins グループに付与されます。員. Active Directory でのアクセス許可の継承が無効になっている場合、セットアップはそれらのアクセス許可を割り当てることができません。 その結果、RTCUniversalUserAdmins グループのメンバーは、Skype for Business Server のエンティティを管理することができなくなります。 これらの管理権限は、ドメイン管理者のみが使用できます。 

Test-CsOUPermission コマンドレットは、ユーザー、コンピューター、およびその他のオブジェクトを管理するために必要なアクセス許可が Active Directory コンテナーに設定されているかどうかを確認します。 これらのアクセス許可が設定されていない場合は、 [Grant-CsOUPermission コマンドレット](https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission)を実行することによって、この問題を解決できます。 

RTCUniversalUserAdmins グループのメンバーに対してアクセス許可を割り当てることはできないことに注意してください。 このコマンドレットを使用して、任意のユーザーまたはグループにアクセス許可を付与することはできません。 別のユーザーまたはグループにユーザー管理アクセス許可を付与する場合は、そのユーザーまたはグループを RTCUniversalUserAdmins グループに追加する必要があります。 


## <a name="running-the-test"></a>テストの実行

管理アクセス許可がコンテナーに設定されていることを確認するには、Test-CsOUPermission コマンドレットを実行した後に、コンテナーの識別名、および検証するアクセス許可の種類を指定します。 たとえば、次のコマンドは、ユーザーのアクセス許可が OU ou = Redmond, dc = litwareinc, dc = com で設定されているかどうかを確認します。

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"`

単一のコマンドを使用して複数のアクセス許可を確認するには、各アクセス許可の種類を二重引用符で囲み、コンマを使用してそれらの種類を区切ります。 たとえば、次のコマンドは、ユーザー、コンピューター、および連絡先のアクセス許可を確認します。

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"`

詳細については、 [Test-CsOUPermission コマンドレットのヘルプトピック](https://docs.microsoft.com/powershell/module/skype/test-csoupermission)を参照してください。

## <a name="determining-success-or-failure"></a>成功または失敗を判断する

必要なアクセス許可が既に設定されている場合、Test-CsOUPermission は1単語の応答を返します。

はい

必要なアクセス許可が設定されていない場合、Test-CsOUPermission は値 False を返します。 この値を見つけるには、少し時間を置いて検索する必要があるかもしれません。 通常は、いくつかの付随する警告に埋め込まれます。 例:

警告: アクセス制御エントリ (ACE) atl-cs-001\RTCUniversalUserReadOnlyGroup;使うReadPropertyContainerInherit;子孫bf967aba-0de6-11d0-00aa003049e2;d819615a-4738 3b9b-b47e-f1bd8ee3aea4 

警告: オブジェクト "OU = NorthAmerica, DC = atl-cs-001\DC = litwareinc, DC = com" のアクセス制御エントリ (Ace) の準備ができていません。 

False 

警告: "Test-CsOUPermission" 処理は完了しましたが、警告があります。 この実行中に警告が記録されました。 

警告: 詳細な結果は、"C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html" にあります。 

## <a name="reasons-why-the-test-might-have-failed"></a>テストが失敗した理由

Test-CsOUPermission に失敗した場合は、通常、指定されたアクセス許可が RTCUniversalUserAdmins グループに割り当てられていないことを意味します。 この問題を解決して、Grant-CsOUPermission コマンドレットを使用して必要なアクセス許可を割り当てることができます。 たとえば、次のコマンドを実行すると、ユーザー、連絡先、および inetOrgPersons の OU 権限が RTCUniversalUserAdmins グループに付与されます。

`Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"`

詳細については、 [Test-CsOUPermission コマンドレットのヘルプトピック](https://docs.microsoft.com/powershell/module/skype/test-csoupermission)を参照してください。
