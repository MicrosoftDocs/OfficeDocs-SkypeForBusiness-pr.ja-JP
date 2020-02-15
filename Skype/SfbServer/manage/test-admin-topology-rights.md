---
title: Skype for Business Server の管理者トポロジ権限のテスト
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
ms.openlocfilehash: de2f5752bdcd9096a47595fd7ffd10a3ab799d9c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030150"
---
# <a name="testing-admin-topology-rights-in-skype-for-business-server"></a>Skype for Business Server の管理者トポロジ権限のテスト

| | |
|--|--|
|検証スケジュール|最初の Skype for business Server の展開後。 必要に応じて、アクセス許可に関連する問題が発生します。|
|テストツール|Windows PowerShell|
|必要なアクセス許可|Skype for Business Server 管理シェルを使用してローカルに実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。<br/><br/>Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには、テスト用の CsSetupPermission コマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。 このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。<br/><br/>-オブジェクト {$ _ \|の場所で-CsAdminRole を取得します。コマンドレット-一致 "Test-CsSetupPermission"}|
|||

## <a name="description"></a>説明

既定では、ドメイン管理者のみが Skype for business Server トポロジを有効にして、Skype for Business Server インフラストラクチャに大きな変更を加えることができます。 これは、ドメイン管理者と Skype for Business Server 管理者が1つの場合に限り、問題になりません。 多くの組織では、Skype for Business Server 管理者はドメイン全体に対する管理権限を保持していません。 既定では、これらの管理者 (RTCUniversalServerAdmins グループのメンバーとして定義されている) が Skype for Business Server のトポロジを変更することはできません。 RTCUniversalServerAdmins グループのメンバーがトポロジを変更できるようにするには、必要な Active Directory アクセス許可を付与するために、 [Grant-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission)コマンドレットを使用する必要があります。
 
Test-CsSetupPermission コマンドレットは、Skype for Business Server またはそのコンポーネントのいずれかをインストールするために必要なアクセス許可が、指定した Active Directory コンテナーに対して構成されているかどうかを確認します。 アクセス許可が割り当てられていない場合は、Grant-CsSetupPermission コマンドレットを実行して、RTCUniversalServerAdmins グループのメンバーに、Skype for Business Server をインストールして有効にする権限を与えることができます。

## <a name="running-the-test"></a>テストの実行

Active Directory コンテナーにセットアップのアクセス許可が割り当てられているかどうかを判断するには、Test-CsSetupPermission コマンドレットを呼び出します。 確認するコンテナーの識別名を指定します。 たとえば、次のコマンドは、コンテナー ou = CsServers, dc = litwareinc, dc = com: に対するセットアップのアクセス許可を確認します。

`Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"`

詳細については、 [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission)コマンドレットのヘルプトピックを参照してください。

## <a name="determining-success-or-failure"></a>成功または失敗を判断する

必要なアクセス許可が Active Directory コンテナーに既に設定されている場合、このコマンドレットは True という値を返します。

はい 

権限が設定されていない場合、Test-CsSetupPermission は値 False を返します。 この値は通常、多くの警告メッセージで囲まれていることに注意してください。 例:

警告: アクセス制御エントリ (ACE) atl-cs-001\RTCUniversalServerAdmins;使うExtendedRight;該当該当1131f6aa-9c07-11d1-f79f-00c04fc2dcd2 

警告: オブジェクト "CN = Computers, DC = litwareinc, DC = com" のアクセス制御エントリ (Ace) の準備ができていません。 

False 

警告: "Test-CsSetupPermission" 処理は完了しましたが、警告があります。 この実行中に警告が記録されました。 

警告: 詳細な結果は、"C:\Users\Admin\AppData\Local\Temp\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html" にあります。 

## <a name="reasons-why-the-test-might-have-failed"></a>テストが失敗した理由

例外はまれですが、通常は、指定された Active Directory コンテナーにセットアップのアクセス許可が割り当てられていないことを意味します。 これらのアクセス許可は、Grant-CsSetupPermission コマンドレットを使用して割り当てることができます。 たとえば、次のコマンドは、ドメイン litwareinc.com の Computers コンテナーに対するセットアップのアクセス許可を付与します。

`Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"`

詳細については、 [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission)コマンドレットのヘルプトピックを参照してください。
