---
title: Microsoft Teams for Educationでの保護者の管理設定
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Microsoft Teams for Educationでの保護者の前提条件とセットアップを文書化した Microsoft Teams の記事。
ms.localizationpriority: Normal
ROBOTS: NOINDEX, NOFOLLOW
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b4cb61038c08739afcd6a48825f8ddaa0cb7c573
ms.sourcegitcommit: 22f66e314e631b3c9262c5c7dc5664472f42971e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2022
ms.locfileid: "68912816"
---
# <a name="set-up-parent-connection-in-microsoft-teams-for-education"></a>Microsoft Teams for Educationで親接続を設定する

Microsoft Teams for Educationの親接続は、教育者が Teams を使用して、クラス チームの学生の保護者と安全に接続し、関与するのに役立ちます。

この記事では、保護者の接続の要件とセットアップに関する教育 IT プロフェッショナルにガイダンスを提供します。

## <a name="share-guardian-and-educator-resources"></a>保護者と教師のリソースを共有する

ここでは、IT 管理者が保護者や教師と親接続の使用を開始する方法について共有できるリソースをいくつか示します。

- 保護者の設定に関するガイダンスについては、「 [Teams で教師と接続する](https://support.microsoft.com/topic/connect-with-educators-in-teams-ec2430c3-952a-4ba4-9891-1d1cab577960)」を参照してください。
- 教師のセットアップに関するガイダンスについては、「 [Microsoft Teams で保護者と通信する](https://support.microsoft.com/topic/communicate-with-guardians-in-microsoft-teams-01471ecd-eb5d-4eda-9c5d-0064d672960e?ui=en-us&rs=en-us&ad=us)」を参照してください。

## <a name="benefits-of-parent-connection"></a>親接続の利点

保護者接続を使用すると、教師と保護者は Teams を使用してチャット、メール、通話を行うことができます。

- 教師は保護者とチャットを開始できます。
  - 保護者が Teams コンシューマー アカウントを持っていない場合、または Teams にまだ参加していない場合は、教育者からメッセージと共に、Teams に移動するための電子メールの招待を受け取ります。 これは、招待の制限に達していない場合にのみ適用され、チャットは親接続から再入力された新しいチャットまたは既存のチャットです。
- 教師ありチャットで動作します。 詳細については、「 [Microsoft Teams で監視付きチャットを使用する](supervise-chats-edu.md)」を参照してください。
  - 既定では、保護者はアクセス許可が制限されているため、学生とチャットしたり、チャットからユーザーを削除したりすることはできません。
  - この設定は、テナント管理者が変更できます。
- 教師は保護者のメールをクリックして、ネイティブメールクライアントを使用してメールを送信できます。
- 教師は保護者の電話番号をクリックして Teams 内で呼び出すことができます。

> [!IMPORTANT]
> クリックして Teams の機能を呼び出すには、テナントに次が必要です。
>
> - Public Branch Exchange (PBX) 機能。
> - PSTN への接続。
>
> Microsoft 365 A1と A3 プランには PBX 機能も PSTN 接続も含まれていません。 [これらのそれぞれにアドオン ライセンスを](/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)購入できます。
>
> Microsoft 365 A5プランには、Teams 電話システムを使用した PBX 機能のみが含まれます。 引き続き [Teams 通話プランを購入するか、サード パーティのソリューションを使用](pstn-connectivity.md) して PSTN の外部番号に接続する必要があります。
>
> PSTN 接続を取得するためのすべてのオプションの詳細については、「 [PSTN 接続オプション](pstn-connectivity.md)」を参照してください。
>
> Teams 通話ライセンスの詳細については、「 [Teams アドオン ライセンス オプション](/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)」を参照してください。

## <a name="requirements"></a>要件

Microsoft Graph または School Data Sync (SDS) を使用して、各学生の保護者に関連する連絡先情報を設定する必要があります。

### <a name="graph-api"></a>Graph API

[既に Microsoft Graph PowerShell SDK](/powershell/microsoftgraph/overview) を使用して Student ID を作成している場合は、[relatedContact リソースの種類](/graph/api/resources/relatedcontact)を簡単に含めることができます。

### <a name="school-data-sync"></a>School Data Sync

SdS が定期的に同期するように設定されている場合、Teams ガーディアンの連絡先データは、School Data Sync (SDS) を使用して SIS に最新の状態を維持します。

*保護者が学生の* レコードから削除された場合、それらに関連する既存のチャットには、チャット所有者に表示されるバナーが含まれます。 このバナーにより、チャット所有者は変更を認識し、チャットから保護者を削除するよう求められます。 Microsoft は、保護者を削除するようにチャット メンバーシップを自動的に更新しません。

- 各学生の保護者 **関連の連絡先情報** を設定するには、School Data Sync (SDS) が必要です。
  - [SDS を展開する](/schooldatasync/parents-and-guardians-in-sds)

- SDS の設定と、テナント内の学生の保護者 **関連の連絡先** の設定に関するサポートが必要な場合は、次の方法で EDU カスタマー サクセス チームにお問い合わせください。
  - [FastTrack](https://www.microsoft.com/fasttrack?rtc=1) での RFA プロセスの完了。
  - [サポート](https://aka.ms/sdssupport)でチケットを開く。

- 現在、SDS では、親連絡先の CSV ベースのデータ インジェストのみがサポートされています。ただし、すべての名簿データに [PowerSchool API Sync](/schooldatasync/how-to-deploy-school-data-sync-by-using-powerschool-sync) または [OneRoster API Sync](/schooldatasync/how-to-deploy-school-data-sync-by-using-oneroster-sync) を使用し、CSV を使用して親連絡先を追加するだけです。
  - [SDS v1 CSV 同期形式](/schooldatasync/school-data-sync-format-csv-files-for-sds)を使用して、2 つ目の同期プロファイルを作成します。
  - v1 ファイルの残りの部分が空の 2 つの親 [ファイル](/schooldatasync/parent-contact-sync-file-format) (ヘッダーのみ) をプルします。
    - User.csv
    - Guardianrelationship.csv
      - 親と保護者が親か保護者かを示すには、各親と保護者の *ロール**値を完了**する必要* があります。
  - v1 CSV ファイルのサンプル セットを表示するには、 [GitHub ファイルの最小必須属性に関するページを](https://github.com/OfficeDev/O365-EDU-Tools/tree/master/CSV%20Samples/SDS%20Format/Min%20Required%20Attributes)参照してください。
  - 初期同期後に CSV ファイルのプルを自動化する場合は、[CSV File Sync Automation ドキュメント](/schooldatasync/csv-file-sync-automation)を参照してください。
  - SDS データ同期の設定に関するヘルプについては、 [カスタマー サクセス チーム](https://www.microsoft.com/fasttrack?rtc=1) に連絡するか、 [サポート チケットを開いてください](https://edusupport.microsoft.com/support?product_id=data_sync)。

### <a name="teams-admin-center-policies"></a>Teams 管理センター ポリシー

- クラス チームの所有者は、Teams チャットを有効にする必要があります。
- クラス チームの所有者は、有効になっている **組織によって管理されていない Teams アカウント** に対する外部アクセス権を持っている必要があります。
  - これは、テナント レベルとユーザー レベルでオンにする必要があります。 テナント レベルの設定は、Teams 管理センターの **[ユーザー >外部アクセス** ] にあります。 この設定には、PowerShell を使用してアクセスすることもできます。 ユーザー レベルの外部アクセス ポリシーには、PowerShell 経由でのみアクセスできます。 詳細なガイダンスについては、以下の PowerShell コマンドを参照してください。

#### <a name="parent-and-guardian-restrictions"></a>保護者の制限

保護者は、保護者接続で *外部ユーザー* として分類されます。つまり、完全なテナント権限がありません。 ユーザーは、自分が参加しているチャットや、チャットで共有されているファイル、画像、その他のコンテンツにのみアクセスできます。

外部チャットの場合、内部ユーザーと外部ユーザーの両方がチャットにユーザーを追加できます。 外部チャット エクスペリエンスの詳細については、「 [Microsoft Teams で外部会議とチャットを管理](manage-external-access.md)する」を参照してください。

また、外部ユーザーは、組織のユーザーのプレゼンス (オフライン、使用可能、ビジーなど) を確認できますが、これは PowerShell を使用してユーザーのプライバシーを保護するためにオフにすることができます。 PowerShell で、 [Set-CsPrivacyConfiguration を](/powershell/module/skype/set-csprivacyconfiguration) 使用し、 を設定 ``EnablePrivacyMode=true``します。

保護者は外部ユーザーであっても、チャットへの投稿は検出可能です。 「Microsoft Teams で [コンテンツの電子情報開示調査を実施する」を参照して、Teams 電子情報開示調査を実施する](ediscovery-investigation.md)方法について説明します。

> [!IMPORTANT]
> IT 管理者は、学生のプライバシーに対するリスクなど、チャットで学生情報を共有するためのベスト プラクティスについて、すべてのクラス所有者を教育する必要があります。

#### <a name="blocking-a-parent-or-guardian-in-a-chat"></a>チャットで親または保護者をブロックする

教師は、親接続で開始されたチャットで保護者をブロックできます。

クラス所有者は次のことができます。

1. 保護者のプロフィール カードを開き、省略記号と **ブロック ユーザー** を選択します。
2. 次に、チャットから保護者を削除します。

ブロックされたユーザーは、クラス所有者との追加のチャットを開始できません。

## <a name="allow-external-access-with-teams-accounts-not-managed-by-an-organization"></a>組織が管理していない Teams アカウントで外部アクセスを許可する

教育者が Teams の保護者と通信できるようにするには、教育テナントの IT 管理者がテナントのポリシーを更新して、テナント外の Teams アカウントに対する外部アクセスを許可する必要があります。 外部アクセスの管理の詳細については、「 [Microsoft Teams での外部アクセスの管理](manage-external-access.md)」を参照してください。

保護者の外部アクセスを有効にする手順を次に示します。

1. 最新の Microsoft Teams PowerShell モジュール プレビューをインストールします。

    ```powershell
    Install-Module -Name PowerShellGet -Force -AllowClobber
    Install-Module -Name MicrosoftTeams -AllowPrerelease -Force –AllowClobber
    ```

2. 管理者特権を持つ資格情報を使用して、次のコマンドを実行します。

    ```powershell
    $credential = Get-Credential
    Connect-MicrosoftTeams -Credential $credential
    ```

    ユーザー レベル (`EnableTeamsConsumerAccess`) で組織によって管理されていない Teams アカウントで外部アクセスを有効にするポリシー設定は、すべてのユーザー レベルの外部アクセス ポリシーに対して既定でオンになっています。 ユーザーが組織によって管理されていない Teams アカウントに外部アクセスできるようにするには、テナント レベルの設定とユーザー レベルのポリシー設定の両方を有効にする必要があります。 テナント内のすべてのユーザーにこのアクセスを有効にさせたくない場合は、テナント レベルの設定がオフになっていることを確認し、ユーザーに割り当てられているユーザー レベルの外部アクセス ポリシーを更新してから、テナント レベルの設定を有効にする必要があります。

    どのユーザー レベルの外部アクセス ポリシーが存在し、誰に割り当てられているかを確認するには、次の手順を使用します。

3. ユーザー レベルの外部アクセス ポリシーが存在することを確認します。

    ```powershell
    Get-CsExternalAccessPolicy
    ```

4. "グローバル" ポリシー以外のポリシーごとに、ポリシーが割り当てられているユーザーを確認します。

   > [!NOTE]
   > 特定のポリシーが割り当てられないユーザーは、"グローバル" ポリシーにフォールバックします。 テナントに追加された新しいユーザーには、"グローバル" ポリシーが割り当てられます。

    ```powershell
    Get-CsOnlineUser -Filter {ExternalAccessPolicy -eq "<PolicyName>"} | Select-Object DisplayName,ObjectId,UserPrincipalName
    ```

すべてのユーザー レベルの外部アクセス ポリシーが `EnableTeamsConsumerAccess` 既定で true に設定されているため、特定のユーザーの設定を調整 `EnableTeamsConsumerAccess` する場合は、調整された設定で既存の外部アクセス ポリシーを作成または変更したり、次の PowerShell コマンドレットを使用してユーザーを新規または既存のポリシーに再割り当てしたりできます。

- 新しい外部アクセス ポリシーを作成 [する: New-CsExternalAccessPolicy](/powershell/module/skype/new-csexternalaccesspolicy)

- 既存の外部アクセス ポリシー ("グローバル" ポリシーを含む) をカスタマイズ [する: Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)

> [!NOTE]
> 次のサブスクリプションの既定のポリシーは変更できません:'FederationAndPICDefault'、'FederationOnly'、'NoFederationAndPIC'。 既定では、すべてのユーザーに割り当て済みの "FederationAndPICDefault" ポリシーが使用されましたが、新しいユーザーには既定で "グローバル" ポリシーが割り当てられます。 これらのサブスクリプションの既定のポリシーが割り当てられているユーザーのポリシー設定を変更する必要がある場合は、これらのユーザーに適切な設定で異なるポリシーを割り当てます。

- 1 人のユーザーに外部アクセス ポリシーを割り当てる: [Grant-CsExternalAccessPolicy](/powershell/module/skype/grant-csexternalaccesspolicy)

- 一連のユーザーにポリシーを割り当てる: [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation)

テナント内のユーザーに対してユーザー レベルの外部アクセス ポリシーが正しく設定されたら、次のコマンドレットを使用してテナントのテナント レベル設定 (`AllowTeamsConsumer`) を有効にすることができます。

- テナントのフェデレーション構成設定を設定する: [Set-CsTenantFederationConfiguration](/powershell/module/skype/set-cstenantfederationconfiguration)

## <a name="turn-on-the-parents-app-in-the-teams-admin-center"></a>Teams 管理センターで保護者アプリを有効にする

保護者アプリは既定でオフになっているため、クラス チームの所有者は、Teams 管理センターで許可されるまで、クラス チームに表示されません。 開発者 [によってブロックされたアプリを許可](manage-apps.md#allow-and-block-apps)するを使用して、Teams 管理センターで保護者アプリが有効になっています。

Teams 管理センターでアプリを [許可およびブロック](manage-apps.md#allow-and-block-apps) するを使用すると、いつでもテナント レベルでアプリをオフにすることができます。 テナント レベルでオフになっている場合、ユーザー レベルのアクセス許可が有効になっている場合でも、すべてのユーザーに対してブロックされます。

保護者向けアプリは、 [Microsoft Teams でアプリのアクセス許可ポリシーを管理](teams-app-permission-policies.md)するを使用して、ユーザー レベルでオフにすることもできます。

## <a name="more-information"></a>詳細情報

- [CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)
- [CsTenantFederationConfiguration](/powershell/module/skype/set-cstenantfederationconfiguration)
