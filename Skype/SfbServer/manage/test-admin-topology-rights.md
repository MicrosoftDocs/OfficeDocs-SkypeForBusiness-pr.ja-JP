---
title: Skype for Business Server で管理者トポロジの権限をテストする
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
description: Skype for Business Server でトポロジの権限をテストする方法
ms.openlocfilehash: 1664a7e7d2b202b596a882e4b393cc15220806c9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817313"
---
# <a name="testing-admin-topology-rights-in-skype-for-business-server"></a>Skype for Business Server で管理者トポロジの権限をテストする

| | |
|--|--|
|確認のスケジュール|初めての Skype for Business Server の展開後。 必要に応じて、アクセス許可に関連する問題が発生します。|
|テストツール|Windows PowerShell|
|必要なアクセス許可|Skype for Business Server 管理シェルを使用してローカルで実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。<br/><br/>Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには、CsSetupPermission コマンドレットを実行するためのアクセス許可が与えられた RBAC の役割を割り当てる必要があります。 このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。<br/><br/>を\|取得します。-オブジェクト {$ _コマンドレット-match "Test-CsSetupPermission"}|
|||

## <a name="description"></a>説明

既定では、ドメイン管理者のみが Skype for business Server のトポロジを有効にして、Skype for Business Server インフラストラクチャに大きな変更を加えることができます。 これは、ドメイン管理者と Skype for Business Server の管理者がどちらも同じである限り、問題になりません。 多くの組織では、Skype for Business Server の管理者は、ドメイン全体の管理権限を保持していません。 既定では、これらの管理者 (RTCUniversalServerAdmins グループのメンバーとして定義されます) は、Skype for Business Server のトポロジを変更できません。 トポロジを変更する権利を RTCUniversalServerAdmins グループのメンバーに付与するには、[グラント Setuppermission](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsSetupPermission)コマンドレットを使用して、必要な Active Directory アクセス許可を割り当てる必要があります。
 
テスト用のセットアップアクセス許可コマンドレットを使用して、Skype for Business Server またはそのコンポーネントのいずれかをインストールするために必要なアクセス許可が、指定した Active Directory コンテナーで構成されていることを確認します。 アクセス許可が割り当てられていない場合は、グラント Setuppermission コマンドレットを実行して、RTCUniversalServerAdmins グループのメンバーに Skype for Business Server をインストールして有効にする権利を与えることができます。

## <a name="running-the-test"></a>テストの実行

Active Directory コンテナーにセットアップのアクセス許可が割り当てられているかどうかを判断するには、CsSetupPermission コマンドレットを呼び出します。 確認するコンテナーの識別名を指定します。 たとえば、次のコマンドは、コンテナー ou = CsServers、dc = litwareinc、dc = com のセットアップアクセス許可を確認します。

`Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"`

詳細については、「 [CsSetupPermission のテスト](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsSetupPermission)」コマンドレットのヘルプトピックを参照してください。

## <a name="determining-success-or-failure"></a>成功または失敗を確認する

Active Directory コンテナーで必要なアクセス許可が既に設定されていることを確認した場合、コマンドレットは値 True を返します。

True 

権限が設定されていない場合は、CsSetupPermission は値 False を返します。 通常、この値は多くの警告メッセージで囲まれることに注意してください。 次に例を示します。

警告: アクセス制御エントリ (ACE) atl-cs-001\RTCUniversalServerAdmins許可ExtendedRight;--1131f6aa-9c07-11d1-f79f-00c04fc2dcd2 

警告: オブジェクト "CN = Computers, DC = litwareinc, DC = com" のアクセス制御エントリ (Ace) の準備ができていません。 

False 

警告: "Test-CsSetupPermission" 処理は、警告と共に完了します。 この実行中に警告が記録されました。 

警告: 詳細な結果は "C:\Users\Admin\AppData\Local\Temp\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html" に記載されています。 

## <a name="reasons-why-the-test-might-have-failed"></a>テストに失敗した可能性がある理由

例外はまれにありますが、通常は、指定した Active Directory コンテナーに対するセットアップアクセス許可が割り当てられていないことを意味します。 これらのアクセス許可を割り当てるには、グラント Setuppermission コマンドレットを使用します。 たとえば、次のコマンドを実行すると、domain litwareinc.com の Computers コンテナーのセットアップ権限が付与されます。

`Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"`

詳細については、「 [CsSetupPermission のテスト](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsSetupPermission)」コマンドレットのヘルプトピックを参照してください。
