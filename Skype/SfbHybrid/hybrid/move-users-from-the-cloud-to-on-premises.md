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
description: Skype for Business Online からオンプレミスにユーザーを移動する方法について学習します。
ms.openlocfilehash: fdc8a8fb4e8e6cb1e2426b067aefbfa25e808171
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110613"
---
# <a name="move-users-from-the-cloud-to-on-premises"></a>クラウドからオンプレミスにユーザーを移動する 

必要に応じて、以前にオンプレミスからクラウドに移行されたユーザー (Skype for Business Online または Teams Only を使用する場合) をオンプレミスに移動できます。 Skype for Business Online または TeamsOnly モードから Skype for Business Server のオンプレミス展開に戻す場合は、Move-CsUser コマンドレットまたは Skype for Business Server コントロール パネルのいずれかを使用します。どちらもオンプレミス ツールです。 ユーザーをオンプレミス展開に戻す場合は、ユーザーを移動するプールを決定する必要があります。

> [!Important]
> ユーザーが以前 TeamsOnly モードで、CU8 を使用して Skype for Business Server 2015 より前のバージョンを使用している場合は、そのユーザーの TeamsUpgradePolicy の TeamsOnly モードの割り当てを削除する必要があります。 オンプレミスのユーザーは mode= TeamsOnly を持つ必要があります。  以降のバージョンの Skype for Business Server では、この割り当てが自動的に削除されます。 詳細については [、「Grant-CsTeamsUpgradePolicy」を参照してください](/powershell/module/skype/grant-csteamsupgradepolicy)。

## <a name="prerequisites"></a>前提条件

- 「Configure Azure AD Connect」の説明に従って、組織は AD Azure AD Connect を適切に構成し、ユーザーに関連 [するすべての属性を同期している必要があります](configure-azure-ad-connect.md)。
- オンラインからオンプレミスに移動するユーザーは、オンプレミスの Active Directory に既に存在している必要があります。
- 「Skype for Business ハイブリッドの構成」の説明に従って [、Skype for Business ハイブリッドを構成する必要があります](configure-federation-with-skype-for-business-online.md)。

## <a name="moving-users-back-to-on-premises"></a>ユーザーをオンプレミスに戻す

ユーザーをクラウドからオンプレミスに戻したら、次の方法を実行します。

- ユーザーは、その機能のために Skype for Business Server の展開を操作します。 
- Skype for Business Online または Teams に存在していた連絡先は、Skype for Business Server に移行されます。 2 つの連絡先セットが結合され、オンプレミスに移行されます。  さらに、Teams に既存の連絡先は Teams に残ります。
- ユーザーが Teams も使用している場合、Skype for Business ユーザーと相互運用する機能も、フェデレーション組織のユーザーと通信する機能もありません。
- Skype for Business Online の会議 *は、* オンプレミスに自動的に移行されません。 ユーザーは、会議のスケジュールを変更するか、必要に応じて会議移行ツール [を使用する必要があります](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)。

### <a name="move-users-with-move-csuser"></a>ユーザーをユーザーに移動Move-CsUser

Move-CsUserは、オンプレミスの Skype for Business Management Shell PowerShell ウィンドウから利用できます。 「必須の管理資格情報」の説明に従って、オンプレミス環境とクラウド サービス組織 (Microsoft 365 または Office 365) の両方で十分な特権を持っている [必要](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)があります。 両方の環境で特権を持つ 1 つのアカウントを使用するか、オンプレミスの資格情報を使用してオンプレミスの Skype for Business Server 管理シェル ウィンドウを起動し、パラメーターを使用して、必要な管理役割を持つ `-Credential` Microsoft 365 または Office 365 アカウントの資格情報を指定できます。

Move-CsUser を使用してユーザーをオンプレミスに移動するには、次のコマンドを実行します。

- Identity パラメーターを使用して移動するユーザーを指定します。
- ユーザーをホストする必要なオンプレミス プールの完全修飾ドメイン名を指定して、-Target パラメーターを指定します。
- オンプレミスとクラウド サービス (Microsoft 365 または Office 365) の両方に十分なアクセス許可を持つアカウントが 1 つない場合は、-credential パラメーターを使用して、Microsoft 365 または Office 365 で十分なアクセス許可を持つアカウントを指定します。
- Microsoft 365 または Office 365 のアクセス許可を持つアカウントが "on.microsoft.com" で終了しない場合は、-HostedMigrationOverrideUrl パラメーターを指定し、「必須の[](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)管理資格情報」で説明したように正しい値を指定する必要があります。

次のコマンドレット シーケンスを使用して、ユーザーを Skype for Business Server に移動し、Microsoft 365 または Office 365 資格情報が別のアカウントであり、Get-Credential プロンプトの入力として提供されたと見なします。

```PowerShell
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
Move-CsUser -Identity username@contoso.com -Target pool.corp.contoso.com -Credential $cred -HostedMigrationOverrideUrl $url
```

### <a name="move-users-with-the-skype-for-business-server-control-panel"></a>Skype for Business Server コントロール パネルを使用してユーザーを移動する

1. Skype for Business Server コントロール パネル アプリを開きます。
2. 左側のナビゲーションで、[ユーザー] を **選択します**。
3. [ **検索]** を使用して、オンプレミスに戻すユーザーを探します。
4. ユーザーを選択し、リストの上にある[アクション] ドロップダウンから [選択したユーザーをオンプレミスに移動する]**を選択します**。
5. ウィザードで、ユーザーをホストするユーザー プールを選択し、[次へ] を **クリックします**。
6. メッセージが表示されたら、Microsoft 365 または Office 365 に .onmicrosoft.com で終了し、十分なアクセス許可を持つアカウントでサインインします。
7. [ **次へ]** をクリックし、[ **次** へ] をクリックしてもう 1 回ユーザーを移動します。
8. 成功または失敗に関する状態メッセージは、ウィザードではなく、メインのコントロール パネル アプリの上部に表示されます。

### <a name="removing-teamsonly-mode"></a>TeamsOnly モードの削除

CU8 で Skype for Business 2015 より前のバージョンを使用している場合、ユーザーが TeamsOnly モードでオンプレミスに戻される場合は、ユーザーをオンプレミスに移動する前に UpgradeToTeams インスタンスを削除する必要があります。 `TeamsUpgradePolicy` 別のモードでポリシーを明示的に付与するか、そのユーザーがグローバル ポリシーを使用する既存のポリシー割り当てを削除します (テナントのグローバル ポリシーが UpgradeToTeams ではない限り)。

TeamsUpgradePolicy のユーザーの割り当てを削除するには、Skype for Business Online PowerShell ウィンドウから次のコマンドレットを実行します。

`Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName $null`

または、mode=TeamsOnly を持つ TeamsUpgradePolicy の別のインスタンスを割り当てるには、コマンドレットで PolicyName パラメーターの値として目的のインスタンスの名前を指定できます。 TeamsUpgradePolicy の使用可能なインスタンスの一覧を表示するには、Get-CsTeamsUpgradePolicy を実行します。


## <a name="see-also"></a>関連項目

[Move-CsUser](/powershell/module/skype/move-csuser)