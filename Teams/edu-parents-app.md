---
title: Microsoft Teams for Education での保護者の管理者Microsoft Teams for Education
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Microsoft Teamsの前提条件とセットアップについて説明した記事Microsoft Teams for Education。
ms.localizationpriority: Normal
ROBOTS: NOINDEX, NOFOLLOW
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: af6433cb3e5ca0e1849322bdd128915e826e219b
ms.sourcegitcommit: 2044fdcb0c5db10dbc77c5d66e382c1b927ccdc4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/01/2022
ms.locfileid: "63040065"
---
# <a name="set-up-parent-connection-in-microsoft-teams-for-education"></a>[親接続の設定] Microsoft Teams for Education

Microsoft Teams for Education の親接続は、教師が Teams チャットを使用して、クラス チームの学生の保護者と安全に接続し、関与するのに役立ちます。このチャットは、教師の組織全体で拡張されます。 保護者のすべてのデータは、IT スタッフがスムーズに設定学校データ同期を使用してプロビジョニングされます。

保護者は、設定が完了したら、チャットを使って学生の教師とTeamsできます。 保護者を教師に接続する方法のガイダンスについては、「Connectの教師と一緒に[Teams。](https://support.microsoft.com/topic/connect-with-educators-in-teams-ec2430c3-952a-4ba4-9891-1d1cab577960)

保護者は教師ありチャットでも機能します。 保護者は完全な Teams アクセス許可を持たなかったり、学生との会話を開始したり、フルアクセス許可のユーザー (教師など) をチャットから削除したりすることはできません。 教師ありチャットの詳細については、「[教師ありチャット](supervise-chats-edu.md)を使用する」を参照Microsoft Teams。

## <a name="requirements"></a>要件

### <a name="school-data-sync"></a>学校データ同期

- 各学生学校データ同期保護者に関連する連絡先情報を入力するには、SDS (サポート情報) **が必要** です。
  - [SDS を展開する](/schooldatasync/parents-and-guardians-in-sds)

- SDS の設定と、テナント内の学生の保護者関連の連絡先の設定に関するサポートが必要な場合は、次の方法で EDU Customer Success チームに問い合わせてください。
  - RFA プロセスの[完了 (FastTrack](https://www.microsoft.com/fasttrack?rtc=1))。
  - サポートでチケットを開 [く](https://aka.ms/sdssupport)。

- 現在、SDS では、親連絡先の CSV ベースのデータ インジェストのみをサポートしています。ただし、すべてのリスト データに [PowerSchool API Sync](/schooldatasync/how-to-deploy-school-data-sync-by-using-powerschool-sync) または [OneRoster API Sync](/schooldatasync/how-to-deploy-school-data-sync-by-using-oneroster-sync) を使用し、CSV を使用して親連絡先を追加できます。
  - [SDS v1 CSV 同期形式を使用して、2 つ目の同期プロファイルを作成します](/schooldatasync/school-data-sync-format-csv-files-for-sds)。
  - 残りの v1 ファイルが空 [の 2](/schooldatasync/parent-contact-sync-file-format) つの親ファイルをプルします (ヘッダーだけ)。
    - User.csv
    - Guardianrelationship.csv
  - v1 CSV ファイルのサンプル セットを表示するには、「最小必須属性」を参照GitHub[してください](https://github.com/OfficeDev/O365-EDU-Tools/tree/master/CSV%20Samples/SDS%20Format/Min%20Required%20Attributes)。
  - 初期同期後に CSV ファイルのプルを自動化する場合は、CSV ファイル同期 Automation に関する [ドキュメントを参照してください](/schooldatasync/csv-file-sync-automation)。
  - SDS データ同期の設定に関するヘルプが必要な場合[](https://www.microsoft.com/fasttrack?rtc=1)は、カスタマー サクセス チームに連絡するか、サポート [チケットを開きます](https://edusupport.microsoft.com/support?product_id=data_sync)。

### <a name="teams-admin-center---policies"></a>Teams 管理センター - ポリシー

- クラス チームの所有者は、チャットTeamsオンになっている必要があります。
- クラス チームの所有者は、組織によって管理されていないアカウントTeams **外部アクセス権を持っている** 必要があります。
  - これは、テナント レベルとユーザー レベルで有効になっている必要があります。 テナント レベルの設定は、管理センターの [ユーザー> **外部** アクセス] Teamsにあります。 この設定には、PowerShell を使用してアクセスできます。 ユーザー レベルの外部アクセス ポリシーには、PowerShell 経由でのみアクセスできます。 詳細なガイダンスについては、以下の PowerShell コマンドを参照してください。

> [!NOTE]
>保護者は、保護者機能で外部ユーザーとして分類されます。つまり、完全なテナント権限はありません。 ユーザーは、追加されたチャットまたはチャットだけでなく、チャットで共有されているファイル、画像、その他のコンテンツにのみアクセスできます。
>
>また、外部ユーザーは組織のユーザーのプレゼンス (オフライン、利用可能、取り込み中など) を確認できますが、これは PowerShell を使用してユーザーのプライバシーを保護するためにオフにできます。 PowerShell で [Set-CsPrivacyConfiguration を使用し、](/powershell/module/skype/set-csprivacyconfiguration?view=skype-ps) を設定します ``EnablePrivacyMode=true``。
>
>保護者が外部ユーザーである場合でも、チャットへの投稿は検出可能です。 「電子情報開示の調査を行Teams電子情報開示調査を行う」を参照して、電子情報開示調査を実施[する方法Microsoft Teams](ediscovery-investigation.md)。

## <a name="allow-external-access-with-teams-accounts-not-managed-by-an-organization"></a>組織が管理していないアカウントTeams外部アクセスを許可する

教師が Teams で保護者と通信するには、教育機関のテナントの IT 管理者がテナントのポリシーを更新して、テナントの外部の Teams アカウントに対する外部アクセスを許可する必要があります。 外部アクセスの管理の詳細については、「外部アクセスの管理」を参照[Microsoft Teams](manage-external-access.md)。

保護者の外部アクセスを有効にする手順を次に示します。

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

    ユーザー レベル (`EnableTeamsConsumerAccess`) で組織によって管理されていない Teams アカウントで外部アクセスを有効にするポリシー設定は、すべてのユーザー レベルの外部アクセス ポリシーに対して既定で有効になっています。 ユーザーが組織によって管理されていない Teams アカウントで外部アクセスを持つには、テナント レベルの設定とユーザー レベルのポリシー設定の両方を有効にする必要があります。 テナント内のすべてのユーザーにこのアクセスを有効にしたくない場合は、テナント レベルの設定がオフになっていることを確認し、ユーザーに割り当てられているユーザー レベルの外部アクセス ポリシーを更新してから、テナント レベルの設定を有効にする必要があります。

    どのユーザーレベルの外部アクセス ポリシーが存在し、誰に割り当てられているのか確認するには、次の手順を使用します。

3. ユーザー レベルの外部アクセス ポリシーが存在する必要があります。

    ```powershell
    Get-CsExternalAccessPolicy
    ```

4. "グローバル" ポリシー以外の各ポリシーについて、ポリシーが割り当てられているユーザーを確認します。

   > [!NOTE]
   > 特定のポリシーが割り当てられていないユーザーは、"グローバル" ポリシーに戻されます。 テナントに追加された新しいユーザーには、"グローバル" ポリシーが割り当てられます。

    ```powershell
    Get-CsOnlineUser -Filter {ExternalAccessPolicy -eq "<PolicyName>"} | Select-Object DisplayName,ObjectId,UserPrincipalName
    ```

`EnableTeamsConsumerAccess`すべてのユーザー レベルの外部アクセス ポリシーは既定で true `EnableTeamsConsumerAccess` に設定されています。特定のユーザーの設定を調整する場合は、次の PowerShell コマンドレットを使用して、調整された設定で既存の外部アクセス ポリシーを作成/変更したり、ユーザーを新規または既存のポリシーに再割り当てすることができます。

- 新しい外部アクセス ポリシーを作成する: [New-CsExternalAccessPolicy](/powershell/module/skype/new-csexternalaccesspolicy)

- 既存の外部アクセス ポリシー ("グローバル" ポリシーを含む) をカスタマイズする: [Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)

> [!NOTE]
> "FederationAndPICDefault"、"FederationOnly"、"NoFederationAndPIC" のサブスクリプションの既定のポリシーは変更できません。 既定ではすべてのユーザーに割り当てられた 'FederationAndPICDefault' ポリシーが使用されましたが、新しいユーザーには既定で "グローバル" ポリシーが割り当てられます。 これらのサブスクリプションの既定のポリシーが割り当てられているユーザーのポリシー設定を変更する必要がある場合は、正しい設定の異なるポリシーをこれらのユーザーに割り当てる必要があります。

- 1 人のユーザーに外部アクセス ポリシーを割り当てる: [Grant-CsExternalAccessPolicy](/powershell/module/skype/grant-csexternalaccesspolicy)

- 一連のユーザーにポリシーを割り当てる: [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation)

テナント内のユーザーに対してユーザー レベルの外部アクセス ポリシーが正しく設定された後は、次のコマンドレットを使用して、テナントのテナント レベルの設定 (`AllowTeamsConsumer`) を有効にできます。

- テナントのフェデレーション構成設定を設定する: [Set-CsTenantFederationConfiguration](/powershell/module/skype/set-cstenantfederationconfiguration)

## <a name="turn-on-the-parents-app-in-the-teams-admin-center"></a>管理センターで保護者アプリをTeamsする

保護者アプリは既定で無効になっているので、クラス チームの所有者は、管理センターで許可されるまで、クラス チームのTeamsされません。 保護者向けアプリは、パブリッシャーによってブロックTeamsアプリを許可するを使用して、管理センター[で有効にされます](manage-apps.md#apps-blocked-by-publishers)。

アプリは、管理センターの [許可] と [ブロック] を使用[](manage-apps.md#allow-and-block-apps)して、テナント レベルTeamsできます。 テナント レベルでオフになっている場合、ユーザー レベルのアクセス許可が有効になっている場合でも、すべてのユーザーに対してブロックされます。

Parents アプリは、アプリのアクセス許可ポリシーの管理を使用して、ユーザー レベルでオフ[Microsoft Teams](teams-app-permission-policies.md)。

## <a name="more-information"></a>詳細情報

- [CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)
- [CsTenantFederationConfiguration](/powershell/module/skype/set-cstenantfederationconfiguration)
