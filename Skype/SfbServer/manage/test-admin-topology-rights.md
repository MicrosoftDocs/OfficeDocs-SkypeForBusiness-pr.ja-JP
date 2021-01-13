---
title: Skype for Business Server での管理トポロジ権限のテスト
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
description: Skype for Business Server でトポロジ権限をテストする方法
ms.openlocfilehash: a6bbebd44387911fdb69679a16ab052c673f0b10
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832847"
---
# <a name="testing-admin-topology-rights-in-skype-for-business-server"></a>Skype for Business Server での管理トポロジ権限のテスト

| | |
|--|--|
|検証スケジュール|Skype for Business Server の初期展開後。 必要に応じて、アクセス許可関連の問題が発生した場合。|
|テスト ツール|Windows PowerShell|
|必要なアクセス許可|Skype for Business Server 管理シェルを使用してローカルで実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティ グループのメンバーである必要があります。<br/><br/>Windows PowerShell のリモート インスタンスを使用して実行する場合、ユーザーには、Test-CsSetupPermission コマンドレットを実行するアクセス許可を持つ RBAC の役割が割り当てられている必要があります。 このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、次のコマンドをプロンプトWindows PowerShellします。<br/><br/>Get-CsAdminRoleWhere-Object \| {$_.Cmdlets -match "Test-CsSetupPermission"}|
|||

## <a name="description"></a>説明

既定では、ドメイン管理者だけが Skype for Business Server トポロジを有効にし、Skype for Business Server インフラストラクチャに大きな変更を加えます。 ドメイン管理者と Skype for Business Server 管理者が同一である限り、これは問題ではありません。 多くの組織では、Skype for Business Server 管理者はドメイン全体に対する管理者権限を保持しません。 既定では、これらの管理者 (RTCUniversalServerAdmins グループのメンバーとして定義されている管理者) は Skype for Business Server トポロジを変更できません。 RTCUniversalServerAdmins グループのメンバーにトポロジを変更する権限を付与するには [、Grant-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission) コマンドレットを使用して必要な Active Directory アクセス許可を割り当てる必要があります。
 
次Test-CsSetupPermissionコマンドレットは、Skype for Business Server またはそのコンポーネントの 1 つをインストールするために必要なアクセス許可が、指定された Active Directory コンテナーに構成されていることを確認します。 アクセス許可が割り当てられていない場合は、Grant-CsSetupPermission コマンドレットを実行して、RTCUniversalServerAdmins グループのメンバーに Skype for Business Server をインストールして有効にする権限を付与できます。

## <a name="running-the-test"></a>テストの実行

Active Directory コンテナーに対してセットアップのアクセス許可が割り当てられているかどうかを確認するには、次のコマンドレットTest-CsSetupPermissionします。 確認するコンテナーの識別名を指定します。 たとえば、次のコマンドは、コンテナー ou=CsServers,dc=litwareinc,dc=com に対するセットアップのアクセス許可を確認します。

`Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"`

詳細については [、Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) コマンドレットのヘルプ トピックを参照してください。

## <a name="determining-success-or-failure"></a>成功または失敗を判断する

Active Directory Test-CsSetupPermissionに必要なアクセス許可が既に設定されている場合、コマンドレットは値 True を返します。

正 

アクセス許可が設定されていない場合、Test-CsSetupPermission False が返されます。 通常、この値は多くの警告メッセージで囲まれます。 例:

警告: アクセス制御エントリ (ACE) atl-cs-001\RTCUniversalServerAdmins;許可;ExtendedRight;なし。なし。1131f6aa-9c07-11d1-f79f-00c04fc2dcd2 

警告: オブジェクト "CN=Computers,DC=litwareinc,DC=com" のアクセス制御エントリ (ES) は準備ができていない。 

False 

警告: "Test-CsSetupPermission" 処理が完了し、警告が表示されました。 この実行時に"2" の警告が記録されました。 

警告: 詳細な結果については、「C:\Users\Admin\AppData\Local\Temp\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html」を参照してください。 

## <a name="reasons-why-the-test-might-have-failed"></a>テストが失敗した可能性がある理由

まれな例外は発生しますが、Test-CsSetupPermission失敗した場合は、通常、指定した Active Directory コンテナーに対してセットアップのアクセス許可が割り当てられていないという意味になります。 これらのアクセス許可は、次のコマンドレットを使用Grant-CsSetupPermissionできます。 たとえば、次のコマンドを実行すると、ドメイン ドメイン内の Computers コンテナーに対するセットアップアクセス許可がlitwareinc.com。

`Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"`

詳細については [、Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) コマンドレットのヘルプ トピックを参照してください。
