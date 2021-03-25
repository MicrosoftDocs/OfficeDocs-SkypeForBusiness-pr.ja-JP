---
title: Skype for Business Server での管理者トポロジ権限のテスト
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
ms.openlocfilehash: d9c0ec5560dcb6f1a6872f0b38f2930e46b2364c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122391"
---
# <a name="testing-admin-topology-rights-in-skype-for-business-server"></a>Skype for Business Server での管理者トポロジ権限のテスト

| | |
|--|--|
|検証スケジュール|Skype for Business Server の初期展開後。 必要に応じて、アクセス許可に関連する問題が発生した場合。|
|テスト ツール|Windows PowerShell|
|必要なアクセス許可|Skype for Business Server 管理シェルを使用してローカルで実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティ グループのメンバーである必要があります。<br/><br/>リモート インスタンスを使用して Windows PowerShellを実行する場合、ユーザーには、このコマンドレットを実行するアクセス許可を持つ RBAC ロールTest-CsSetupPermissionがあります。 このコマンドレットを使用できるすべての RBAC 役割の一覧を表示するには、次のコマンドをプロンプトからWindows PowerShellします。<br/><br/>Get-CsAdminRoleWhere-Object \| {$_.コマンドレット -match "Test-CsSetupPermission"}|
|||

## <a name="description"></a>説明

既定では、Skype for Business Server トポロジを有効にし、Skype for Business Server インフラストラクチャに大きな変更を加えるのは、ドメイン管理者のみです。 ドメイン管理者と Skype for Business Server 管理者が同一である限り、これは問題ではありません。 多くの組織では、Skype for Business Server 管理者はドメイン全体に対する管理者権限を保持しません。 既定では、これらの管理者 (RTCUniversalServerAdmins グループのメンバーとして定義) では、Skype for Business Server トポロジを変更できません。 RTCUniversalServerAdmins グループのメンバーにトポロジの変更を行う権限を付与するには [、Grant-CsSetupPermission](/powershell/module/skype/Grant-CsSetupPermission) コマンドレットを使用して必要な Active Directory アクセス許可を割り当てる必要があります。
 
この Test-CsSetupPermissionコマンドレットは、Skype for Business Server のインストールに必要なアクセス許可、またはそのコンポーネントの 1 つが、指定された Active Directory コンテナーに構成されていることを確認します。 アクセス許可が割り当てられていない場合は、Grant-CsSetupPermission コマンドレットを実行して、RTCUniversalServerAdmins グループのメンバーに Skype for Business Server をインストールして有効にする権限を付与できます。

## <a name="running-the-test"></a>テストの実行

Active Directory コンテナーに対してセットアップアクセス許可が割り当てられているかどうかを確認するには、次のコマンドレットTest-CsSetupPermissionします。 チェックするコンテナーの識別名を指定します。 たとえば、次のコマンドは、コンテナー ou=CsServers、dc=litwareinc、dc=com に対するセットアップアクセス許可を確認します。

`Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"`

詳細については [、Test-CsSetupPermission コマンドレットのヘルプ トピックを参照](/powershell/module/skype/Test-CsSetupPermission) してください。

## <a name="determining-success-or-failure"></a>成功または失敗を判断する

Active Directory Test-CsSetupPermissionに必要なアクセス許可が既に設定されている場合、コマンドレットは値 True を返します。

True 

アクセス許可が設定されていない場合、Test-CsSetupPermission False が返されます。 通常、この値は多くの警告メッセージで囲まれます。 例:

警告: アクセス制御エントリ (ACE) atl-cs-001\RTCUniversalServerAdmins;許可する。ExtendedRight;なし。なし。1131f6aa-9c07-11d1-f79f-00c04fc2dcd2 

警告: オブジェクト "CN=Computers,DC=litwareinc,DC=com" のアクセス制御エントリ (ACEs) が準備ができていません。 

False 

警告: "Test-CsSetupPermission" 処理が完了し、警告が表示されました。 "2" 警告は、この実行時に記録されました。 

警告: 詳細な結果は"C:\Users\Admin\AppData\Local\Temp\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html" で確認できます。 

## <a name="reasons-why-the-test-might-have-failed"></a>テストが失敗した可能性がある理由

まれな例外は発生しますが、Test-CsSetupPermission失敗した場合は、通常、指定した Active Directory コンテナーに対してセットアップアクセス許可が割り当てられていないという意味です。 これらのアクセス許可は、このコマンドレットを使用してGrant-CsSetupPermissionできます。 たとえば、次のコマンドは、ドメイン サーバー内の Computers コンテナーに対するセットアップ権限を付与 litwareinc.com。

`Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"`

詳細については [、Test-CsSetupPermission コマンドレットのヘルプ トピックを参照](/powershell/module/skype/Test-CsSetupPermission) してください。