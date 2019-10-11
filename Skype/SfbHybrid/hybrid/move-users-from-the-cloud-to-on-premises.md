---
title: クラウドからオンプレミスにユーザーを移動する
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
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
description: Skype for Business Online からオンプレミスにユーザーを移動する方法について説明します。
ms.openlocfilehash: ec3aa727753ed9ac6564712d591ab6d2beac4ebf
ms.sourcegitcommit: de7e0afbd40bbe52994ab99d85cf9e95ecbc4a6c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/09/2019
ms.locfileid: "37434730"
---
# <a name="move-users-from-the-cloud-to-on-premises"></a>クラウドからオンプレミスにユーザーを移動する 

必要に応じて、オンプレミスからクラウドに移行されたユーザー (Skype for Business Online または Teams のみを使用しているかどうか) をオンプレミスに移行できます。 Skype for business Online または TeamsOnly モードから、Skype for business Server のオンプレミス展開にユーザーを戻すには、両方のユーザーコマンドレットまたは Skype for Business Server コントロールパネルを使用します。これらは両方ともオンプレミスのツールです。 ユーザーをオンプレミス展開に戻した場合は、移動先のプールを決定する必要があります。

> [!Important]
> 以前は TeamsOnly モードでユーザーが以前のバージョンを使用していて、CU8 で Skype for business Server 2015 より前のバージョンを使用している場合は、そのユーザーの TeamsUpgradePolicy の TeamsOnly モードの割り当ても削除する必要があります。 オンプレミスのユーザーは、mode = TeamsOnly を持たない必要があります。  今後のバージョンの Skype for Business Server では、この割り当てが自動的に削除されます。 詳細については、「 [CsTeamsUpgradePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/grant-csteamsupgradepolicy)」を参照してください。

## <a name="prerequisites"></a>前提条件

- 「 [AZURE Ad connect を構成](configure-azure-ad-connect.md)する」の説明に従って、組織では、Azure ad connect が適切に構成されており、ユーザーの関連するすべての属性を同期している必要があります。
- オンラインからオンプレミスに移行するユーザーは、オンプレミスの Active Directory に既に存在している必要があります。
- 「 [Configure skype For business hybrid](configure-federation-with-skype-for-business-online.md)」で説明されているように、Skype for business ハイブリッドを構成する必要があります。

## <a name="moving-users-back-to-on-premises"></a>オンプレミスへのユーザーの移行

クラウドからオンプレミスにユーザーを戻すと、次のようになります。

- ユーザーは、その機能を利用するために Skype for Business Server の展開と対話します。 
- Skype for business Online または Teams のいずれかに存在していた連絡先は、Skype for Business Server に移行されます。 2つの連絡先セットが統合され、オンプレミスに移行されます。  また、Teams の既存の連絡先は Teams に残ります。
- ユーザーが Teams も使用している場合、Skype for Business ユーザーとの相互運用を行うことはできません。また、フェデレーション組織でユーザーと通信することもできません。
- Skype for Business Online の会議は、オンプレミスに自動的に移行される*ことはありません*。 ユーザーは会議を再スケジュールするか、必要に応じて[会議移行ツール](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)を使用する必要があります。

### <a name="move-users-with-move-csuser"></a>Move-CsUser を使用してユーザーを移動する

Move-CsUser は、オンプレミスの Skype for Business 管理シェル PowerShell ウィンドウから入手できます。 [必要な管理者の資格情報](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)で説明されているように、オンプレミス環境と Office 365 テナントの両方に十分な特権を持っている必要があります。 両方の環境で権限を持つ1つのアカウントを使用するか、オンプレミスの資格情報を使用してオンプレミスの Skype for Business Server 管理シェルウィンドウを`-Credential`開始することができます。また、パラメーターを使用して Office 365 の資格情報を指定することもできます。必要な Office 365 管理者の役割を持つアカウント。

Move-CsUser を使用してユーザーをオンプレミスに移動するには、次のようにします。

- Identity パラメーターを使用して移動するユーザーを指定します。
- -Target パラメーターに、ユーザーをホストする必要があるオンプレミスプールの完全修飾ドメイン名を指定します。
- オンプレミスと Office 365 の両方に十分な権限を持つアカウントが1つもない場合は、-credential パラメーターを使用して、Office 365 に十分な権限を持つアカウントを指定します。
- Office 365 のアクセス許可を持つアカウントが "on.microsoft.com" で終わっていない場合は、「[必要な管理者の資格情報](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)」に説明されているように、正しい値を指定して-HostedMigrationOverrideUrl パラメーターを指定する必要があります。

次のコマンドレットシーケンスを使用して、ユーザーを Skype for Business Server に移動できます。また、Office 365 資格情報が別のアカウントであると仮定して、資格情報の取得を求めるプロンプトの入力として指定します。

```
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
Move-CsUser -Identity username@contoso.com -Target pool.corp.contoso.com -Credential $cred -HostedMigrationOverrideUrl $url
```

### <a name="move-users-with-the-skype-for-business-server-control-panel"></a>Skype for Business Server コントロールパネルを使用してユーザーを移動する

1. Skype for Business Server コントロールパネルアプリを開きます。
2. 左側のナビゲーションで、[**ユーザー**] を選択します。
3. [**検索**] を使用して、オンプレミスに戻したいユーザーを検索します。
4. ユーザーを選択し、リストの上にある**アクション**ドロップダウンから、[**選択したユーザーをオンプレミスに移動**] を選択します。
5. ウィザードで、ユーザーをホストするユーザープールを選択し、[**次へ**] をクリックします。
6. メッセージが表示された場合は、onmicrosoft.com で終了し、十分な権限があるアカウントを使用して、Office 365 にサインインします。
7. [**次へ**] をクリックし、[**次**へ] をもう一度クリックして、ユーザーを移動します。
8. 成功または失敗に関するステータスメッセージは、ウィザードではなく、メインコントロールパネルアプリの上部に表示されることに注意してください。

### <a name="removing-teamsonly-mode"></a>TeamsOnly モードを削除する

CU8 を使用して Skype for Business 2015 より前のバージョンを使用していて、ユーザーを TeamsOnly モードでオンプレミスに戻した場合は、ユーザーをオンプレ`TeamsUpgradePolicy`ミスで移動する前に、の UpgradeToTeams インスタンスを削除する必要があります。 別のモードでポリシーを明示的に付与するか、グローバルポリシーを使用するようにそのユーザーの既存のポリシー割り当てを削除することができます (テナントのグローバルポリシーが Teams にアップグレードされていない場合)。

TeamsUpgradePolicy のユーザーの割り当てを削除するには、Skype for Business Online PowerShell ウィンドウから次のコマンドレットを実行します。

`Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName $null`

また、mode = TeamsOnly を持たない TeamsUpgradePolicy の別のインスタンスを割り当てるには、コマンドレットの PolicyName パラメーターの値として目的のインスタンスの名前を指定することもできます。 TeamsUpgradePolicy の使用可能なインスタンスの一覧を表示するには、CsTeamsUpgradePolicy を実行します。


## <a name="see-also"></a>関連項目

[Move-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/move-csuser)
