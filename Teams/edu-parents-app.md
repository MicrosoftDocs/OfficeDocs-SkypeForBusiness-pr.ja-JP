---
title: EDU Microsoft 保護者アプリの管理者セットアップ
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Microsoft Teams EDU の詳細については、保護者アプリの前提条件と PowerShell のセットアップに関する記事を参照してください。
ms.localizationpriority: Normal
ROBOTS: NOINDEX, NOFOLLOW
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8cd05f6ad2b238b4db2d611a6fc00e5f8a57189f
ms.sourcegitcommit: 6da1531dda6a0a3eecdca40e682783cc81c0d3e0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60785150"
---
# <a name="deploying-the-parents-app-in-microsoft-teams"></a>親アプリをアプリケーションにデプロイMicrosoft Teams

親アプリは、教師が教師組織全体で拡張される Teams チャットを使用して、クラス内の学生の保護者と安全に接続し、関与するのに役立ちます。 保護者のすべてのデータは、教師と IT スタッフがスムーズに設定できるように、学校データ同期 を使用してプロビジョニングされます。

## <a name="requirements"></a>要件

### <a name="school-data-sync"></a>学校データ同期

- 各学生学校データ同期連絡先情報を入力するには、SDS (データの取得 **) が必要** です。
  - [SDS を展開する](/schooldatasync/how-to-deploy-sds-using-sds-v2.1-csv-files)

- SDS を設定し、テナントで親の連絡先を有効にする方法についてサポートが必要な場合は、次の方法で EDU Customer Success チームに問い合わせてください。
  - RFA プロセスの完了[(FastTrack)。](https://www.microsoft.com/fasttrack?rtc=1)
  - サポート でチケットを開 [く](https://aka.ms/sdssupport)。

### <a name="teams-admins-center---policies"></a>Teams管理センター - ポリシー

- クラスの所有者がチャットを有効にする必要があります
- クラス所有者は、組織によって管理されていないTeams **を使用して外部アクセスを有効にする必要** があります。 
  - この設定は、テナント レベルの [ユーザー > 外部アクセス] で確認できます。または、特定のユーザー セットに対して有効にする場合は、以下の PowerShell を参照してください。

## <a name="enabling-federated-chat-on-a-per-user-basis"></a>ユーザーごとにフェデレーション チャットを有効にする

1. PowerShell モジュール プレビュー Microsoft Teams最新バージョンをインストールします。

    ```powershell
    Install-Module -Name PowerShellGet -Force -AllowClobber
    Install-Module -Name MicrosoftTeams -AllowPrerelease -Force –AllowClobber
    ```
    
2. 管理者特権を持つ資格情報を使用して、コマンド ウィンドウで次のコマンドを実行します。

    ```powershell
    $credential = Get-Credential
    Connect-MicrosoftTeams -Credential $credential
    ```

ユーザー レベルで Teams コンシューマーの外部アクセスを有効にするポリシー設定 (EnableTeamsConsumerAccess) は、すべてのユーザー レベルの外部アクセス ポリシーに対して既定で有効になっています。 テナント レベルの設定 (AllowTeamsConsumer) とユーザー レベルのポリシー設定の両方を、ユーザーがコンシューマーの外部アクセス権を持Teams必要があります。 テナント内のすべてのユーザーに Teams コンシューマーの外部アクセスを有効にしたくない場合は、テナント レベルの設定を有効にする前に、ユーザーに割り当てられているユーザー レベルの外部アクセス ポリシーを更新する必要があります。

存在するユーザー レベルの外部アクセス ポリシーと、そのポリシーが割り当てられているユーザーを確認する必要がある場合は、次の手順を使用できます。
    
3. どのユーザー レベルの外部アクセス ポリシーが存在するのかを確認します。

    ```powershell
    Get-CsExternalAccessPolicy -Include All
    ```

4. "グローバル" ポリシー以外の各ポリシーについて、ポリシーが割り当てられているユーザーを確認します。 注: 特定のポリシーが割り当てられていないユーザーは、"グローバル" ポリシーに戻されます。

    ```powershell
    Get-CsOnlineUser -Filter {ExternalAccessPolicy -eq "<PolicyName>"} | Select-Object DisplayName,ObjectId,UserPrincipalName
    ```

### <a name="further-powershell-options"></a>その他の PowerShell オプション

すべてのユーザー レベルの外部アクセス ポリシーには既定で EnableTeamsConsumerAccess が true に設定されています。これらのポリシーを更新して EnableTeamsConsumerAccess 設定を調整する場合は、次の PowerShell を使用して、調整された設定で新しい外部アクセス ポリシーを作成するか、ユーザーを新規または既存のポリシーに再割り当てできます。

- 新しい外部アクセス ポリシーを作成します (これにより、新しい外部アクセス ポリシーが作成され、設定が [定義されます):New-CsExternalAccessPolicy](/powershell/module/skype/new-csexternalaccesspolicy)

- 既存の外部アクセス ポリシーをカスタマイズする (グローバル ポリシーを含む既存の外部アクセス ポリシーの設定を変更する)): [Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)

> [!NOTE]
> "FederationAndPICDefault"、"FederationOnly"、"NoFederationAndPIC" のサブスクリプションの既定値は変更できません。 これらのポリシーが割り当てられているユーザーのポリシー設定を変更する必要がある場合は、正しい設定の異なるポリシーをこれらのユーザーに割り当てる必要があります。

- 1 人のユーザーに外部アクセス ポリシーを割り当てる: [Grant-CsExternalAccessPolicy](/powershell/module/skype/grant-csexternalaccesspolicy)

- 一連のユーザーにポリシーを割り当てる: [New-CsBatchPolicyAssignmentOperation](/powershell/module/skype/new-csbatchpolicyassignmentoperation)

すべてのユーザーに対してユーザー レベルの外部アクセス ポリシーが正しく設定されていることを確信したら、次のコマンドレットを使用して、テナントの Teams コンシューマー外部アクセスを制御するテナント レベルの設定を有効にできます。

- テナントのフェデレーション構成設定を設定する (AllowTeamsConsumer を true に設定): [Set-CsTenantFederationConfiguration (SkypeForBusiness)](/powershell/module/skype/set-cstenantfederationconfiguration)

### <a name="disabling-the-parents-app"></a>保護者アプリを無効にする

保護者アプリは既定で有効になっているので、クラスのすべての所有者はクラス チームにアプリを表示します。 アプリは、テナント 管理センターの [[](manage-apps.md#allow-and-block-apps)アプリの許可とブロック] を使用してMicrosoft Teamsできます。 これがテナント レベルで無効になっている場合、ユーザー レベルのアクセス許可が有効になっている場合でも、すべてのユーザーに対してブロックされます。

[アプリのアクセス許可ポリシーを管理する] を使用して、ユーザー レベルMicrosoft Teams。(teams-app-permission-policies.md)。

## <a name="more-information"></a>詳細情報

- [CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)
- [ユーザーへのポリシーの割り当て](/powershell/module/skype/grant-csexternalaccesspolicy)
