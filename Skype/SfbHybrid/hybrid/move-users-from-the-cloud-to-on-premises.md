---
title: クラウドからオンプレミスにユーザーを移動する
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: ユーザーをオンラインからオンプレミスSkype for Businessする方法について学習します。
ms.openlocfilehash: 78e86e48e9f409c9e2a9f348cada9c24f30c6279
ms.sourcegitcommit: 9879bc587382755d9a5cd63a75b0e7dc4e15574c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2021
ms.locfileid: "53509788"
---
# <a name="move-users-from-the-cloud-to-on-premises"></a>クラウドからオンプレミスにユーザーを移動する 

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

必要に応じて、以前にオンプレミスからクラウドに移行されたユーザー (Skype for Business Online または Teams Only を使用する場合) をオンプレミスに移動できます。 Skype for Business Online モードまたは TeamsOnly モードから Skype for Business Server のオンプレミス展開にユーザーを移動するには、Move-CsUser コマンドレットまたは Skype for Business Server コントロール パネルのいずれかを使用します。どちらもオンプレミス ツールです。 ユーザーをオンプレミス展開に戻す場合は、ユーザーを移動するプールを決定する必要があります。

> [!Important]
> ユーザーが以前 TeamsOnly モードで、CU8 で Skype for Business Server 2015 より前のバージョンを使用している場合は、そのユーザーの TeamsUpgradePolicy の TeamsOnly モードの割り当てを削除する必要があります。 オンプレミスのユーザーは mode= TeamsOnly を持つ必要があります。  それ以降のバージョンのSkype for Business Serverこの割り当てを自動的に削除します。 詳細については [、「Grant-CsTeamsUpgradePolicy」を参照してください](/powershell/module/skype/grant-csteamsupgradepolicy)。

## <a name="prerequisites"></a>前提条件

- 組織では、「Azure AD Connect構成」の説明に従って、Azure リソースを適切に構成し、ユーザーに関連するすべての属性[を同期する必要AD Connect。](configure-azure-ad-connect.md)
- オンラインからオンプレミスに移動するユーザーは、オンプレミスの Active Directory に既に存在している必要があります。
- Skype for Businessハイブリッドの構成」の説明に従って、ハイブリッド[Skype for Businessする必要があります](configure-federation-with-skype-for-business-online.md)。

## <a name="moving-users-back-to-on-premises"></a>ユーザーをオンプレミスに戻す

ユーザーをクラウドからオンプレミスに戻したら、次の方法を実行します。

- ユーザーは、その機能Skype for Business Server展開を操作します。 
- [オンライン] または [オンライン] または [Skype for Business] にTeams連絡先は、Skype for Business Server。 2 つの連絡先セットが結合され、オンプレミスに移行されます。  さらに、既存の連絡先は、Teamsに残Teams。
- ユーザーが Teams を使用している場合、Skype for Business ユーザーと相互運用する機能も、フェデレーション組織のユーザーと通信する機能もありません。
- オンラインでの会議Skype for Business *オンプレミス* に自動的に移行されません。 ユーザーは、会議のスケジュールを変更するか、必要に応じて会議移行ツール [を使用する必要があります](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)。

### <a name="move-users-with-move-csuser"></a>ユーザーをユーザーに移動Move-CsUser

Move-CsUser管理シェル PowerShell ウィンドウからSkype for Business使用できます。 「必須の管理資格情報」の説明に従って、オンプレミス環境とクラウド サービス組織 (Microsoft 365 または Office 365) の両方で十分な特権を持っている[必要があります](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)。 両方の環境で特権を持つ 1 つのアカウントを使用するか、オンプレミスの資格情報を使用してオンプレミスの Skype for Business Server 管理シェル ウィンドウを起動し、パラメーターを使用して、必要な管理役割を持つ Microsoft 365 アカウントまたは Office 365 アカウントの資格情報を指定できます。 `-Credential`

Move-CsUser を使用してユーザーをオンプレミスに移動するには、次のコマンドを実行します。

- Identity パラメーターを使用して移動するユーザーを指定します。
- ユーザーをホストする必要なオンプレミス プールの完全修飾ドメイン名を指定して、-Target パラメーターを指定します。
- オンプレミスとクラウド サービス (Microsoft 365 または Office 365) の両方に十分なアクセス許可を持つアカウントが 1 つない場合は、-credential パラメーターを使用して、Microsoft 365 または Office 365 で十分なアクセス許可を持つアカウントを指定します。
- Microsoft 365 または Office 365 のアクセス許可を持つアカウントが "on.microsoft.com" で終わらない場合は、「必須の管理資格情報」の説明に従って、-HostedMigrationOverrideUrl パラメーターを[](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)正しい値で指定する必要があります。

次のコマンドレット シーケンスを使用して、ユーザーを Skype for Business Server に移動し、Microsoft 365 資格情報または Office 365 資格情報が別のアカウントであり、Get-Credential プロンプトの入力として指定されたと見なします。

```PowerShell
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
Move-CsUser -Identity username@contoso.com -Target pool.corp.contoso.com -Credential $cred -HostedMigrationOverrideUrl $url
```

### <a name="move-users-with-the-skype-for-business-server-control-panel"></a>コントロール パネルでユーザー Skype for Business Server移動する

1. コントロール パネル アプリSkype for Business Server開きます。
2. 左側のナビゲーションで、[ユーザー] を **選択します**。
3. [ **検索]** を使用して、オンプレミスに戻すユーザーを探します。
4. ユーザーを選択し、リストの上にある[アクション] ドロップダウンから [選択したユーザーをオンプレミスに移動する]**を選択します**。
5. ウィザードで、ユーザーをホストするユーザー プールを選択し、[次へ] を **クリックします**。
6. メッセージが表示されたら、.Microsoft 365でOffice 365で、十分なアクセス許可を持つアカウントを使用して、Microsoft 365 または onmicrosoft.com にサインインします。
7. [ **次へ]** をクリックし、[ **次** へ] をクリックしてもう 1 回ユーザーを移動します。
8. 成功または失敗に関する状態メッセージは、ウィザードではなく、メインのコントロール パネル アプリの上部に表示されます。

### <a name="removing-teamsonly-mode"></a>TeamsOnly モードの削除

CU8 で Skype for Business 2015 より前のバージョンを使用し、ユーザーが TeamsOnly モードでオンプレミスに戻される場合は、ユーザーをオンプレミスに移動する前に UpgradeToTeams インスタンスを削除する必要があります。 `TeamsUpgradePolicy` 別のモードでポリシーを明示的に付与するか、そのユーザーがグローバル ポリシーを使用する既存のポリシー割り当てを削除します (テナントのグローバル ポリシーが UpgradeToTeams ではない限り)。

TeamsUpgradePolicy のユーザーの割り当てを削除するには、次のコマンドレットを [オンライン PowerShell] ウィンドウSkype for Business実行します。

`Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName $null`

または、mode=TeamsOnly を持つ TeamsUpgradePolicy の別のインスタンスを割り当てるには、コマンドレットで PolicyName パラメーターの値として目的のインスタンスの名前を指定できます。 TeamsUpgradePolicy の使用可能なインスタンスの一覧を表示するには、Get-CsTeamsUpgradePolicy を実行します。


## <a name="see-also"></a>関連項目

[Move-CsUser](/powershell/module/skype/move-csuser)