---
title: Microsoft Teams for Educationでの保護者の管理設定
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Microsoft Teams for Educationでの保護者の前提条件とセットアップに関する記事Microsoft Teams。
ms.localizationpriority: Normal
ROBOTS: NOINDEX, NOFOLLOW
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ccc69a07d523b046298643ad387e31e25138096f
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676129"
---
# <a name="set-up-parent-connection-in-microsoft-teams-for-education"></a>Microsoft Teams for Educationで親接続を設定する

Microsoft Teams for Educationの親接続は、教育者がTeamsを使用して、クラス チームの学生の保護者と安全に接続して関わるのに役立ちます。

この記事では、親接続の要件とセットアップに関する教育 IT プロフェッショナル向けのガイダンスを提供します。

## <a name="share-guardian-and-educator-resources"></a>保護者と教育者のリソースを共有する

IT 管理者が保護者や教育者と親接続の使用を開始する方法について共有できるリソースを次に示します。

- 保護者の設定に関するガイダンスについては、[Teamsの教育者とのConnectを](https://support.microsoft.com/topic/connect-with-educators-in-teams-ec2430c3-952a-4ba4-9891-1d1cab577960)参照してください。
- 教育者のセットアップに関するガイダンスについては、「[Microsoft Teamsで保護者とコミュニケーションを](https://support.microsoft.com/topic/communicate-with-guardians-in-microsoft-teams-01471ecd-eb5d-4eda-9c5d-0064d672960e?ui=en-us&rs=en-us&ad=us)取る」を参照してください。

## <a name="benefits-of-parent-connection"></a>親接続の利点

保護者向け接続を使用すると、教育者や保護者は、Teamsを使用してチャット、電子メール、通話を行うことができます。

- Teams保護者の連絡先データは、学校データ同期 (SDS) を使用して SIS で最新の状態を維持します。
- 監視付きチャットで動作します。 詳細については、「[Microsoft Teamsで監視付きチャットを使用する](supervise-chats-edu.md)」を参照してください。
  - 保護者は既定でアクセス許可を制限しているため、学生とチャットしたり、チャットからユーザーを削除したりすることはできません。
  - この設定は、テナント管理者が変更できます。
- 教師は保護者とチャットを開始できます。
  - 保護者がTeamsコンシューマー アカウントを持っていない場合は、教育者からの最初のメッセージと、Teamsに移動するための電子メール招待が届きます。
- 教師は保護者のメールをクリックして、ネイティブメール クライアントを使用してメールを送信できます。
- 教師は保護者の電話番号をクリックして、Teams内で電話をかけることができます。

> [!IMPORTANT]
> Teamsでクリックして機能を呼び出すには、テナントが必要です。
>
> - Public Branch Exchange (PBX) 機能。
> - PSTN への接続。
>
> Microsoft 365 A1および A3 プランには、PBX 機能や PSTN 接続は含まれません。 [これらのそれぞれに対してアドオン ライセンスを](/teams-add-on-licensing/microsoft-teams-add-on-licensing)購入できます。
>
> Microsoft 365 A5プランには、Teams 電話システムを使用した PBX 機能のみが含まれます。 引き続き[、Teams通話プランを購入するか、サード パーティのソリューションを使用](pstn-connectivity.md)して PSTN の外部番号に接続する必要があります。
>
> PSTN 接続を取得するためのすべてのオプションの詳細については、「 [PSTN 接続オプション」を](pstn-connectivity.md)参照してください。
>
> ライセンスの呼び出しTeamsの詳細については、「[アドオン ライセンス オプションTeams](/teams-add-on-licensing/microsoft-teams-add-on-licensing)参照してください。

## <a name="requirements"></a>要件

### <a name="school-data-sync"></a>学校データ同期

- 各学生の親および保護者 **関連の連絡先情報** を設定するには、学校データ同期 (SDS) が必要です。
  - [SDS を展開する](/schooldatasync/parents-and-guardians-in-sds)

- テナント内の学生のSDSの設定と保護者 **関連の連絡先** の設定に関するサポートが必要な場合は、次の方法で EDU Customer Success チームにお問い合わせください。
  - [FastTrack](https://www.microsoft.com/fasttrack?rtc=1)で RFA プロセスを完了する。
  - [サポート](https://aka.ms/sdssupport)でチケットを開きます。

- 現在、SDSでは親連絡先の CSV ベースのデータ インジェストのみがサポートされています。ただし、すべての名簿データに [PowerSchool API Sync](/schooldatasync/how-to-deploy-school-data-sync-by-using-powerschool-sync) または [OneRoster API Sync](/schooldatasync/how-to-deploy-school-data-sync-by-using-oneroster-sync) を使用し、CSV を使用して親連絡先を追加することができます。
  - [SDS v1 CSV 同期形式](/schooldatasync/school-data-sync-format-csv-files-for-sds)を使用して、2 つ目の同期プロファイルを作成します。
  - 設定された 2 つの [親ファイル](/schooldatasync/parent-contact-sync-file-format) をプルし、残りの v1 ファイルを空にします (ヘッダーのみ)。
    - User.csv
    - Guardianrelationship.csv
  - v1 CSV ファイルのサンプル セットを表示するには、「[最小必須属性GitHubファイル」を](https://github.com/OfficeDev/O365-EDU-Tools/tree/master/CSV%20Samples/SDS%20Format/Min%20Required%20Attributes)参照してください。
  - 初期同期後に CSV ファイルのプルを自動化する場合は、[CSV File Sync Automation ドキュメント](/schooldatasync/csv-file-sync-automation)を参照してください。
  - SDSデータ同期の設定については、[カスタマー サクセス チーム](https://www.microsoft.com/fasttrack?rtc=1)に連絡するか、[サポート チケットを開いてください](https://edusupport.microsoft.com/support?product_id=data_sync)。

### <a name="teams-admin-center-policies"></a>管理センター ポリシーをTeamsする

- クラス チームの所有者は、チャットTeams有効にする必要があります。
- クラス チームの所有者は、**組織が管理していないTeams アカウント** を有効にした外部アクセス権を持っている必要があります。
  - これは、テナント レベルとユーザー レベルで有効にする必要があります。 テナント レベルの設定は、Teams管理センターの **ユーザー >外部アクセス** にあります。 この設定には、PowerShell を使用してアクセスすることもできます。 ユーザー レベルの外部アクセス ポリシーには、PowerShell 経由でのみアクセスできます。 詳細については、以下の PowerShell コマンドを参照してください。

#### <a name="parent-and-guardian-restrictions"></a>親と保護者の制限
保護者は、保護者接続の外部ユーザーとして分類されます。つまり、完全なテナント権限がありません。 追加したチャットやチャットにアクセスできるのは、チャット内で共有されているファイル、画像、その他のコンテンツだけです。

また、外部ユーザーは組織のユーザーのプレゼンス (オフライン、使用可能、ビジーなど) を表示できますが、PowerShell を使用してユーザーのプライバシーを保護するためにオフにすることができます。 PowerShell では、 [Set-CsPrivacyConfiguration](/powershell/module/skype/set-csprivacyconfiguration) と set ``EnablePrivacyMode=true``を使用します。

保護者が外部ユーザーであっても、チャットへの貢献は検出可能です。 Microsoft Teamsでコンテンツの電子情報開示調査を実施する方法に関する記事を参照して[、Teams電子情報開示調査を実施](ediscovery-investigation.md)する方法について説明します。

#### <a name="blocking-a-parent-or-guardian-in-a-chat"></a>チャットで親または保護者をブロックする
教師は、親接続で開始されたチャットで保護者をブロックできます。

クラスの所有者は、次のことができます。

1. 保護者のプロフィール カードを開き、省略記号と **ブロック ユーザー** を選択します。
2. 次に、チャットから保護者を削除します。

ブロックされたユーザーは、クラスの所有者と追加のチャットを開始できません。

## <a name="allow-external-access-with-teams-accounts-not-managed-by-an-organization"></a>組織で管理されていないTeams アカウントで外部アクセスを許可する

教育者がTeamsで保護者と通信できるようにするには、教育テナントの IT 管理者がテナントのポリシーを更新して、テナント外のTeams アカウントに対する外部アクセスを許可する必要があります。 外部アクセスの管理の詳細については、「[Microsoft Teamsの外部アクセスの管理](manage-external-access.md)」を参照してください。

保護者向けの外部アクセスを有効にする手順を次に示します。

1. 最新のMicrosoft Teams PowerShell モジュール プレビューをインストールします。

    ```powershell
    Install-Module -Name PowerShellGet -Force -AllowClobber
    Install-Module -Name MicrosoftTeams -AllowPrerelease -Force –AllowClobber
    ```

2. 管理者特権を持つ資格情報を使用して、次のコマンドを実行します。

    ```powershell
    $credential = Get-Credential
    Connect-MicrosoftTeams -Credential $credential
    ```

    ユーザー レベル (`EnableTeamsConsumerAccess`) で組織によって管理されていないTeams アカウントを使用して外部アクセスを有効にするポリシー設定は、すべてのユーザー レベルの外部アクセス ポリシーに対して既定でオンになっています。 ユーザーが組織によって管理されていないTeams アカウントで外部アクセス権を持つには、テナント レベルの設定とユーザー レベルのポリシー設定の両方を有効にする必要があります。 テナント内のすべてのユーザーにこのアクセスを有効にしたくない場合は、テナント レベルの設定がオフになっていることを確認し、ユーザーに割り当てられているユーザー レベルの外部アクセス ポリシーを更新してから、テナント レベルの設定をオンにする必要があります。

    どのユーザー レベルの外部アクセス ポリシーが存在し、誰に割り当てられているかを確認するには、次の手順を使用します。

3. ユーザー レベルの外部アクセス ポリシーが存在することを確認します。

    ```powershell
    Get-CsExternalAccessPolicy
    ```

4. 'Global' ポリシー以外のポリシーごとに、ポリシーが割り当てられているユーザーを確認します。

   > [!NOTE]
   > 特定のポリシーが割り当てられていないユーザーは、"グローバル" ポリシーにフォールバックします。 テナントに追加されたすべての新しいユーザーには、"グローバル" ポリシーが割り当てられます。

    ```powershell
    Get-CsOnlineUser -Filter {ExternalAccessPolicy -eq "<PolicyName>"} | Select-Object DisplayName,ObjectId,UserPrincipalName
    ```

すべてのユーザー レベルの外部アクセス ポリシーは `EnableTeamsConsumerAccess` 既定で true に設定されているため、特定のユーザーの設定を調整 `EnableTeamsConsumerAccess` する場合は、次の PowerShell コマンドレットを使用して、設定を調整して既存の外部アクセス ポリシーを作成または変更したり、新しいポリシーまたは既存のポリシーにユーザーを再割り当てしたりできます。

- 新しい外部アクセス ポリシーの作成: [New-CsExternalAccessPolicy](/powershell/module/skype/new-csexternalaccesspolicy)

- 既存の外部アクセス ポリシーをカスタマイズする ("グローバル" ポリシーを含む): [Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)

> [!NOTE]
> 次のサブスクリプションの既定のポリシーは変更できません。'FederationAndPICDefault'、'FederationOnly'、'NoFederationAndPIC'。 'FederationAndPICDefault' ポリシーは、既定ですべてのユーザーに割り当て以前は使用されましたが、新しいユーザーには既定で 'Global' ポリシーが割り当てられます。 これらのサブスクリプションの既定のポリシーが割り当てられているユーザーのポリシー設定を変更する必要がある場合は、これらのユーザーに正しい設定で異なるポリシーを割り当てます。

- 1 人のユーザーに外部アクセス ポリシーを割り当てる: [Grant-CsExternalAccessPolicy](/powershell/module/skype/grant-csexternalaccesspolicy)

- 一連のユーザーにポリシーを割り当てる: [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation)

テナント内のユーザーに対してユーザー レベルの外部アクセス ポリシーが正しく設定されたら、次のコマンドレットを使用してテナントのテナント レベルの設定 (`AllowTeamsConsumer`) を有効にすることができます。

- テナントのフェデレーション構成設定を設定する: [Set-CsTenantFederationConfiguration](/powershell/module/skype/set-cstenantfederationconfiguration)

## <a name="turn-on-the-parents-app-in-the-teams-admin-center"></a>Teams管理センターで保護者向けアプリを有効にする

保護者向けアプリは既定でオフになっているため、クラス チームの所有者は、Teams管理センターを通じて許可されるまで、そのアプリをクラス チームに表示しません。 保護者向けアプリは、[発行元によってブロックされた](manage-apps.md#apps-blocked-by-publishers)アプリを許可するを使用して、Teams管理センターで有効になっています。

アプリはいつでも、Teams管理センターでアプリを[許可およびブロック](manage-apps.md#allow-and-block-apps)して、テナント レベルでオフにすることができます。 テナント レベルでオフになっている場合、ユーザー レベルのアクセス許可がオンになっている場合でも、すべてのユーザーに対してブロックされます。

保護者向けアプリは、[Microsoft Teamsのアプリアクセス許可ポリシーの管理](teams-app-permission-policies.md)を使用して、ユーザー レベルでオフにすることもできます。

## <a name="more-information"></a>詳細情報

- [CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)
- [CsTenantFederationConfiguration](/powershell/module/skype/set-cstenantfederationconfiguration)
