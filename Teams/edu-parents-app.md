---
title: Microsoft EDU Parents アプリの管理者セットアップ (Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Microsoft Teamsの前提条件とセットアップについて説明している EDU の記事を参照してください。
ms.localizationpriority: Normal
ROBOTS: NOINDEX, NOFOLLOW
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0d875c6cd753e4c2e97477b3a3a88e0f071b5cbe
ms.sourcegitcommit: 05e7c8ac9d6d6f712742d08820d43118c8949bbc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/07/2021
ms.locfileid: "61322989"
---
# <a name="deploying-the-parents-app-in-microsoft-teams"></a>親アプリをデプロイするMicrosoft Teams

保護者向けアプリは、教師が Teams チャットを使用して、クラス チームの学生の保護者と安全に接続して関与するのに役立ちます。このチャットは、教師の組織全体で拡張されます。 保護者のすべてのデータは、IT スタッフがスムーズに設定学校データ同期を使用してプロビジョニングされます。

## <a name="requirements"></a>要件

### <a name="school-data-sync"></a>学校データ同期

- 各学生学校データ同期保護者に関連する連絡先情報を設定するには、SDS (ユーザー設定)**が必要** です。
  - [SDS を展開する](/schooldatasync/parent-contact-sync)

- SDS の設定と、テナント内の学生の保護者関連の連絡先の設定に関するサポートが必要な場合は、次の方法で EDU Customer Success チームに問い合わせてください。
  - RFA プロセスの完了[(FastTrack)。](https://www.microsoft.com/fasttrack?rtc=1)
  - サポート でチケットを開 [く](https://aka.ms/sdssupport)。

### <a name="teams-admin-center---policies"></a>Teams 管理センター - ポリシー

- クラス チームの所有者は、チャットを有効Teams必要があります。
- クラス チームの所有者は、組織によって管理されていないアカウントTeams **外部アクセス権を持っている必要** があります。
  - これは、テナント レベルとユーザー レベルで有効にする必要があります。 テナント レベルの設定は、管理センターの [>**外部** アクセスTeamsにあります。 この設定には、PowerShell を使用してアクセスできます。 ユーザー レベルの外部アクセス ポリシーには、PowerShell 経由でのみアクセスできます。 詳細なガイダンスについては、以下の PowerShell コマンドを参照してください。

## <a name="enabling-external-access-with-teams-accounts-not-managed-by-an-organization"></a>組織が管理していないアカウントTeams外部アクセスを有効にする

1. PowerShell モジュール プレビュー Microsoft Teams最新バージョンをインストールします。

    ```powershell
    Install-Module -Name PowerShellGet -Force -AllowClobber
    Install-Module -Name MicrosoftTeams -AllowPrerelease -Force –AllowClobber
    ```
    
2. 管理者特権を持つ資格情報を使用して、次のコマンドを実行します。

    ```powershell
    $credential = Get-Credential
    Connect-MicrosoftTeams -Credential $credential
    ```

ユーザー レベル () で組織によって管理されていない Teams アカウントを使用して外部アクセスを有効にするポリシー設定は、すべてのユーザー レベルの外部アクセス ポリシーに対して既定 `EnableTeamsConsumerAccess` で有効になっています。 ユーザーが組織によって管理されていない Teams アカウントを使用して外部アクセスを許可するには、テナント レベルの設定とユーザー レベルのポリシー設定の両方を有効にする必要があります。 テナント内のすべてのユーザーにこのアクセスを有効にしたくない場合は、テナント レベルの設定を無効にし、ユーザーに割り当てられているユーザー レベルの外部アクセス ポリシーを更新してから、テナント レベルの設定を有効にする必要があります。

どのユーザーレベルの外部アクセス ポリシーが存在し、誰に割り当てられているのか確認するには、次の手順を使用します。
    
3. どのユーザー レベルの外部アクセス ポリシーが存在するのかを確認します。

    ```powershell
    Get-CsExternalAccessPolicy
    ```

4. "グローバル" ポリシー以外の各ポリシーについて、ポリシーが割り当てられているユーザーを確認します。

   > [!NOTE]
   > 特定のポリシーが割り当てられていないユーザーは、"グローバル" ポリシーに戻されます。 テナントに追加された新しいユーザーには、"グローバル" ポリシーが割り当てられます。

    ```powershell
    Get-CsOnlineUser -Filter {ExternalAccessPolicy -eq "<PolicyName>"} | Select-Object DisplayName,ObjectId,UserPrincipalName
    ```

すべてのユーザー レベルの外部アクセス ポリシーは既定で true に設定されています。特定のユーザーの設定を調整する場合は、次の PowerShell コマンドレットを使用して、調整された設定で既存の外部アクセス ポリシーを作成/変更したり、ユーザーを新規または既存のポリシーに再割り当てすることができます `EnableTeamsConsumerAccess` `EnableTeamsConsumerAccess` 。

- 新しい外部アクセス ポリシーを作成する: [New-CsExternalAccessPolicy](/powershell/module/skype/new-csexternalaccesspolicy)

- 既存の外部アクセス ポリシー ("グローバル" ポリシーを含む) をカスタマイズする: [Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)

> [!NOTE]
> "FederationAndPICDefault"、"FederationOnly"、"NoFederationAndPIC" のサブスクリプションの既定のポリシーは変更できません。 既定ではすべてのユーザーに割り当てられた 'FederationAndPICDefault' ポリシーが使用されましたが、新しいユーザーには既定で "グローバル" ポリシーが割り当てられます。 これらのサブスクリプションの既定のポリシーが割り当てられているユーザーのポリシー設定を変更する必要がある場合は、正しい設定の異なるポリシーをこれらのユーザーに割り当てる必要があります。

- 1 人のユーザーに外部アクセス ポリシーを割り当てる: [Grant-CsExternalAccessPolicy](/powershell/module/skype/grant-csexternalaccesspolicy)

- 一連のユーザーにポリシーを割り当てる: [New-CsBatchPolicyAssignmentOperation](/powershell/module/skype/new-csbatchpolicyassignmentoperation)

テナント内のユーザーに対してユーザー レベルの外部アクセス ポリシーが正しく設定された後は、次のコマンドレットを使用して、テナントのテナント レベルの設定 ( `AllowTeamsConsumer` ) を有効にできます。

- テナントのフェデレーション構成設定を設定する: [Set-CsTenantFederationConfiguration](/powershell/module/skype/set-cstenantfederationconfiguration)

## <a name="enabling-the-parents-app"></a>保護者アプリの有効化

Parents アプリは既定で無効になっているので、クラス チームの所有者は、管理センターからアプリが許可されるまで、クラス チームのTeamsされません。 アプリは、パブリッシャーによってブロックされるアプリTeamsを使用して、管理センターから[許可できます](manage-apps.md#apps-blocked-by-publishers)。

アプリは、テナント レベルでいつでも、管理センターでアプリを[](manage-apps.md#allow-and-block-apps)許可およびブロックTeamsできます。 アプリがテナント レベルで無効になっている場合、ユーザー レベルのアクセス許可が有効になっている場合でも、すべてのユーザーに対してアプリがブロックされます。

アプリは、 の [アプリのアクセス許可ポリシーの管理] を使用して、ユーザー レベル[Microsoft Teams。](teams-app-permission-policies.md)

## <a name="more-information"></a>詳細情報

- [CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)
- [CsTenantFederationConfiguration](/powershell/module/skype/set-cstenantfederationconfiguration)
