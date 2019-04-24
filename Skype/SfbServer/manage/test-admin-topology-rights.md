---
title: Skype のビジネス サーバーのトポロジの管理者権限をテスト
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype のビジネス サーバーのトポロジの権限をテストする方法
ms.openlocfilehash: ad65d42a49d7b85c324766e208e44d6b5e1b632f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214871"
---
# <a name="testing-admin-topology-rights-in-skype-for-business-server"></a>Skype のビジネス サーバーのトポロジの管理者権限をテスト

| | |
|--|--|
|検証スケジュール|後ビジネス サーバーの展開の初期の Skype です。 必要に応じてアクセス許可に関連する問題が発生した場合。|
|テスト ツール|Windows PowerShell|
|必要なアクセス許可|ビジネス サーバー管理シェルには、Skype を使用してローカルで実行するとユーザーは RTCUniversalServerAdmins のセキュリティ グループのメンバーである必要があります。<br/><br/>実行すると、Windows PowerShell のリモート インスタンスを使用してユーザーがテスト CsSetupPermission コマンドレットを実行する権限を持っている RBAC の役割を割り当てられる必要があります。 このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。<br/><br/>Get CsAdminRole \| Where-object {$_ です。コマンドレットの「テスト CsSetupPermission」に一致。|
|||

## <a name="description"></a>説明

既定では、ドメイン管理者のみが、Skype ビジネス サーバー トポロジを有効にしてビジネスのサーバー インフラストラクチャの Skype に大きな変更を加えます。 問題として、ドメイン管理者およびビジネスのサーバー管理者のため、Skype では、1 つ必要はありません。 多くの組織でビジネスのサーバー管理者のための Skype は、ドメイン全体に対する管理者権限を保持しないでください。 既定では、(RTCUniversalServerAdmins グループのメンバーとして定義されている)、これらの管理者がビジネスのサーバー トポロジの変更の Skype をすることはできないことを意味します。 RTCUniversalServerAdmins グループ トポロジを変更する権限のメンバーを与えるには、 [Grant CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsSetupPermission)コマンドレットを使用して、必要な Active Directory のアクセス許可を割り当てる必要があります。
 
テスト CsSetupPermission コマンドレットは、指定した Active Directory コンテナーに必要な Business Server またはそのコンポーネントのいずれかの Skype をインストールするために必要なアクセス許可が構成されているを確認します。 アクセス許可が割り当てられていない場合は、RTCUniversalServerAdmins グループのメンバーにインストールし、ビジネスのサーバーで Skype を有効にする権限を付与する Grant CsSetupPermission コマンドレットを実行できます。

## <a name="running-the-test"></a>テストを実行しています。

セットアップ アクセス許可が Active Directory コンテナーに割り当てられたかどうかを確認するのには、テスト CsSetupPermission コマンドレットを呼び出します。 チェックするコンテナーの識別名を指定します。 このコマンドがコンテナー ou のアクセス許可を設定を確認するたとえば、= CsServers、dc = litwareinc、dc = com。

`Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"`

詳細については、[テスト CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsSetupPermission)コマンドレットのヘルプ トピックを参照してください。

## <a name="determining-success-or-failure"></a>成功または失敗を決定します。

必要なアクセス許可が Active Directory コンテナーに設定されている既にテスト CsSetupPermission と判断した場合、コマンドレットは True 値を返します。

True 

アクセス許可が設定されていない場合、テスト CsSetupPermission は値 False を返します。 この値が多くの警告メッセージで囲まれた通常は注意してください。 次に例を示します。

警告: アクセス制御エントリ (ACE) atl の cs-001\RTCUniversalServerAdmins です。許可します。ExtendedRight。[なし] です。[なし] です。1131f6aa-9c07-11d1-f79f-00c04fc2dcd2 

警告: アクセス制御エントリ (Ace) オブジェクトの"CN = Computers、DC = litwareinc、DC = com」準備ができていません。 

False 

警告: 警告「テスト CsSetupPermission」の処理が完了しました。 この実行中に「2」の警告が記録されています。 

警告:"C:\Users\Admin\AppData\Local\Temp\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html"の結果の詳細を参照しています。 

## <a name="reasons-why-the-test-might-have-failed"></a>なぜテストが失敗した理由

テスト CsSetupPermission が失敗した場合に通常は、まれな例外がありますが、指定した Active Directory コンテナーにはアクセス許可を設定することを意味は割り当てられていません。 許可 CsSetupPermission コマンドレットを使用してこれらのアクセス許可を指定できます。 たとえば、このコマンドでは、ドメイン litwareinc.com のコンピューター コンテナーにセットアップの許可が付与されます。

`Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"`

詳細については、[テスト CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsSetupPermission)コマンドレットのヘルプ トピックを参照してください。
